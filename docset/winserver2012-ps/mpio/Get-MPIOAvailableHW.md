---
external help file: MPIO_Cmdlets.xml
Module Name: MPIO
online version: https://docs.microsoft.com/powershell/module/mpio/get-mpioavailablehw?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-MPIOAvailableHW

## SYNOPSIS
Lists devices available to the system that can be managed by the Microsoft Device Specific Module (MSDSM) for Multipath I/O (MPIO).

## SYNTAX

```
Get-MPIOAvailableHW [[-VendorId] <String[]>] [[-ProductId] <String[]>] [-AsJob] [-BusType <BusType[]>]
 [-CimSession <CimSession[]>] [-IsMultipathed <Boolean[]>] [-IsSPC3Supported <Boolean[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **** cmdlet lists available hardware devices in the system that can be managed by the Microsoft Device Specific Module (MSDSM) for Multipath I/O (MPIO).

Note: To add one of the devices to MSDSM supported hardware list, use the vendor identifier (ID) and product ID of the device that are outputs from this cmdlet as inputs for the New-MSDSMSupportedHW cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-MPIOAvailableHW
```

This example returns a list of multipath-capable devices currently connected to the system.

### EXAMPLE 2
```
PS C:\>Get-MPIOAvailableHW -BusType iSCSI
```

This example returns a list of multipath-capable devices currently connected to the system via iSCSI.

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

### -BusType
Specifies the bus type via which the device is connected to the system.
The acceptable values for this parameter are: iSCSI, SAS, and FibreChannel.

```yaml
Type: BusType[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -IsMultipathed
Specifies that the device is currently multipath enabled by Microsoft MPIO.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsSPC3Supported
Specifies that the supported specification of the device is T10 SPC3 or later.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProductId
Specifies the product ID of the device.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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
Specifies the vendor ID of the device.

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

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[New-MSDSMSupportedHW](./New-MSDSMSupportedHW.md)

