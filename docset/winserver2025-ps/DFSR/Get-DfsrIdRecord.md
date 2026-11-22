---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/get-dfsridrecord?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsrIdRecord
---

# Get-DfsrIdRecord

## SYNOPSIS
Gets ID records for replicated files or folders from the DFS Replication database.

## SYNTAX

### PathParameterSet (Default)
```
Get-DfsrIdRecord [-Path] <String[]> [[-ComputerName] <String>] [<CommonParameters>]
```

### UidParameterSet
```
Get-DfsrIdRecord [-Uid] <String[]> [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrIdRecord** cmdlet gets ID records for replicated files or folders from the Distributed File System (DFS) Replication database.
Specify unique identifiers (UIDs) or file paths.
A UID consists of a GUID and a version value.

## EXAMPLES

### Example 1: Get an ID record for a specified path
```
PS C:\> Get-DfsrIdRecord -Path "C:\RF01\Accounting 2013.xlsx"
Identifier                  : {031C15B7-397D-4F99-A340-B1C7931EEE01}-v12
Flags                       : 5
Attributes                  : 32
GlobalVersionSequenceNumber : {9F159608-2199-4D8B-B9F5-51D83A778089}-v11
UpdateSequenceNumber        : 77158344
ParentId                    : {1D69BB80-C1DC-4D87-8259-BBD9639C2A7F}-v1
FileId                      : 562949953494937
Volume                      : \\.\C:
Fence                       : 3
Clock                       : 130096051943887948
CreateTime                  : 4/4/2013 6:26:59 PM
UpdateTime                  : 4/4/2013 8:13:14 PM
FileHash                    : 89de8fbaba0b700b 9b2a6b771ee17921
FileName                    : accounting 2013.xlsx
FullPathName                : C:\RF01\Accounting 2013.xlsx
Index                       : 4
ReplicatedFolderId          : 1d69bb80-c1dc-4d87-8259-bbd9639c2a7f
```

This command gets the ID record for a file specified by the file path C:\RF01\Accounting 2013.xlsx.

## PARAMETERS

### -ComputerName
Specifies the name of a replication member computer.
If you do not specify this parameter, the cmdlet uses the current computer.

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

### -Path
Specifies an array of paths for files or folders.
If you specify this parameter, do not specify the *Uid* parameter.

```yaml
Type: String[]
Parameter Sets: PathParameterSet
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Uid
Specifies an array of UIDs for files or folders.
If you specify this parameter, do not specify the *Path* parameter.

```yaml
Type: String[]
Parameter Sets: UidParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### DfsrIdRecord

## NOTES

## RELATED LINKS

[ConvertFrom-DfsrGuid](./ConvertFrom-DfsrGuid.md)

