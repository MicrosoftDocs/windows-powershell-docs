---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSDSMSupportedHW.cdxml-help.xml
Module Name: MPIO
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/mpio/get-msdsmsupportedhw?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MSDSMSupportedHW
---

# Get-MSDSMSupportedHW

## SYNOPSIS
Lists hardware IDs in the MSDSM supported hardware list.

## SYNTAX

```
Get-MSDSMSupportedHW [[-VendorId] <String[]>] [[-ProductId] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MSDSMSupportedHW** cmdlet lists hardware identifiers (IDs) in the Microsoft Device Specific Module (MSDSM) supported hardware list.

When you specify the *VendorID* and the *ProductID* parameters, you do not have to pad the parameter values with trailing spaces in the way you did for MPCLAIM.EXE.

## EXAMPLES

### Example 1: Get hardware IDs
```
PS C:\> Get-MSDSMSupportedHW
```

This example gets all of the hardware IDs from the MSDSM supported hardware list.

### Example 2: Get hardware IDs for a vendor ID
```
PS C:\> Get-MSDSMSupportedHW -VendorId "VendorX"
```

This example gets all of the hardware IDs for which the vendor ID is VendorX from the MSDSM supported hardware list.

### Example 3: Get hardware IDs for a product ID
```
PS C:\> Get-MSDSMSupportedHW -ProductId "ProductY"
```

This example gets all of the hardware IDs for which the product ID is ProductY from the MSDSM supported hardware list.

### Example 4: Get hardware IDs vendor Id and product ID
```
PS C:\> Get-MSDSMSupportedHW -VendorId "VendorX" -ProductId "ProductY"
```

This example gets all of the hardware IDs for which the vendor ID is VendorX and the product ID is ProductY from the MSDSM supported hardware list.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies product ID for which this cmdlet gets hardware IDs.

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
Specifies vendor IDs for which this cmdlet gets hardware IDs.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Clear-MSDSMSupportedHW](./Clear-MSDSMSupportedHW.md)

[New-MSDSMSupportedHW](./New-MSDSMSupportedHW.md)

[Remove-MSDSMSupportedHW](./Remove-MSDSMSupportedHW.md)

