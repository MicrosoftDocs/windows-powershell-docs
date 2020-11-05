---
external help file: NetAdapter_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 78FD4A08-1D00-4D41-85AA-ABD1EAC6E46D
manager: dansimp
---

# Set-NetAdapterAdvancedProperty

## SYNOPSIS
Sets the advanced properties of a network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetAdapterAdvancedProperty [[-Name] <String[]>] [-AllProperties] [-AsJob] [-CimSession <CimSession[]>]
 [-DisplayValue <String>] [-IncludeHidden] [-NoRestart] [-PassThru] [-RegistryValue <String[]>]
 [-ThrottleLimit <Int32>] -DisplayName <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetAdapterAdvancedProperty [-AllProperties] [-AsJob] [-CimSession <CimSession[]>] [-DisplayValue <String>]
 [-IncludeHidden] [-NoRestart] [-PassThru] [-RegistryValue <String[]>] [-ThrottleLimit <Int32>]
 -InterfaceDescription <String[]> -RegistryKeyword <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-NetAdapterAdvancedProperty [[-Name] <String[]>] [-AllProperties] [-AsJob] [-CimSession <CimSession[]>]
 [-DisplayValue <String>] [-IncludeHidden] [-NoRestart] [-PassThru] [-RegistryValue <String[]>]
 [-ThrottleLimit <Int32>] -RegistryKeyword <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Set-NetAdapterAdvancedProperty [-AllProperties] [-AsJob] [-CimSession <CimSession[]>] [-DisplayValue <String>]
 [-IncludeHidden] [-NoRestart] [-PassThru] [-RegistryValue <String[]>] [-ThrottleLimit <Int32>]
 -DisplayName <String[]> -InterfaceDescription <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Set-NetAdapterAdvancedProperty [-AsJob] [-CimSession <CimSession[]>] [-DisplayValue <String>] [-NoRestart]
 [-PassThru] [-RegistryValue <String[]>] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm]
 [-WhatIf]
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
PS C:\>Set-NetAdapterAdvancedProperty -Name MyAdapter -RegistryKeyword "*Flo*rol" -RegistryValue "Disable"
```

This example sets the value of the Flow Control advanced property on the network adapter named MyAdapter using wildcard characters in the keyword name.

## PARAMETERS

### -AllProperties
Returns all the advanced properties of the network adapter.
If this parameter is not specified, then only advanced properties that have a DisplayName parameter are returned.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the advanced property.
Note: This parameter is normally used in conjunction with the **DisplayValue** parameter.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: ifDesc

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name
Specifies the name of the network adapter.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
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

