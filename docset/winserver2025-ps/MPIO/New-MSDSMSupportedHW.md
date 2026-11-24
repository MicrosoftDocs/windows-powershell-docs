---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSDSMSupportedHW.cdxml-help.xml
Module Name: MPIO
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/mpio/new-msdsmsupportedhw?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-MSDSMSupportedHW
---

# New-MSDSMSupportedHW

## SYNOPSIS
Creates a hardware ID with a vendor ID and product ID combination in the MSDSM supported hardware list.

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

Unlike MPCLAIM.exe, when you specify the vendor ID and product ID, do not pad the fields with spaces.

The **Update-MPIOClaimedHW** cmdlet must be run to have the Multipath I/O (MPIO) claiming process take effect.

## EXAMPLES

### Example 1: Add a hardware ID
```
PS C:\> New-MSDSMSupportedHW -ProductID "VendorX" -VendorID "ProductY"
```

This example adds a hardware identifier with vendor ID of VendorX and product ID of ProductY combination in the MSDSM supported hardware list.

### Example 2: Add all applicable hardware IDs
```
PS C:\> New-MSDSMSupportedHW -AllApplicable
```

This example finds all applicable devices and then adds corresponding hardware identifiers to the MSDSM supported hardware list.
Applicable devices are those that are connected to the system by using Fibre Channel, iSCSI, or SAS.

## PARAMETERS

### -AllApplicable
Specifies that all applicable devices that are connected to system by using Fibre Channel, iSCSI, or SAS, are added to the MSDSM supported hardware list.

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
Specifies the product ID.

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
Specifies the vendor ID.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

