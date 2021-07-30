---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wsspoolabledisk?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssPoolableDisk
---

# Get-WssPoolableDisk

## SYNOPSIS
Gets disks to use to create storage space.

## SYNTAX

```
Get-WssPoolableDisk [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssPoolableDisk** cmdlet gets objects that represent the physical disks to use to create storage space.

## EXAMPLES

### Example 1: Get poolable disks
```
PS C:\>Get-WssPoolableDisk
```

This command gets objects that represent all of the physical disks available for storage space.

### 1:
```
PS C:\>
```

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.Disk

## NOTES

## RELATED LINKS

[New-WssStorageSpace](./New-WssStorageSpace.md)

[Add-WssDisksToSpacesPool](./Add-WssDisksToSpacesPool.md)

