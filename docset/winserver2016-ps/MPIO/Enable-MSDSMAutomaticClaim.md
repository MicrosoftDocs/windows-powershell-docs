---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Mpio-help.xml
Module Name: MPIO
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/mpio/enable-msdsmautomaticclaim?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-MSDSMAutomaticClaim
---

# Enable-MSDSMAutomaticClaim

## SYNOPSIS
Enables MSDSM to automatically claim SAN disks for MPIO.

## SYNTAX

```
Enable-MSDSMAutomaticClaim [-BusType] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-MSDSMAutomaticClaim** cmdlet enables a Microsoft Device Specific Module (MSDSM) to automatically claim storage area network (SAN) disks for Microsoft Multipath I/O (MPIO) for a bus type.

You must specify a valid bus type, either serial attached storage (SAS) and Internet Small Computer System Interface (iSCSI).
You can enable MSDSM to automatically claim both SAS and iSCSI disks.
Run the cmdlet two times, one time for SAS, one time for iSCSI.

## EXAMPLES

### Example 1: Enable automatic claims for iSCSI
```
PS C:\> Enable-MSDSMAutomaticClaim -BusType "iSCSI"
```

This command enables MSDSM to automatically claim resources with an iSCSI bus type.
Specify SAS instead of iSCSI to enable for an SAS bus type.

## PARAMETERS

### -BusType
Specifies a bus type.
The cmdlet enables MSDSM to automatically claim SAN disks for this bus type.
The acceptable values for this parameter are: SAS and iSCSI.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: SAS, iSCSI

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-MSDSMAutomaticClaim](./Disable-MSDSMAutomaticClaim.md)

[Get-MSDSMAutomaticClaimSettings](./Get-MSDSMAutomaticClaimSettings.md)

