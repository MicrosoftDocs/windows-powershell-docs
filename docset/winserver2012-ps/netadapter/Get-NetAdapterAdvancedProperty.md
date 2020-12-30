---
external help file: NetAdapter_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 9C35AF5F-3291-43E0-93AE-CCBB1B74931C
manager: dansimp
---

# Get-NetAdapterAdvancedProperty

## SYNOPSIS
Returns the advanced properties for the network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetAdapterAdvancedProperty [[-Name] <String[]>] [-AllProperties] [-AsJob] [-CimSession <CimSession[]>]
 [-IncludeHidden] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetAdapterAdvancedProperty [[-Name] <String[]>] [-AllProperties] [-AsJob] [-CimSession <CimSession[]>]
 [-IncludeHidden] [-ThrottleLimit <Int32>] -DisplayName <String[]>
```

### UNNAMED_PARAMETER_SET_3
```
Get-NetAdapterAdvancedProperty [-AllProperties] [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden]
 [-ThrottleLimit <Int32>] -InterfaceDescription <String[]> -RegistryKeyword <String[]>
```

### UNNAMED_PARAMETER_SET_4
```
Get-NetAdapterAdvancedProperty [-AllProperties] [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden]
 [-ThrottleLimit <Int32>] -DisplayName <String[]> -InterfaceDescription <String[]>
```

### UNNAMED_PARAMETER_SET_5
```
Get-NetAdapterAdvancedProperty [-AllProperties] [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden]
 [-ThrottleLimit <Int32>] -InterfaceDescription <String[]>
```

### UNNAMED_PARAMETER_SET_6
```
Get-NetAdapterAdvancedProperty [[-Name] <String[]>] [-AllProperties] [-AsJob] [-CimSession <CimSession[]>]
 [-IncludeHidden] [-ThrottleLimit <Int32>] -RegistryKeyword <String[]>
```

## DESCRIPTION
The **Get-NetAdapterAdvancedProperty** cmdlet gets the advanced properties for the network adapter.
By default this cmdlet returns advanced properties that have display name values, meaning that these advanced properties are visible in the Advanced pane of the Adapter Properties in the Windows UI.
Advanced properties that do not have display names require that the **AllProperties** parameter is specified.
Individual advanced properties can also be selected either by **DisplayName** or **RegistryKeyword** parameters.
Both of these parameters support the use of wildcard characters.
The advanced properties are normally found in the following location in the registry `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Class\{4D36E972-E325-11CE-BFC1-08002BE10318}\xxxxxxxx` where `xxxx` is a four character string representing an integer such as `0007`.
The standardized keywords have a RegistryKeyword name that begins with an asterisk (`*`).
The valid values for these keywords are available by piping the output into the Format-Listhttp://go.microsoft.com/fwlink/p/?LinkID=113302 cmdlet with the ValidDisplayValues or the ValidRegistryValues specified.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetAdapterAdvancedProperty -Name *
```

This example gets all of the advanced properties that have a display name from all visible network adapters.

### EXAMPLE 2
```
PS C:\>Get-NetAdapterAdvancedProperty -Name * -AllProperties
```

This example gets all of the advanced properties from all visible network adapters.

### EXAMPLE 3
```
PS C:\>Get-NetAdapterAdvancedProperty -Name * -RegistryKeyword *
```

This example gets all of the advanced properties from all visible network adapters.

### EXAMPLE 4
```
PS C:\>Get-NetAdapterAdvancedProperty -Name * -AllProperties -IncludeHidden
```

This example gets all of the advanced properties from all network adapters.

### EXAMPLE 5
```
PS C:\>Get-NetAdapterAdvancedProperty -Name * -RegistryKeyword * -IncludeHidden
```

This example gets all of the advanced properties from all network adapters.

### EXAMPLE 6
```
PS C:\>Get-NetAdapterAdvancedProperty -Name MyAdapter | Format-List -Property *
```

This example gets all of the unformatted, advanced properties  from the network adapter named MyAdapter.

### EXAMPLE 7
```
PS C:\>Get-NetAdapterAdvancedProperty -Name * | Where-Object -FilterScript { $_.DisplayName -Like "TCP*" }
```

This example gets the advanced properties for network adapters that have a display name that starts with TCP.

### EXAMPLE 8
```
PS C:\>Get-NetAdapterAdvancedProperty -Name * | Where-Object -FilterScript { $_.DisplayName -Like "Inter*" }
```

This example gets the advanced properties for network adapters that have a display name that starts with Inter.

## PARAMETERS

### -AllProperties
Returns all the advanced properties of the network adapter.
If this parameter is not specified, then only advanced properties that have a **DisplayName** parameter are returned.

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
Specifies the advanced property name shown in the Advanced tab under the network adapter properties in Windows Server® 2012 and later.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -IncludeHidden
Specifies both visible and hidden network adapters should be included.
By default only visible network adapters are included.
If a wildcard character is used in identifying a network adapter and this parameter has been specified, then the wildcard string is matched against both hidden and visible network adapters.

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

### -InterfaceDescription
Specifies the network adapter interface description.
For a physical network adapter this is typically the name of the vendor of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_6
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -RegistryKeyword
Contains the name of the registry value to be read, such as one of the registry values found in HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Class\{4D36E972-E325-11CE-BFC1-08002BE10318}\0007.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_6
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterAdvancedPropertySettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/p/?LinkID=113302)

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkID=113423)

[New-NetAdapterAdvancedProperty](./New-NetAdapterAdvancedProperty.md)

[Remove-NetAdapterAdvancedProperty](./Remove-NetAdapterAdvancedProperty.md)

[Reset-NetAdapterAdvancedProperty](./Reset-NetAdapterAdvancedProperty.md)

[Set-NetAdapterAdvancedProperty](./Set-NetAdapterAdvancedProperty.md)

