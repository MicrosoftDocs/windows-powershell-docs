---
external help file: MSFT_NetAdapterSriov.cdxml-help.xml
Module Name: NetAdapter
online version: 
schema: 2.0.0
title: Set-NetAdapterSriov
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: D9B971D9-2C10-424A-A277-704C156C8F18
ms.author: kenwith
ms.reviewer: brianlic
---

# Set-NetAdapterSriov

## SYNOPSIS
Sets the Single-Root I/O Virtualization (SR-IOV) properties of the network adapter, such as the number of virtual functions (VFs), the number of virtual ports (VPorts), and the number of queue pairs for default and non-default VPorts.

## SYNTAX

### ByName (Default)
```
Set-NetAdapterSriov [-Name] <String[]> [-IncludeHidden] [-NumVFs <UInt32>] [-Enabled <Boolean>] [-NoRestart]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByInstanceID
```
Set-NetAdapterSriov -InterfaceDescription <String[]> [-IncludeHidden] [-NumVFs <UInt32>] [-Enabled <Boolean>]
 [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetAdapterSriov -InputObject <CimInstance[]> [-NumVFs <UInt32>] [-Enabled <Boolean>] [-NoRestart]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetAdapterSriov** cmdlet sets the Single-Root I/O Virtualization (SR-IOV) properties of the network adapter.
The properties include the number of virtual functions (VFs), the number of virtual ports (VPorts), and the number of queue pairs for default and non-default VPorts.
The enabled state of SR-IOV can also be set with the cmdlet.

The network adapter for these actions can be specified with the adapter name, interface description, or piped as an input object.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetAdapterSriov -Name "Ethernet 2" -NumVFs 31
```

This example sets the number of VFs available to 31 on the network adapter named Ethernet 2.

### EXAMPLE 2
```
PS C:\>Set-NetAdapterSriov -Name "Ethernet 2" -NumVFs 31 -VPorts 64 -NumQueuePairsForDefaultVPort 2 -NumQueuePairsForNonDefaultVPort 2
```

This example sets the number of VFs to 31 and the total number of VPorts to 64.
This will result in 31 VF and `32` virtual machine queue (VMQ), plus 1 used by the physical function (PF).
Since the number of queue pair is set to 2 for both default and non-default ports, the total number of queue pairs used will be `128`.

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

### -Enabled
Sets the enabled state of SR-IOV on the network adapter.
If set to True, then SR-IOV is Enabled.
If set to False, then SR-IOV is Disabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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

The network adapter can be selected using the **Name** parameter, this parameter, or piped in using the **InputObject** parameter.

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

The network adapter can be selected using this parameter, the **InterfaceDescription** parameter, or piped in using the **InputObject** parameter.

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

### -NumVFs
Specifies the number of VFs that the network adapter exposes for SR-IOV.
This is the maximum number of VFs that Windows Server 2012 and later will allocate on this network adapter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Vf

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterSriovSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterSriovSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The output object will have the updated SR-IOV settings.

## NOTES

## RELATED LINKS

[Disable-NetAdapterSriov](./Disable-NetAdapterSriov.md)

[Enable-NetAdapterSriov](./Enable-NetAdapterSriov.md)

[Get-NetAdapterSriov](./Get-NetAdapterSriov.md)

[Get-NetAdapterSriovVf](./Get-NetAdapterSriovVf.md)

