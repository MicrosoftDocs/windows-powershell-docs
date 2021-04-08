---
author: Kateyanne
external help file: DcbQos_Cmdlets.xml
manager: dansimp
Module Name: DcbQoS
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dcbqos/set-netqostrafficclass?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetQosTrafficClass

## SYNOPSIS
Sets the traffic class settings.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetQosTrafficClass [[-Name] <String[]>] [-Algorithm <Algorithm>] [-AsJob] [-BandwidthPercentage <Byte>]
 [-CimSession <CimSession[]>] [-PassThru] [-Priority <Byte[]>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetQosTrafficClass [-Algorithm <Algorithm>] [-AsJob] [-BandwidthPercentage <Byte>]
 [-CimSession <CimSession[]>] [-PassThru] [-Priority <Byte[]>] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetQosTrafficClass** cmdlet modifies the settings of a traffic class, such as the mapping between 802.1p priority and traffic class, the transmission algorithm to be used, and the bandwidth allocation to the traffic class.
If Windows Server® 2012 or later is set to be not willing to accept configurations from a remote device, then Windows Server 2012 or later will send the updated settings to data center bridging (DCB)-capable network adapters in the computer.

For more information on remote device configurations, see the Set-NetQosDcbxSetting cmdlet.

For more information on traffic class, see the New-NetQosTrafficClass cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-NetQosTrafficClass -Name SMB -BandwidthPercentage 50
```

This example changes the bandwidth allocation to traffic class named SMB to 50 percent.

### EXAMPLE 2
```
PS C:\> Get-NetQosTrafficClass -Name SMB | Set-NetQosTrafficClass -Priority 3,4
```

This example gets the settings of the traffic class named SMB and changes the priority mapping setting so that traffic tagged with 3 or 4 are mapped to the traffic class named SMB.

## PARAMETERS

### -Algorithm
Specifies the transmission selection algorithm to assign to the traffic class, such as enhanced transmission selection (ETS).

```yaml
Type: Algorithm
Parameter Sets: (All)
Aliases: Tsa

Required: False
Position: Named
Default value: Ets
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

### -BandwidthPercentage
Specifies the percent of total bandwidth to assign to the traffic class.

```yaml
Type: Byte
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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specified the object which will be modified by this cmdlet.
The object must be piped to the cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the traffic class.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
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

### -Priority
Specifies the IEEE 802.1p priority values.

```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosTrafficClassSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_NetQosTrafficClassSettingData object contains a network traffic class.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosTrafficClassSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_NetQosTrafficClassSettingData object contains a network traffic class.
Only when the **PassThru** parameter is specified will the cmdlet return the MSFT_NetQosTrafficClassSettingData object.

## NOTES

## RELATED LINKS

[Get-NetQosTrafficClass](./Get-NetQosTrafficClass.md)

[New-NetQosTrafficClass](./New-NetQosTrafficClass.md)

[Remove-NetQosTrafficClass](./Remove-NetQosTrafficClass.md)

[Set-NetQosDcbxSetting](./Set-NetQosDcbxSetting.md)

[Set-NetQosTrafficClass](./Set-NetQosTrafficClass.md)

