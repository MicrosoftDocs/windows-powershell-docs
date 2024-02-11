---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/new-dfsreplicationgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-DfsReplicationGroup
---

# New-DfsReplicationGroup

## SYNOPSIS
Creates a replication group.

## SYNTAX

```
New-DfsReplicationGroup [-GroupName] <String[]> [[-Description] <String>] [[-DomainName] <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-DfsReplicationGroup** cmdlet creates a replication group.
A replication group is a set of servers, or members, that participate in the replication of one or more folders.
A replicated folder is kept synchronized among the members of a replication group.
This cmdlet cannot modify resource group bandwidth or schedules.

## EXAMPLES

### Example 1: Create a replication group
```
PS C:\> New-DfsReplicationGroup -GroupName "RG01"

GroupName              : RG01
DomainName             : corp.contoso.com
Identifier             : 81251362-e30f-4c1e-b6b0-23906c1ebdd7
Description            :
State                  : Normal
```

This command creates a replication group named RG01.

### Example 2: Create a replication topology
```
PS C:\> New-DfsReplicationGroup -GroupName "Branch Office 1" | New-DfsReplicatedFolder -FolderName "Data Distribution 1" | Add-DfsrMember -ComputerName "SRV01","SRV02","SRV03" | Format-Table dnsname,groupname -auto -wrap

DnsName               GroupName
-------               ---------
SRV01.corp.contoso.com Branch Office 1
SRV02.corp.contoso.com Branch Office 1
SRV03.corp.contoso.com Branch Office 1

PS C:\> Add-DfsrConnection -GroupName "Branch Office 1" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" | Format-Table *name -wrap -autosize

GroupName       SourceComputerName DestinationComputerName
---------       ------------------ -----------------------
Branch Office 1 SRV01               SRV02
Branch Office 1 SRV02               SRV01

PS C:\> Add-DfsrConnection -GroupName "Branch Office 1" -SourceComputerName "SRV01" -DestinationComputerName "SRV03" | Format-Table *name -wrap -autosize

GroupName       SourceComputerName DestinationComputerName
---------       ------------------ -----------------------
Branch Office 1 SRV01               SRV03
Branch Office 1 SRV03               SRV01

PS C:\> Set-DfsrMembership -GroupName "Branch Office 1" -FolderName "Data Distribution 1" -ContentPath "C:\Rf01" -ComputerName "SRV01" -PrimaryMember $True -StagingPathQuotaInMB 16384 -Force | Format-Table *name,*path,primary* -autosize -wrap

DomainName       GroupName       FolderName          ComputerName ContentPath StagingPath                PrimaryMember
----------       ---------       ----------          ------------ ----------- -----------                -------------
corp.contoso.com Branch Office 1 Data Distribution 1 SRV01         c:\Rf01      c:\Rf01\DfsrPrivate\Staging          True

PS C:\> Set-DfsrMembership -GroupName "Branch Office 1" -FolderName "Data Distribution 1" -ContentPath "C:\Rf01" -ComputerName "SRV02","SRV03" -StagingPathQuotaInMB 16384 -Force | Format-Table *name,*path,primary* -autosize -wrap

DomainName       GroupName       FolderName          ComputerName ContentPath StagingPath                PrimaryMember
----------       ---------       ----------          ------------ ----------- -----------                -------------
corp.contoso.com Branch Office 1 Data Distribution 1 SRV02         c:\Rf01      c:\Rf01\DfsrPrivate\Staging         False
corp.contoso.com Branch Office 1 Data Distribution 1 SRV03         c:\Rf01      c:\Rf01\DfsrPrivate\Staging         False
```

This example creates a replication topology with an upstream server and two downstream servers.

The first command uses the **New-DfsReplicationGroup** cmdlet to create a replication group with the name Branch Office 1.
The command pipes the output to the **New-DfsReplicatedFolder** cmdlet to create a replicated folder with the name Data Distribution 1.
The command pipes the output to the **Add-DfsrMember** cmdlet to add the member servers named SRV01, SRV02, and SRV03.
The command formats the output of the pipeline as a table.

The second command uses the **Add-DfsrConnection** cmdlet to add bidirectional connections between servers SRV01 and SRV02.

The third command uses the **Add-DfsrConnection** cmdlet to add bidirectional connections between servers SRV01 and SRV03.

The fourth command uses the **Set-DfsrMembership** cmdlet to set SRV01 as the primary member.

The fifth command uses the **Set-DfsrMembership** cmdlet to set membership for servers SRV02 and SRV03.

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

### -Description
Specifies a description for the replication group.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the NetBIOS name or fully qualified domain name (FQDN) for the Active Directory Domain Service (AD DS) domain that contains a replication group.
If you do not specify this parameter, the cmdlet uses the current domain.

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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## NOTES

## RELATED LINKS

[Get-DfsReplicationGroup](./Get-DfsReplicationGroup.md)

[Remove-DfsReplicationGroup](./Remove-DfsReplicationGroup.md)

[Set-DfsReplicationGroup](./Set-DfsReplicationGroup.md)

[Suspend-DfsReplicationGroup](./Suspend-DfsReplicationGroup.md)

[Sync-DfsReplicationGroup](./Sync-DfsReplicationGroup.md)

