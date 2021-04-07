---
author: Kateyanne
description: 
external help file: MSFT_NetAdapterQos.cdxml-help.xml
manager: jasgro
Module Name: NetAdapter
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/netadapter/disable-netadapterqos?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-NetAdapterQos
---

# Disable-NetAdapterQos

## SYNOPSIS
Disables quality of service (QoS) on the network adapter, specifically data center bridging (DCB).

## SYNTAX

### ByName (Default)
```
Disable-NetAdapterQos [-Name] <String[]> [-IncludeHidden] [-NoRestart] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInstanceID
```
Disable-NetAdapterQos -InterfaceDescription <String[]> [-IncludeHidden] [-NoRestart] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Disable-NetAdapterQos -InputObject <CimInstance[]> [-NoRestart] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-NetAdapterQos** cmdlet disables quality of service (QoS) on a network adapter.
The QoS features, which include bandwidth allocation and priority based flow control, are specified in the IEEE data center bridging (DCB) standard.
When QoS is disabled, the computer will not send to the network adapter any configuration for the QoS features.
This cmdlet does not stop the network adapter from setting up configurations and utilizing the hardware QoS capabilities.

A network adapter that supports DCB is typically known as a converged network adapter.
It supports both storage and networking functionalities.
In some use cases the DCB must be enabled to support the storage functionalities.
If DCB on a network adapter is disabled from the point of view of a computer, then it may still be functioning on the network adapter.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Disable-NetAdapterQos -Name *
```

This example disables QoS on all network adapters and restarts the network adapters.

### EXAMPLE 2
```
PS C:\>Disable-NetAdapterQos -Name "Ethernet 2"

This is the cmdlet using wildcard characters.
PS C:\>Disable-NetAdapterQos -Name E*2
```

This example disables QoS on a network adapter named Ethernet 2 and restarts the network adapter.

### EXAMPLE 3
```
PS C:\> $netAdapterQoS1 = Get-NetAdapterQos -Name *
PS C:\> Disable-NetAdapterQos -InputObject $netAdapterQoS1

This is a version of the cmdlet that gets all of the network adapters that support QoS and disables QoS on all of them via the pipeline, then restarts the QoS network adapters.
PS C:\> Get-NetAdapterQos -Name * | Disable-NetAdapterQos
```

This example gets all of the network adapters that support QoS and disables QoS on all of them and restarts the QoS network adapters.

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

### -IncludeHidden
Specifies both visible and hidden network adapters should be included.
By default only visible network adapters are included.
If a wildcard character is used in identifying a network adapter and this parameter has been specified, then the wildcard string is matched against both hidden and visible network adapters.

```yaml
Type: SwitchParameter
Parameter Sets: ByName, ByInstanceID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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

### -InterfaceDescription
Specifies the network adapter interface description.
For a physical network adapter this is typically the name of the vendor of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: ByInstanceID
Aliases: ifDesc, InstanceID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the network adapter.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias, InterfaceAlias

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoRestart
Specifies that the network adapter is not restarted as part of running this cmdlet.
Note: Many advanced properties require restarting the network adapter before the new settings take effect.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterQosSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The input object is a list of network adapter objects, such as output from the Get-NetAdapter cmdlet.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance# ROOT/StandardCimv2/MSFT_NetAdapterQosSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The output object contains QoS capabilities and configurations on a network adapter.
The output object is returned only when **PassThru** parameter is specified.

## NOTES

## RELATED LINKS

[Enable-NetAdapterQos](./Enable-NetAdapterQos.md)

[Get-NetAdapter](./Get-NetAdapter.md)

[Get-NetAdapterQos](./Get-NetAdapterQos.md)

