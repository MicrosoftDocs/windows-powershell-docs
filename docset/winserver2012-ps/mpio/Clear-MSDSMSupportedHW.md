---
external help file: MPIO_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: B5C4D790-55E1-45DB-9DA0-4B2371E6576A
manager: dansimp
---

# Clear-MSDSMSupportedHW

## SYNOPSIS
Removes all hardware identifiers (IDs) from the Microsoft Device Specific Module (MSDSM) supported hardware list.

## SYNTAX

```
Clear-MSDSMSupportedHW [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
This **Clear-MSDSMSupportedHW** cmdlet removes all hardware identifiers (IDs) from the Microsoft Device Specific Module (MSDSM) supported hardware list.

Note: The **Update-MPIOClaimedHW** cmdlet needs to be run to have the MPIO claiming process take effect.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Clear-MSDSMSupportedHW
```

This example removes all hardware IDs from the MSDSM supported hardware list.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-MSDSMSupportedHW](./Get-MSDSMSupportedHW.md)

[New-MSDSMSupportedHW](./New-MSDSMSupportedHW.md)

[Remove-MSDSMSupportedHW](./Remove-MSDSMSupportedHW.md)

[Update-MPIOClaimedHW](./Update-MPIOClaimedHW.md)

