---
external help file: MSDSMSupportedHW.cdxml-help.xml
Module Name: MPIO
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/mpio/remove-msdsmsupportedhw?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-MSDSMSupportedHW
---

# Remove-MSDSMSupportedHW

## SYNOPSIS
Removes a hardware identifier (ID) with the specific vendor ID and product ID combination from the Microsoft Device Specific Module (MSDSM) supported hardware list.

## SYNTAX

### ByVendorProductId (Default)
```
Remove-MSDSMSupportedHW [-VendorId] <String[]> [-ProductId] <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-MSDSMSupportedHW -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-MSDSMSupportedHW** cmdlet removes a hardware identifier (ID) with the specific vendor ID and product ID combination from the Microsoft Device Specific Module (MSDSM) supported hardware list.

Note: Unlike MPCLAIM.exe, when specifying the vendor ID and product ID, the fields should not be padded with spaces.

Note: The Update-MPIOClaimedHW cmdlet needs to be run to have the Multipath I/O (MPIO) claiming process take effect.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-MSDSMSupportedHW -VendorId "VendorX" -ProductId "ProductY"
```

This example removes the combination of the vendor ID VendorX and the product ID ProductY from the MSDSM supported hardware list.

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

### -InputObject
Accepts an object from the input pipeline.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Passes the object through to the pipeline.

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

### -ProductId
Represents the product ID.

```yaml
Type: String[]
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
Type: String[]
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

[New-MSDSMSupportedHW](./New-MSDSMSupportedHW.md)

[Update-MPIOClaimedHW](./Update-MPIOClaimedHW.md)

