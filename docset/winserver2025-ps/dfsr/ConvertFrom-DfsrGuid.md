---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/convertfrom-dfsrguid?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-DfsrGuid
---

# ConvertFrom-DfsrGuid

## SYNOPSIS
Translates GUIDs to friendly names within a given replication group.

## SYNTAX

```
ConvertFrom-DfsrGuid [-GroupName] <String[]> [-Guid] <Guid[]> [[-DomainName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **ConvertFrom-DfsrGuid** cmdlet translates Distributed File System (DFS) Replication GUIDs to friendly names within a given replication group.
DFS Replication uses GUIDs to represent the friendly names of various objects and metadata.
DFS Replication writes these GUIDs to Active Directory, XML files, the event log, and debug logs.
This cmdlet converts GUIDs for connections (connid), replicated folders (csid), replication groups (rgid), volumes (volumeid), members (memberid), and databases (dbguid).

## EXAMPLES

### Example 1: Convert a GUID to a friendly name
```
PS C:\> ConvertFrom-DfsrGuid -GroupName RG01 -Guid 9268F23A-7701-4184-8B8B-4BFDBB8AC411

GroupName              : RG01
FolderName             : RF01
DomainName             : corp.contoso.com
Identifier             : 9268f23a-7701-4184-8b8b-4bfdbb8ac411
Description            :
FileNameToExclude      : {~*, *.bak, *.tmp}
DirectoryNameToExclude : {}
DfsnPath               :
IsDfsnPathPublished    : False
```

This command uses the **ConvertFrom-DfsrGuid** cmdlet to convert a replicated folder GUID to its friendly details.

### Example 2: Determine which server originated a file modification
```
PS C:\> Get-DfsrIdRecord -Path C:\rf01\canary.bmp | Format-List global* GlobalVersionSequenceNumber : {B34A6F21-A20D-402D-9BE1-467309C21CDF}-v20
PS C:\> ConvertFrom-DfsrGuid -GroupName Rg01 -guid B34A6F21-A20D-402D-9BE1-467309C21CDF

ComputerName : SRV01
DomainName   : corp.contoso.com
VolumeGuid   : 9ee0fc3b-a906-11e2-8f95-806e6f6e6963
SerialNumber : 903727946
Path         : \\.\C:
DatabaseGuid : B34A6F21-A20D-402D-9BE1-467309C21CDF
```

This example looks up a Global Version Sequence Number (GUID) for a file, and then looks up the name of the server that originated that change.

The first command uses the **Get-DfsrIdRecord** cmdlet to lookup a file's Global Version Sequence Number (GUID).

The second command looks up the server that originated the change.

## PARAMETERS

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
If you do not specify this parameter, the cmdlet queries for all participating replication groups.
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

### -Guid
Specifies an array of GUID values to convert to a friendly name.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, Guid

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, Microsoft.DistributedFileSystemReplication.DfsReplicatedFolder, Microsoft.DistributedFileSystemReplication.DfsrMember, Microsoft.DistributedFileSystemReplication.DfsrMembership, Microsoft.DistributedFileSystemReplication.DfsrConnection, Microsoft.DistributedFileSystemReplication.DfsrVolume

## NOTES

## RELATED LINKS

