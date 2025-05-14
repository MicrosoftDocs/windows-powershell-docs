---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/set-dfsrmembership?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DfsrMembership
---

# Set-DfsrMembership

## SYNOPSIS
Configures membership settings for replication group members.

## SYNTAX

```
Set-DfsrMembership [-GroupName] <String[]> [-FolderName] <String[]> [-ComputerName] <String[]>
 [[-ContentPath] <String>] [[-PrimaryMember] <Boolean>] [[-StagingPath] <String>]
 [[-StagingPathQuotaInMB] <UInt32>] [[-ConflictAndDeletedQuotaInMB] <UInt32>] [[-ReadOnly] <Boolean>]
 [[-RemoveDeletedFiles] <Boolean>] [[-DisableMembership] <Boolean>]
 [[-MinimumFileStagingSize] <FileStagingSize>] [[-DfsnPath] <String>] [-Force] [[-DomainName] <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DfsrMembership** cmdlet configures membership settings for Distributed File System (DFS) Replication group members.
Members of a replication group host replicated folders.
Use the **Add-DfsrMember** cmdlet to add a member to a group.
Adding a member creates a membership that contains default values.
After you add a member, you can use the current cmdlet to modify membership settings.

Use this cmdlet to specify the name and location of a replicated folder and whether a replicated folder is read-only.
You can specify a member computer as the primary member of its group.

You can also specify how much disk space the member computer allocates for its ConflictsAndDeleted folder and whether to copy deleted replicated files to that folder.
You can specify a staging folder and its maximum size and the smallest file that DSF Replication stages during outbound replication.

You can disable replication for a member computer by using this cmdlet, but to pause replication, disable the connections by using the **Remove-DfsrConnection** cmdlet on the member or use the **Suspend-DfsReplicationGroup** cmdlet.

## EXAMPLES

### Example 1: Change membership settings
```
PS C:\> Set-DfsrMembership -GroupName "RG22" -FolderName "RepFolder" -ComputerName "SRV07" -StagingPathQuotaInMB 32768 -ConflictAndDeletedQuotaInMB 4096
GroupName                   : RG22
ComputerName                : SRV07
FolderName                  : RF01
GroupDomainName             : corp.contoso.com
ComputerDomainName          : corp.contoso.com
Identifier                  : 9931c757-b252-4f04-8347-53575610c423
DistinguishedName           : CN=72c0c2bc-8a4e-4984-a23c-2efadc238724,CN=957751c2-15f0-429b-8688-44c22044226d,CN=DFSR-L
                              ocalSettings,CN=SRV07,OU=Domain Controllers,DC=corp,DC=contoso,DC=com
ContentPath                 : c:\rf01
PrimaryMember               : False
StagingPath                 : c:\rf01\DfsrPrivate\Staging
StagingPathQuotaInMB        : 32768
MinimumStagingFileSize      : Size256KB
ConflictAndDeletedPath      : c:\rf01\DfsrPrivate\ConflictAndDeleted
ConflictAndDeletedQuotaInMB : 4096
ReadOnly                    : False
RemoveDeletedFiles          : False
Enabled                     : True
DfsnPath                    :
State                       : Normal
```

This command changes settings for a replication folder on a computer named SRV07 that belongs to a group named RG22.
The command sets the staging folder quota to 32768 MB and the ConflictAndDeleted folder quota to 4096 MB.
The console displays the membership object, which includes the new values for the settings.

### Example 2: Create a replication group
```
The first command creates a replication group, specifies a replicated folder, and adds three computers to the group as members. The command creates a replication group named River Branch Office by using the **New-DfsReplicationGroup** cmdlet. The command passes the new group to the **New-DfsReplicatedFolder** cmdlet by using the pipeline operator. That cmdlet creates a replicated folder named Data Distribution 01. The command adds three computers, named SRV01, SRV02, and SRV03, to the new replication group.
PS C:\> New-DfsReplicationGroup -GroupName "River Branch Office" | New-DfsReplicatedFolder -FolderName "Data Distribution 01" | Add-DfsrMember -ComputerName "SRV01","SRV02","SRV03" | Format-Table dnsname,groupname -auto -wrap
DnsName                GroupName
-------                ---------
SRV01.corp.contoso.com River Branch Office
SRV02.corp.contoso.com River Branch Office
SRV03.corp.contoso.com River Branch Office

The second command adds a connection between the source computer named SRV01 and the destination computer named SRV02 by using the **Add-DfsrConnection** cmdlet.
PS C:\> Add-DfsrConnection -GroupName "River Branch Office" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" | Format-Table *name -wrap -auto
GroupName           SourceComputerName  DestinationComputerName
---------           ------------------  -----------------------
River Branch Office SRV01               SRV02
River Branch Office SRV02               SRV01

The third command adds a connection between the source computer named SRV01 and the destination computer named SRV03.
PS C:\> Add-DfsrConnection -GroupName "River Branch Office" -SourceComputerName "SRV01" -DestinationComputerName "SRV03" | Format-Table *name -wrap -auto
GroupName           SourceComputerName  DestinationComputerName
---------           ------------------  -----------------------
River Branch Office SRV01               SRV03
River Branch Office SRV03               SRV01

The fourth command makes the computer named SRV01 the primary member of the group. The command also specifies Data Distribution 01 as the name of the replicated folder in the location C:\RF01. The command specifies the staging folder quota as 16384 MB. The command includes the *Force* parameter, and, therefore, does not prompt the user for confirmation.
PS C:\> Set-DfsrMembership -GroupName "River Branch Office" -FolderName "Data Distribution 01" -ContentPath "C:\RF01" -ComputerName "SRV01" -PrimaryMember $True -StagingPathQuotaInMB 16384 -Force | Format-Table *name,*path,primary* -auto -wrap
DomainName       GroupName           FolderName           ComputerName  ContentPath StagingPath                PrimaryMember
----------       ---------           ----------           ------------  ----------- -----------                -------------
corp.contoso.com River Branch Office Data Distribution 01 SRV01         C:\RF01     C:\RF01\DfsrPrivate\Staging         True

The fifth command modifies values for the computers named SRV02 and SRV03. The command specifies Data Distribution 01 as the name of the replicated folder in the location C:\RF01. The command specifies the staging folder quota as 16384 MB. The command includes the *Force* parameter, and, therefore, does not prompt the user for confirmation.Unlike the previous command, this command does not specify a value of the *PrimaryMember* parameter. The computers named SRV02 and SRV03 have the default value of $False for the setting.
PS C:\> Set-DfsrMembership -GroupName "River Branch Office" -FolderName "Data Distribution 1" -ContentPath "C:\RF01" -ComputerName "SRV02","SRV03" -StagingPathQuotaInMB 16384 -Force | Format-Table *name,*path,primary* -auto -wrap
DomainName       GroupName           FolderName           ComputerName  ContentPath StagingPath                PrimaryMember
----------       ---------           ----------           ------------  ----------- -----------                -------------
corp.contoso.com River Branch Office Data Distribution 01 SRV02         C:\RF01     C:\RF01\DfsrPrivate\Staging        False
corp.contoso.com River Branch Office Data Distribution 01 SRV03         C:\RF01     C:\RF01\DfsrPrivate\Staging        False
```

This example sets up a replication group called River Branch Office.
The group consists of three computers, a primary member named SRV01 and two other computers named SRV02 and SRV03.
The example specifies a replication folder and establishes connections between the members.
The example also specifies the maximum size of the staging folder.

Each command returns the appropriate object or objects.
This example uses the **Format-Table** cmdlet to format output in the console.
For more information, type `Get-Help Format-Table`.

## PARAMETERS

### -ComputerName
Specifies an array of names of member computers.
The cmdlet modifies membership settings for these member computers.
You can use a comma separated list and the wildcard character (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: MemberList, MemList

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

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

### -ConflictAndDeletedQuotaInMB
Specifies the maximum size, in megabytes, for the ConflictsAndDeleted folder.
The default value is 4096 MB.

When the size of this folder reaches a specified percent of the quota value, DFS Replication deletes the oldest files in the folder.
The default value is 90 percent.
DFS Replication continues to delete files until the size of the folder reaches a specified percent of the quota value.
The default value is 60 percent.
Use the **Set-DfsrServiceConfiguration** cmdlet to modify the percent values.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContentPath
Specifies a local folder to contain replicated files associated with the replicated folder specified by using the *FolderName* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DfsnPath
Specifies the DFS Namespace folder path of the membership.
You can use this value to keep track of the DFS Namespace folder path.
This value does not affect replication.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 12
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableMembership
Indicates whether to disable the membership for a replication folder in a replication group.

If you disable membership, DFS Replication stops replicating content on this computer, but does not delete the replicated folder or its private replication data.
If you re-enable membership, you will lose any private data and can lose replicated data.
You may be able to recover replicated data by using the **Restore-DfsrPreservedFiles** cmdlet.
By default, memberships are enabled.

If you want to temporarily pause replication, disable the connections on the member by using the **Set-DfsrConnection** cmdlet or use the **Suspend-DfsReplicationGroup** cmdlet.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
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

### -FolderName
Specifies an array of names of replicated folders.
If you do not specify this parameter, the cmdlet applies to all participating replicated folders.
You can use a comma separated list and the wildcard character (*).

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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupName
Specifies an array of names of replication groups.
If you do not specify this parameter, the cmdlet applies to all participating replication groups.
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

### -MinimumFileStagingSize
Specifies the minimum file size that DFS Replication stages during outbound replication.
By default, this value is 256 KB.
If you also disable Remote Differential Compression (RDC), files smaller than this size replicate without staging.
On high-bandwidth, low-latency networks like LANs and high-speed WANs, this typically results in faster replication, at the cost of higher bandwidth saturation.
You can use the **Set-DfsrConnection** cmdlet to disable or enable RDC.

Windows Server® 2012 and previous versions of the Windows operating system do not support the file size setting.
Previous versions of the Windows operating system that support DFS Replication use a hard-coded 256 KB minimum staging size.

The acceptable values for this parameter are:

- Size256KB (0)
- Size512KB (1)
- Size1MB (2)
- Size2MB (3)
- Size4MB (4)
- Size8MB (5)
- Size16MB (6)
- Size32MB (7)
- Size64MB (8)
- Size128MB (9)
- Size256MB (10)
- Size512MB (11)
- Size1GB (12)
- Size2GB (13)
- Size4GB (14)
- Size8GB (15)
- Size16GB (16)
- Size32GB (17)
- Size64GB (18)
- Size128GB (19)
- Size256GB (20)
- Size512GB (21)
- Size1TB (22)
- Size2TB (23)
- Size4TB (24)
- Size8TB (25)
- Size16TB (26)
- Size32TB (27)
- Size64TB (28)
- Size128TB (29)
- Size256TB (30)
- Size512TB (31)

```yaml
Type: FileStagingSize
Parameter Sets: (All)
Aliases:
Accepted values: Size256KB, Size512KB, Size1MB, Size2MB, Size4MB, Size8MB, Size16MB, Size32MB, Size64MB, Size128MB, Size256MB, Size512MB, Size1GB, Size2GB, Size4GB, Size8GB, Size16GB, Size32GB, Size64GB, Size128GB, Size256GB, Size512GB, Size1TB, Size2TB, Size4TB, Size8TB, Size16TB, Size32TB, Size64TB, Size128TB, Size256TB, Size512TB

Required: False
Position: 11
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryMember
Indicates whether this member computer is the primary member of a group.
Specify one and only one membership in each replication group as primary.
By default, members are not primary.

If you specify a value of $True for this parameter, do not specify a value of $True for the *ReadOnly* parameter.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReadOnly
Indicates whether a replicated folder is read-only.
By default, memberships are read/write.

If you change a read/write folder to read-only or change a read-only folder to read/write, DFS Replication moves any local unreplicated changes to the ConflictAndDeleted folder.
You may be able to restore these changes by using the **Restore-DfsrPreservedFiles** cmdlet.

If you specify a value of $True for this parameter, do not specify a value of $True for the *PrimaryMember* parameter.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveDeletedFiles
Indicates whether the member computer deletes files and folders immediately following inbound replication.
If this parameter has a value of $False, the member moves deleted files and folders to the ConflictAndDeleted folder when the deletion replicates inbound.
The originating server always deletes files without preservation.
You can use the **Restore-DfsrPreservedFiles** cmdlet to restore deleted files while they still exist in the ConflictAndDeleted folder.
If this parameter has a value of $True, when a replicating member replicates a deletion, it deletes the local copy of the file immediately.
If you do not specify this parameter, by default, DFS Replication preserves deleted files.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StagingPath
Specifies a local folder for staging content.
If you do not specify this parameter, DFS Replication creates a folder named \<replicated folder\>\DfsrPrivate\Staging.

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

### -StagingPathQuotaInMB
Specifies the maximum size, in megabytes, of a staging folder.
Memberships have a default value is 4096 MB.
When the size of this folder reaches a specified percent, by default, 90, of the quota value, DFS Replication deletes the oldest files in the folder.
DFS Replication continues to delete files until the size of the folder reaches a specified percent, by default, 60, of the quota value.
Use the **Set-DfsrServiceConfiguration** cmdlet to modify the percent values.

If you choose a larger quota, the member computer keeps staged data for longer periods, which provides better replication performance.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, Microsoft.DistributedFileSystemReplication.DfsReplicatedFolder, string

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrMembership

## NOTES

## RELATED LINKS

[Get-DfsrMembership](./Get-DfsrMembership.md)

[Add-DfsrMember](./Add-DfsrMember.md)

[Set-DfsrServiceConfiguration](./Set-DfsrServiceConfiguration.md)

[Restore-DfsrPreservedFiles](./Restore-DfsrPreservedFiles.md)

[Suspend-DfsReplicationGroup](./Suspend-DfsReplicationGroup.md)

[Add-DfsrConnection](./Add-DfsrConnection.md)

[Remove-DfsrConnection](./Remove-DfsrConnection.md)

[Set-DfsrConnection](./Set-DfsrConnection.md)

[New-DfsReplicationGroup](./New-DfsReplicationGroup.md)

[New-DfsReplicatedFolder](./New-DfsReplicatedFolder.md)

