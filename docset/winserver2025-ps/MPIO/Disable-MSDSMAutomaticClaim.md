---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Mpio-help.xml
Module Name: MPIO
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/mpio/disable-msdsmautomaticclaim?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-MSDSMAutomaticClaim
---

# Disable-MSDSMAutomaticClaim

## SYNOPSIS
Stops MSDSM from automatically claiming SAN disks for MPIO for a bus type.

## SYNTAX

```
Disable-MSDSMAutomaticClaim [-BusType] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-MSDSMAutomaticClaim** cmdlet stops a Microsoft Device Specific Module (MSDSM) from automatically claiming storage area network (SAN) disks for Microsoft Multipath I/O (MPIO) for a specified bus type.

The valid bus types are serial attached storage (SAS) and Internet Small Computer System Interface (iSCSI).
This cmdlet does not change previously claimed SAN disks.

## EXAMPLES

### Example 1: Disable automatic claim for iSCSI
```
PS C:\> Disable-MSDSMAutomaticClaim -BusType "iSCSI"
```

This command stops MSDSM from automatically claiming SAN disks for MPIO for iSCSI bus types.
The command does not affect previously claimed disks.

The command does not affect the settings for an SAS bus type.
If you want to disable automatic claims for both bus types, use the cmdlet again and specify SAS.

## PARAMETERS

### -BusType
Specifies a bus type.
This cmdlet disables automatic claiming of SAN disks for this bus type.
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

[Enable-MSDSMAutomaticClaim](./Enable-MSDSMAutomaticClaim.md)

[Get-MSDSMAutomaticClaimSettings](./Get-MSDSMAutomaticClaimSettings.md)

