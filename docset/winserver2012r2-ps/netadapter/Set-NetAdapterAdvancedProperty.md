---
external help file: MSFT_NetAdapterAdvancedProperty.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/netadapter/set-netadapteradvancedproperty?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetAdapterAdvancedProperty
---

# Set-NetAdapterAdvancedProperty

## SYNOPSIS
Sets the advanced properties of a network adapter.

## SYNTAX

### ByName (Default)
```
Set-NetAdapterAdvancedProperty [[-Name] <String[]>] [-DisplayName <String[]>] [-RegistryKeyword <String[]>]
 [-IncludeHidden] [-AllProperties] [-DisplayValue <String>] [-RegistryValue <String[]>] [-NoRestart]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByInstanceID
```
Set-NetAdapterAdvancedProperty -InterfaceDescription <String[]> [-DisplayName <String[]>]
 [-RegistryKeyword <String[]>] [-IncludeHidden] [-AllProperties] [-DisplayValue <String>]
 [-RegistryValue <String[]>] [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetAdapterAdvancedProperty -InputObject <CimInstance[]> [-DisplayValue <String>]
 [-RegistryValue <String[]>] [-NoRestart] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetAdapterAdvancedProperty** cmdlet sets the advanced properties of a network adapter.
Changes are made directly into the registry for the computer.
Many of the common advanced properties can be controlled via a cmdlet, such as the Set-NetAdapterRss or Set-NetAdapterLso cmdlets.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NetAdapterAdvancedProperty -Name MyAdapter -DisplayName "Flow Control" -DisplayValue "Rx and Tx Enabled"
```

This example sets the value of the Flow Control advanced property on the network adapter named MyAdapter.

### EXAMPLE 2
```
PS C:\>Set-NetAdapterAdvancedProperty -Name MyAdapter -DisplayName "Flow Control" -DisplayValue "Disable"
```

This example sets the value of the Flow Control advanced property on the network adapter named MyAdapter.

### EXAMPLE 3
```
PS C:\>Set-NetAdapterAdvancedProperty -Name MyAdapter -RegistryKeyword "*Flo*rol" -RegistryValue 0
```

This example sets the value of the Flow Control advanced property on the network adapter named MyAdapter using wildcard characters in the keyword name.

## PARAMETERS

### -AllProperties
Returns all the advanced properties of the network adapter.
If this parameter is not specified, then only advanced properties that have a DisplayName parameter are returned.

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

### -DisplayName
Specifies the display name of the advanced property.
Note: This parameter is normally used in conjunction with the **DisplayValue** parameter.

```yaml
Type: String[]
Parameter Sets: ByName, ByInstanceID
Aliases: DispN

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayValue
Specifies the new value of the advanced property named with the **DisplayName** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the network adapter.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias, InterfaceAlias

Required: False
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

### -RegistryKeyword
Specifies the name of the registry keyword to be set.
Note: This parameter is normally used in conjuction with the **RegistryValue** parameter.

```yaml
Type: String[]
Parameter Sets: ByName, ByInstanceID
Aliases: RegKey

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RegistryValue
Specifies the value of the advanced property named in the **RegistryKeyword** parameter.

```yaml
Type: String[]
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterAdvancedPropertySettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterAdvancedPropertySettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetAdapterAdvancedProperty](./Get-NetAdapterAdvancedProperty.md)

[New-NetAdapterAdvancedProperty](./New-NetAdapterAdvancedProperty.md)

[Remove-NetAdapterAdvancedProperty](./Remove-NetAdapterAdvancedProperty.md)

[Reset-NetAdapterAdvancedProperty](./Reset-NetAdapterAdvancedProperty.md)

[Set-NetAdapterLso](./Set-NetAdapterLso.md)

[Set-NetAdapterRss](./Set-NetAdapterRss.md)

