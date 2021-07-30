---
external help file: DcbQos_Cmdlets.xml
Module Name: DcbQoS
online version: https://docs.microsoft.com/powershell/module/dcbqos/new-netqostrafficclass?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-NetQosTrafficClass

## SYNOPSIS
Creates a new traffic class.

## SYNTAX

```
New-NetQosTrafficClass [-Name] <String> [-Algorithm] <Algorithm> [-Priority] <Byte[]> [-AsJob]
 [-BandwidthPercentage <Byte>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
This **New-NetQosTrafficClass** cmdlet creates a new traffic class.
Traffic class is specified in the enhanced transmission selection (ETS) specification in the IEEE data center bridging (DCB) standard.
In creating a traffic class, the user specifies which types of traffic, differentiated by the IEEE 802.1p priority, are mapped to the traffic class, what transmission algorithm it uses, and how much bandwidth it gets.
If Windows Server® 2012 or later is set to be not willing to accept DCB configurations from a remote device, then Windows Server 2012 or later will program DCB capable network adapters to add this new traffic class.

For more information on remote device configurations, see the Set-NetQosDcbxSetting cmdlet.

There is a default traffic class created by Windows Server 2012 or later.
All 8 priorities are mapped to this default traffic class, which selects ETS as its transmission algorithm and has all of the total bandwidth.
Users cannot delete the default traffic class.
Since a traffic class must have at least one type of traffic mapped to it and there are 8 or less types of such traffic, which is limited by IEEE 802.1p, only 7 additional traffic classes can be created.

In reality, a network adapter that supports DCB may support less than 8 traffic classes.
If there are more traffic classes configured in Windows Server 2012 or later than what a network adapter can support, then Windows Server 2012 or later will not send the configurations to the network adapter.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> New-NetQosTrafficClass -Name "SMB" -Priority 3 -Algorithm ETS -BandwidthPercentage 60
Name                      Algorithm Bandwidth(%) Priority 
----                      --------- ------------ -------- 
SMB                       ETS       60           3
```

Create a traffic class for traffic tagged with the 802.1p value of 3.
This traffic class, named as SMB, has 60 percent of the entire bandwidth.

## PARAMETERS

### -Algorithm
Specifies the transmission selection algorithm to assign to the traffic class.
The acceptable values for this parameter are: ETS or Strict
ETS refers to IEEE 802.1Qaz Enhanced Transmission Selection.
Strict refers to Strict Priority scheduling.
Both of the algorithms are specified in the IEEE 802.1Q standard.

```yaml
Type: Algorithm
Parameter Sets: (All)
Aliases: Tsa

Required: True
Position: 2
Default value: Ets
Accept pipeline input: False
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
Aliases: Bandwidth, Bw

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -Name
Specifies the name of the traffic class.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority
Specifies the IEEE 802.1p priority values.
One priority can be mapped to only one traffic class whereas multiple priorities can be mapped to the same traffic class.

```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosTrafficClassSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_NetQosTrafficClassSettingData object contains a network traffic class.

## NOTES

## RELATED LINKS

[Get-NetQosTrafficClass](./Get-NetQosTrafficClass.md)

[Set-NetQosTrafficClass](./Set-NetQosTrafficClass.md)

