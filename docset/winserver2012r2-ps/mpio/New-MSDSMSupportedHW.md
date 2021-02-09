---
external help file: MSDSMSupportedHW.cdxml-help.xml
Module Name: MPIO
online version: 
schema: 2.0.0
title: New-MSDSMSupportedHW
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C61A8B24-45B5-48D0-B2B5-563EE695CA82
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-MSDSMSupportedHW

## SYNOPSIS
Creates a new hardware identifier (ID) with a specific vendor ID and product ID combination in the Microsoft Device Specific Module (MSDSM) supported hardware list.

## SYNTAX

### ByVendorProductId (Default)
```
New-MSDSMSupportedHW [-VendorId] <String> [-ProductId] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByAllApplicable
```
New-MSDSMSupportedHW [-AllApplicable] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-MSDSMSupportedHW** cmdlet creates a new hardware identifier (ID) with a specific vendor ID and product ID combination in the Microsoft Device Specific Module (MSDSM) supported hardware list.

Note: Unlike MPCLAIM.exe, when specifying the vendor ID and product ID, the fields should not be padded with spaces.

Note: The Update-MPIOClaimedHW cmdlet needs to be executed to have the Multipath I/O (MPIO) claiming process take effect.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-MSDSMSupportedHW -ProductID "VendorX" -VendorID "ProductY"
```

This example adds a new hardware identifier with vendor ID of VendorX and product ID of ProductY combination in the MSDSM supported hardware list.

### EXAMPLE 2
```
PS C:\>New-MSDSMSupportedHW -AllApplicable
```

This example finds all applicable devices (connected to system via Fibre Channel, iSCSI, or SAS), and then adds corresponding hardware identifiers to the MSDSM supported hardware list.

## PARAMETERS

### -AllApplicable
Specifies that all applicable devices (connected to system via Fibre Channel, iSCSI, or SAS) will be added to the MSDSM supported hardware list.

```yaml
Type: SwitchParameter
Parameter Sets: ByAllApplicable
Aliases: All

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Represents the product ID.

```yaml
Type: String
Parameter Sets: ByVendorProductId
Aliases: 

Required: True
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
Represents the vendor ID.

```yaml
Type: String
Parameter Sets: ByVendorProductId
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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Clear-MSDSMSupportedHW](./Clear-MSDSMSupportedHW.md)

[Get-MSDSMSupportedHW](./Get-MSDSMSupportedHW.md)

[Remove-MSDSMSupportedHW](./Remove-MSDSMSupportedHW.md)

[Update-MPIOClaimedHW](./Update-MPIOClaimedHW.md)

