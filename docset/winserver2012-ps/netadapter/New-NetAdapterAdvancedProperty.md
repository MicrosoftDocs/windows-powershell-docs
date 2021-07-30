---
external help file: NetAdapter_Cmdlets.xml
Module Name: NetAdapter
online version: https://docs.microsoft.com/powershell/module/netadapter/new-netadapteradvancedproperty?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-NetAdapterAdvancedProperty

## SYNOPSIS
Creates a new advanced property for the network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-NetAdapterAdvancedProperty [-Name] <String> [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden]
 [-NoRestart] [-RegistryDataType <RegDataType>] [-ThrottleLimit <Int32>] -RegistryKeyword <String>
 -RegistryValue <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
New-NetAdapterAdvancedProperty [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden] [-NoRestart]
 [-RegistryDataType <RegDataType>] [-ThrottleLimit <Int32>] -InterfaceDescription <String>
 -RegistryKeyword <String> -RegistryValue <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-NetAdapterAdvancedProperty** cmdlet creates a new advanced property for the network adapter.
The intention is that network adapter manufacturers can use this cmdlet to manage advanced properties that are not directly supported by Windows Server® 2012 and later.
Note: This cmdlet is the cmdlet in the network adapter family that creates a registry key.
All other cmdlets read or modify existing registry entries.
Note: The use of wildcards in the network adapter identifier, either in the **Name** parameter or **InterfaceDescription** parameter, is not supported.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-NetAdapterAdvancedProperty -Name MyAdapter -RegistryKeyword "MyKeyword" -RegistryValue "1" -RegistryDataType REG_SZ
```

This example creates a new advanced property on the network adapter named MyAdapter with the registry keyword MyKeyword of type REG_SZ with the value 1.

### EXAMPLE 2
```
PS C:\>New-NetAdapterAdvancedProperty -Name MyAdapter -RegistryKeyword "MyKeyword" -RegistryValue "1" -RegistryDataType REG_SZ -NoRestart
```

This example creates a new advanced property on the network adapter named MyAdapter with the registry keyword MyKeyword of type REG_SZ with the value 1 and the network adapter is specified to not restart.
Note: Many advanced properties require restarting the network adapter before the new settings take effect.

### EXAMPLE 3
```
PS C:\>$networkAdapter3 = Get-NetAdapter -Name "Ethernet 3"



PS C:\>New-NetAdapterAdvancedProperty -InputObject $networkAdapter3 -RegistryKeyword "MyKeyword" -RegistryValue "1" -RegistryDataType REG_SZ


This is a version of the cmdlet that creates a new advanced property on the network adapter named Ethernet 3 using wildcard characters and the pipeline. Note: Use of wildcard characters is not allowed for the network adapter identifier as part of this cmdlet, but can be used via the pipeline.
PS C:\>Get-NetAdapter -Name "Ethernet 3" | New-NetAdapterAdvancedProperty -RegistryKeyword "MyKeyword" -RegistryValue "1" -RegistryDataType REG_SZ
```

This example gets a network adapter and creates a new advanced property on the network adapter named Ethernet 3.

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
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: ifDesc

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Name
Specifies the name of the network adapter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: ifAlias, InterfaceAlias

Required: True
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

### -RegistryDataType
Specifies the type of the value data to be set in the registry.
The acceptable values for this parameter are: None, REG_SZ, REG_DWORD, REG_QWORD, and REG_MULTI_SZ.

```yaml
Type: RegDataType
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RegistryKeyword
Specifies the name of the registry keyword to be created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -RegistryValue
Specifies the value of the advanced property.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterAdvancedPropertySettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-NetAdapterAdvancedProperty](./Get-NetAdapterAdvancedProperty.md)

[Remove-NetAdapterAdvancedProperty](./Remove-NetAdapterAdvancedProperty.md)

[Reset-NetAdapterAdvancedProperty](./Reset-NetAdapterAdvancedProperty.md)

[Set-NetAdapterAdvancedProperty](./Set-NetAdapterAdvancedProperty.md)

