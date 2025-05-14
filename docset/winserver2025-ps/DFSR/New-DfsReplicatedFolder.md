---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/new-dfsreplicatedfolder?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-DfsReplicatedFolder
---

# New-DfsReplicatedFolder

## SYNOPSIS
Creates a replicated folder in a replication group.

## SYNTAX

```
New-DfsReplicatedFolder [-GroupName] <String[]> [-FolderName] <String[]> [[-Description] <String>]
 [[-FileNameToExclude] <String[]>] [[-DirectoryNameToExclude] <String[]>] [[-DfsnPath] <String>]
 [-CreateDisabledMemberships] [[-DomainName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-DfsReplicatedFolder** cmdlet creates a new replicated folder in a replication group.
Replicated folders are logical arrangements of replication that do not contain computer-specific settings.

## EXAMPLES

### Example 1: Create a replicated folder
```
PS C:\> New-DfsReplicatedFolder -GroupName "RG22" -FolderName "RF26"


GroupName              : RG22
FolderName             : RF26
DomainName             : corp.contoso.com
Identifier             : 434ca205-388d-4f24-a5b0-7ff875d433e0
Description            :
FileNameToExclude      : {~*, *.bak, *.tmp}
DirectoryNameToExclude : {}
DfsnPath               :
IsDfsnPathPublished    : False
State                  : Normal
```

This command creates a replicated folder named RF26 in the replication group named RG22.
The command does not alter the default settings for a replicated folder.

### Example 2: Create a replicated folder and add a DFS namespace link path
```
PS C:\> New-DfsReplicatedFolder -GroupName "RG22" -FolderName "RF26" -DfsnPath "\\corp.contoso.com\public\link1"


WARNING: The DfsnPath parameter is not validated. An incorrect path will not produce an error.


GroupName              : RG22
FolderName             : RF267
DomainName             : corp.contoso.com
Identifier             : 111c28cb-348a-47e3-8e4d-4bf394f640bb
Description            :
FileNameToExclude      : {~*, *.bak, *.tmp}
DirectoryNameToExclude : {}
DfsnPath               : \\corp.contoso.com\public\link1
IsDfsnPathPublished    : True
State                  : Normal
```

This command creates a replicated folder named RF26 in the replication group named RG22.
The command **DfsnPath** parameter sets the administrative property for a DFS namespace link path.
The cmdlet reminds the administrator that the DFSN path is cosmetic only and is not verified or used by DFS Replication in any way.

### Example 3: Create a replicated folder that excludes specific file names
```
PS C:\> New-DfsReplicatedFolder -GroupName "RG11" -FolderName "RF08" -FileNameToExclude "~*, *.bak, *.tmp, *.ned"


GroupName              : RG11
FolderName             : RF08
DomainName             : corp.contoso.com
Identifier             : 085a1de3-b4e5-46a4-a8f4-8f36a20bafdf
Description            :
FileNameToExclude      : {~*, *.bak, *.tmp, *.ned}
DirectoryNameToExclude : {}
DfsnPath               :
IsDfsnPathPublished    : False
State                  : Normal
```

This command creates a replicated folder named RF08 in the replication group named RG11.
The command specifies that the DFS Replication service exclude file names starting with a tilde (~) character and files that have the extensions .bak, .tmp, and .ned from replication.

### Example 4: Create a data distribution replication topology
```
The first command uses the **New-DfsReplicationGroup** cmdlet to create a replication group object named Branch Office 1, and passes the object to the **New-DfsReplicatedFolder** cmdlet by using the pipe operator. The **New-DfsReplicatedFolder** cmdlet creates a replication folder object named Data Distribution 1, and passes the object to the **Add-DfsrMember** cmdlet by using the pipe operator. The **Add-DfsrMember** cmdlet adds the computers named SRV01, SRV02, and SRV03 to the replication group named Branch Office 1.
PS C:\> New-DfsReplicationGroup -GroupName "Branch Office 1" | New-DfsReplicatedFolder -FolderName "Data Distribution 1" | Add-DfsrMember -ComputerName "SRV01","SRV02","SRV03" | Format-Table dnsname,groupname -auto -wrap

DnsName               GroupName
-------               ---------
SRV01.corp.contoso.com Branch Office 1
SRV02.corp.contoso.com Branch Office 1
SRV03.corp.contoso.com Branch Office 1


The second command creates a bidirectional replication connection between the computer named SRV01 and the computer named SRV02 in the replication group named Branch Office 1.
PS C:\> Add-DfsrConnection -GroupName "Branch Office 1" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" | Format-Table *name -wrap -auto



GroupName       SourceComputerName DestinationComputerName
---------       ------------------ -----------------------
Branch Office 1 SRV01               SRV02
Branch Office 1 SRV02               SRV01


The third command creates a bidirectional replication connection between the computer named SRV01 and the computer named SRV03 in the replication group named Branch Office 1.
PS C:\> Add-DfsrConnection -GroupName "Branch Office 1" -SourceComputerName "SRV01" -DestinationComputerName "SRV03" | Format-Table *name -wrap -auto
GroupName       SourceComputerName DestinationComputerName
---------       ------------------ -----------------------
Branch Office 1 SRV01               SRV03
Branch Office 1 SRV03               SRV01


The fourth command uses the **Set-DfsrMembership** cmdlet to configure membership settings for the primary member of the replication group named Branch Office 1. The command specifies that the computer named SRV01 is the primary member of the group. The command sets an appropriate quota size of the staging folder instead of the lower default.
PS C:\> Set-DfsrMembership -GroupName "Branch Office 1" -FolderName "Data Distribution 1" -ContentPath "C:\rf1" -ComputerName "SRV01" -PrimaryMember $True -StagingPathQuotaInMB 16384 -Force | Format-Table *name,*path,primary* -auto -wrap


DomainName       GroupName       FolderName          ComputerName ContentPath StagingPath                PrimaryMember
----------       ---------       ----------          ------------ ----------- -----------                -------------
corp.contoso.com Branch Office 1 Data Distribution 1 SRV01         c:\rf1      c:\rf1\DfsrPrivate\Staging          True

The last command uses the **Set-DfsrMembership** cmdlet to configure membership settings for the members of the replication group named Branch Office 1. The command specifies that the computers named SRV02 and SRV03 are members of the group. The command sets an appropriate quota size of the staging folder instead of the lower default.
PS C:\> Set-DfsrMembership -GroupName "Branch Office 1" -FolderName "Data Distribution 1" -ContentPath "C:\rf1" -ComputerName "SRV02","SRV03" -StagingPathQuotaInMB 16384 -Force | Format-Table *name,*path,primary* -auto -wrap


DomainName       GroupName       FolderName          ComputerName ContentPath StagingPath                PrimaryMember
----------       ---------       ----------          ------------ ----------- -----------                -------------
corp.contoso.com Branch Office 1 Data Distribution 1 SRV02         c:\rf1      c:\rf1\DfsrPrivate\Staging         False
corp.contoso.com Branch Office 1 Data Distribution 1 SRV03         c:\rf1      c:\rf1\DfsrPrivate\Staging         False
```

This example creates a hub and spoke data distribution replication topology.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateDisabledMemberships
Indicates that the any members that you add to the replicated folder have disabled memberships.
You do not typically need to set this parameter, because the next step in creating a new replication topology is to create the connections and membership, and then start replication.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the replicated folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DfsnPath
Specifies the DFS Namespace (DFSN) folder path of the replicated folder.

The DFSN folder path has no effect on replication.
This property exists only as a descriptive convenience to administrators and DFS Replication service does not validate the value of this property.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectoryNameToExclude
Specifies an array of names of subfolders that the DSFR service excludes and does not replicate in the replicated folder.
You must provide only folder names, not full paths.
You can use wildcards.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: DirectoryFilter

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the NetBIOS name or fully qualified domain name (FQDN) for the Active Directory Domain Service (AD DS) domain that contains the replication group.
If you do not specify this parameter, the cmdlet uses the domain of the current user.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileNameToExclude
Specifies an array of names and extensions of files that the Distributed File System (DSF) Replication service excludes and does not replicate in the replicated folder.
Provide only folder names for this parameter.
Do not specify full paths.
You can use wildcards.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: FileFilter

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FolderName
Specifies an array of names of replicated folders.
You can use a comma separated list and the wildcard character (*).
If you do not specify this parameter, the cmdlet gets all replicated folders.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RF, RfName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -GroupName
Specifies an array of names of replication groups.
You can use a comma separated list and the wildcard character (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RG, RgName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicatedFolder

## NOTES

## RELATED LINKS

[Get-DfsReplicatedFolder](./Get-DfsReplicatedFolder.md)

[Set-DfsReplicatedFolder](./Set-DfsReplicatedFolder.md)

[Remove-DfsReplicatedFolder](./Remove-DfsReplicatedFolder.md)

