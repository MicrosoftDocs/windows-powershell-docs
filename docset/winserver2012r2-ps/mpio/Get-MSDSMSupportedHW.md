---
external help file: MSDSMSupportedHW.cdxml-help.xml
Module Name: MPIO
online version: 
schema: 2.0.0
title: Get-MSDSMSupportedHW
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 93241A3A-A0AD-414A-A8F5-1A633F39C6C3
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-MSDSMSupportedHW

## SYNOPSIS
Lists hardware identifiers (IDs) in the Microsoft Device Specific Module (MSDSM) supported hardware list.

## SYNTAX

```
Get-MSDSMSupportedHW [[-VendorId] <String[]>] [[-ProductId] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MSDSMSupportedHW** cmdlet lists hardware identifiers (IDs) in the Microsoft Device Specific Module (MSDSM) supported hardware list.

Note: When using the **VendorID** and the **ProductID** parameters it is not required to pad the parameter values with trailing spaces like was required with MPCLAIM.EXE.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-MSDSMSupportedHW
```

This example gets all of the hardware IDs from the MSDSM supported hardware list.

### EXAMPLE 2
```
PS C:\>Get-MSDSMSupportedHW -VendorId "VendorX"
```

This example gets all of the hardware IDs for which the vendor ID is VendorX from the MSDSM supported hardware list.

### EXAMPLE 3
```
PS C:\>Get-MSDSMSupportedHW -ProductId "ProductY"
```

This example gets all of the hardware IDs for which the product ID is ProductY from the MSDSM supported hardware list.

### EXAMPLE 4
```
PS C:\>Get-MSDSMSupportedHW -VendorId "VendorX" -ProductId "ProductY"
```

This example gets all of the hardware IDs for which the vendor ID is VendorX and the product ID is ProductY from the MSDSM supported hardware list.

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

### -ProductId
Returns hardware IDs that contain the specified product ID.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -VendorId
Return hardware IDs that contain the specified vendor ID.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Clear-MSDSMSupportedHW](./Clear-MSDSMSupportedHW.md)

[New-MSDSMSupportedHW](./New-MSDSMSupportedHW.md)

[Remove-MSDSMSupportedHW](./Remove-MSDSMSupportedHW.md)

