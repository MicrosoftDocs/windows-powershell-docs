---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssmountvhd?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssMountVhd
---

# Get-WssMountVhd

## SYNOPSIS
Gets a collection of VHDs from a backup set.

## SYNTAX

```
Get-WssMountVhd [-BackupSet] <BackupSet> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMountVhd** cmdlet gets a collection of virtual hard drives (VHDs) from a backup set.
Each VHD represents a backup volume in the set.

## EXAMPLES

### Example 1: Get VHDs from a backup set
```
PS C:\> $ContosoBUSet25VHD = Get-WssMountVhd -BackupSet $ContosoBUSet25
```

This example gets the VHD collection from the backup set that is stored in the variable named $ContosoBUSet25 and stores the collection in the variable named $ContosoBUSet25VHD.

## PARAMETERS

### -BackupSet
Specifies the backup set from which to get the collection of VHDs.

```yaml
Type: BackupSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.MountVhdData
This cmdlet generates the Mount Vhd data.

## NOTES

## RELATED LINKS

[Select-WssMountVhd](./Select-WssMountVhd.md)

