---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/add-dfsrmember?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DfsrMember
---

# Add-DfsrMember

## SYNOPSIS
Adds computers to a replication group.

## SYNTAX

```
Add-DfsrMember [-GroupName] <String[]> [-ComputerName] <String[]> [[-Description] <String>]
 [[-DomainName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DfsrMember** cmdlet adds computers to a replication group as members.
Members of a replication group host replicated folders.
You can specify a description for member computers.
Use the **Remove-DfsrMember** cmdlet to remove members of a replication group.

## EXAMPLES

### Example 1: Add a member to a replication group
```
PS C:\> Add-DfsrMember -GroupName "RG01" -ComputerName "SRV07"
GroupName                    : RG01
ComputerName                 : SRV07
DomainName                   : corp.contoso.com
Identifier                   : 838bba5e-b487-4d1e-8c1c-d2303af49e2a
Description                  :
DnsName                      : SRV07.corp.contoso.com
Site                         : Default-First-Site-Name
NumberOfConnections          : 0
NumberOfInboundConnections   : 0
NumberOfOutboundConnections  : 0
NumberOfInterSiteConnections : 0
NumberOfIntraSiteConnections : 0
IsClusterNode                : False
State                        : Normal
```

This command adds the computer named SRV07 to replication group named RG01.
The console displays the new **DfsrMember** object.

### Example 2: Add multiple members to a new group
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

The fourth command makes the computer named SRV01 the primary member of the group by using the **Set-DfsrMembership** cmdlet. The command also specifies Data Distribution 01 as the name of the replicated folder in the location C:\RF01. The command specifies the staging folder quota as 16384 MB. The command includes the *Force* parameter, and, therefore, does not prompt the user for confirmation.
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
Specifies an array of names of computers.
The cmdlet adds these computers to the replication group specified by the *GroupName* parameter.
You can use a comma separated list and the wildcard character (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: MemberList, MemList

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
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

### -Description
Specifies a description for a member computer.

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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrMember

## NOTES

## RELATED LINKS

[Get-DfsrMember](./Get-DfsrMember.md)

[Remove-DfsrMember](./Remove-DfsrMember.md)

[Set-DfsrMember](./Set-DfsrMember.md)

[New-DfsReplicationGroup](./New-DfsReplicationGroup.md)

[New-DfsReplicatedFolder](./New-DfsReplicatedFolder.md)

[Set-DfsrMembership](./Set-DfsrMembership.md)

