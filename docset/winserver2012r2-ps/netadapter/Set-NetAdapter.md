---
external help file: MSFT_NetAdapter.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
online version: 
schema: 2.0.0
title: Set-NetAdapter
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 37D9BA48-4D42-4128-96C5-5F3CDB1C2F50
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-NetAdapter

## SYNOPSIS
Sets the basic network adapter properties.

## SYNTAX

### ByName (Default)
```
Set-NetAdapter [-Name] <String[]> [-IncludeHidden] [-VlanID <UInt16>] [-MacAddress <String>] [-NoRestart]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByInstanceID
```
Set-NetAdapter -InterfaceDescription <String[]> [-IncludeHidden] [-VlanID <UInt16>] [-MacAddress <String>]
 [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetAdapter -InputObject <CimInstance[]> [-VlanID <UInt16>] [-MacAddress <String>] [-NoRestart]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetAdapter** cmdlet sets the basic properties of a network adapter such as virtual LAN (VLAN) identifier (ID) and MAC address.
Note: These changes could disrupt proper networking functionality.
Other network adapter properties may be settable by using a cmdlet such as the Set-NetAdapterRss, Set-NetAdapterLso, or Set-NetAdapterAdvancedProperty cmdlets.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetAdapter -Name "Ethernet 1" -VlanID 10
```

This example sets the network adapter named Ethernet 1 to have VLAN ID 10.

### EXAMPLE 2
```
PS C:\>Set-NetAdapter -Name "Ethernet 1" -MacAddress "00-10-18-57-1B-0D"
```

This example sets the MAC Address of the network adapter named Ethernet 1.

### EXAMPLE 3
```
PS C:\>Set-NetAdapter -InterfaceDescription B*2 -MacAddress "00-10-18-57-1B-0D"
```

This example sets the MAC address of a network adapter with the interface description matching the pattern B*2.

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
Aliases: ifDesc

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MacAddress
Specifies the current MAC address of the network adapter.
Dashes are optional as part of the input.
Note: Not all network adapters support setting the MAC address.
The address passed in will be also saved in the network addresses property without dashes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: LinkLayerAddress

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Accept pipeline input: False
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

### -VlanID
Specifies the VLAN ID of the network adapter.
Note: Not all network adapters support setting the VLAN ID.

```yaml
Type: UInt16
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapter](./Disable-NetAdapter.md)

[Enable-NetAdapter](./Enable-NetAdapter.md)

[Get-NetAdapter](./Get-NetAdapter.md)

[Rename-NetAdapter](./Rename-NetAdapter.md)

[Restart-NetAdapter](./Restart-NetAdapter.md)

[Set-NetAdapterAdvancedProperty](./Set-NetAdapterAdvancedProperty.md)

[Set-NetAdapterLso](./Set-NetAdapterLso.md)

[Set-NetAdapterRss](./Set-NetAdapterRss.md)

