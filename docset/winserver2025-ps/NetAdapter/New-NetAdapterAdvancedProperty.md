---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetAdapterAdvancedProperty.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netadapter/new-netadapteradvancedproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetAdapterAdvancedProperty
---

# New-NetAdapterAdvancedProperty

## SYNOPSIS
Creates an advanced property for the network adapter.

## SYNTAX

### Name (Default)
```
New-NetAdapterAdvancedProperty -RegistryKeyword <String> [-RegistryDataType <RegDataType>]
 -RegistryValue <String[]> [-NoRestart] [-IncludeHidden] [-Name] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceID
```
New-NetAdapterAdvancedProperty -InterfaceDescription <String> -RegistryKeyword <String>
 [-RegistryDataType <RegDataType>] -RegistryValue <String[]> [-NoRestart] [-IncludeHidden]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetAdapterAdvancedProperty** cmdlet creates an advanced property for the network adapter.
The intention is that network adapter manufacturers can use this cmdlet to manage advanced properties that are not directly supported by Windows Server® 2012 and later.
This cmdlet is the cmdlet in the network adapter family that creates a registry key.
All other cmdlets read or modify existing registry entries.
The use of wildcards in the network adapter identifier, either in the *Name* or *InterfaceDescription* parameters, is not supported.

## EXAMPLES

### Example 1: Create an advanced property on the specified network adapter
```
PS C:\> New-NetAdapterAdvancedProperty -Name "MyAdapter" -RegistryKeyword "MyKeyword" -RegistryValue "1" -RegistryDataType REG_SZ
```

This command creates an advanced property on the network adapter named MyAdapter with the registry keyword MyKeyword of type REG_SZ with the value 1.

### Example 2: Create an advanced property on the specified network adapter that does not restart
```
PS C:\> New-NetAdapterAdvancedProperty -Name "MyAdapter" -RegistryKeyword "MyKeyword" -RegistryValue "1" -RegistryDataType REG_SZ -NoRestart
```

This command creates an advanced property on the network adapter named MyAdapter with the registry keyword MyKeyword of type REG_SZ with the value 1 and the network adapter is specified to not restart.
Many advanced properties require restarting the network adapter before the new settings take effect.

### Example 3: Create an advanced property on the specified network adapter
```
PS C:\> $NetworkAdapter3 = Get-NetAdapter -Name "Ethernet 3"
PS C:\> New-NetAdapterAdvancedProperty -InputObject $NetworkAdapter3 -RegistryKeyword "MyKeyword" -RegistryValue "1" -RegistryDataType REG_SZ

This command is  a version of the cmdlet that creates an advanced property on the network adapter named Ethernet 3 using wildcard characters and the pipeline. Use of wildcard characters is not allowed for the network adapter identifier as part of this cmdlet, but can be used via the pipeline.
PS C:\> Get-NetAdapter -Name "Ethernet 3" | New-NetAdapterAdvancedProperty -RegistryKeyword "MyKeyword" -RegistryValue "1" -RegistryDataType REG_SZ
```

The first command gets the network adapter named Ethernet 3 and stores the result in the variable named $NetworkAdapter3.

The second command creates an advanced property for the network adapter stored in the $NetworkAdapter3 variable as registry value 1 for the keyword named MyKeyword.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Indicates that the cmdlet includes both visible and hidden network adapters in the operation.
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
Parameter Sets: InstanceID
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
Type: String
Parameter Sets: Name
Aliases: ifAlias, InterfaceAlias

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoRestart
Indicates that the cmdlet does not restart the network adapter after completing the operation.
Many advanced properties require restarting the network adapter before the new settings take effect.

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
The acceptable values for this parameter are:

- None
- REG_SZ
- REG_DWORD
- REG_QWORD
- REG_MULTI_SZ

```yaml
Type: RegDataType
Parameter Sets: (All)
Aliases:
Accepted values: None, REG_SZ, REG_DWORD, REG_MULTI_SZ, REG_QWORD

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RegistryKeyword
Specifies the name of the registry keyword that this cmdlet creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RegistryValue
Specifies the value of the advanced property as an array.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

