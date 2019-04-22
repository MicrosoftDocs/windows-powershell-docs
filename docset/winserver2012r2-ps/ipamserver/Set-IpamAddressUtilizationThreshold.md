---
external help file: IpamAddressUtilizationThreshold.cdxml-help.xml
Module Name: IpamServer
online version: 
schema: 2.0.0
title: Set-IpamAddressUtilizationThreshold
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 7BFBFA8C-37D8-43BD-9EA7-ABB5C6CD166F
---

# Set-IpamAddressUtilizationThreshold

## SYNOPSIS
Modifies the address utilization thresholds in IPAM.

## SYNTAX

```
Set-IpamAddressUtilizationThreshold [-UnderUtilizationThreshold <UInt32>] [-OverUtilizationThreshold <UInt32>]
 [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-IpamAddressUtilizationThreshold** cmdlet modifies the values for address overutilization and underutilization thresholds in IP address management (IPAM).
Do not specify an overutilization threshold lower than the underutilization.
IPAM generates an alert when a block, subnet, or range utilization exceeds or drops below the overutilization or underutilization thresholds.

## EXAMPLES

### Example 1: Set the overutilization threshold
```
PS C:\> Set-IpamAddressUtilizationThreshold -OverUtilizationThreshold 70 -PassThru
UnderUtilizationThreshold                                   OverUtilizationThreshold

-------------------------                                   ------------------------

20                                                          70
```

This command sets the address overutilization threshold to 70.

### Example 2: Set the underutilization threshold
```
PS C:\>Set-IpamAddressUtilizationThreshold -UnderUtilizationThreshold 40 -PassThru
UnderUtilizationThreshold                                   OverUtilizationThreshold

-------------------------                                   ------------------------

40                                                          70
```

This command sets the address underutilization threshold to 40.

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

### -OverUtilizationThreshold
Specifies the value of the overutilization threshold.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -UnderUtilizationThreshold
Specifies the value of the underutilization threshold.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamAddressUtilizationThreshold
Represents the IPAM address space utilization threshold

## NOTES

## RELATED LINKS

[Get-IpamAddressUtilizationThreshold](./Get-IpamAddressUtilizationThreshold.md)

