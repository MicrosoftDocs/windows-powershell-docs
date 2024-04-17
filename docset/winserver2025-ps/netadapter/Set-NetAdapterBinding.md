---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetAdapterBinding.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netadapter/set-netadapterbinding?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetAdapterBinding
---

# Set-NetAdapterBinding

## SYNOPSIS
Sets the binding state of a transport or filter on a network adapter.

## SYNTAX

### ByName (Default)
```
Set-NetAdapterBinding [-Name] <String[]> [-ComponentID <String[]>] [-DisplayName <String[]>] [-IncludeHidden]
 [-AllBindings] [-Enabled <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInstanceID
```
Set-NetAdapterBinding -InterfaceDescription <String[]> [-ComponentID <String[]>] [-DisplayName <String[]>]
 [-IncludeHidden] [-AllBindings] [-Enabled <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetAdapterBinding -InputObject <CimInstance[]> [-Enabled <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetAdapterBinding** cmdlet sets the binding state of a transport or filter on a network adapter.
By default only visible bindings are set unless the *AllBindings* parameter is specified.
If only enabling or disabling bindings, then the **Enable-NetAdapterBinding** or **Disable-NetAdapterBinding** cmdlets can be used.
If you disable or enable a network adapter binding, the cmdlet can automatically enable or disable other network adapter bindings.

## EXAMPLES

### Example 1: Enable TCP/IPv4 on the specified network adapter
```
PS C:\> Set-NetAdapterBinding -Name "MyAdapter" -DisplayName "Internet Protocol Version 4 (TCP/IPv4)" -Enabled $True
```

This command enables TCP/IPv4 on the network adapter named MyAdapter.

### Example 2: Disable TCP/IPv4 on the specified network adapter
```
PS C:\> Set-NetAdapterBinding -Name "MyAdapter" -DisplayName "Internet Protocol Version 4 (TCP/IPv4)" -Enabled $False
```

This command disables TCP/IPv4 on the network adapter named MyAdapter.

### Example 3: Enable TCP/IPv4 on the specified network adapter using the component ID
```
PS C:\> Set-NetAdapterBinding -Name "MyAdapter" -ComponentID ms_tcpip -Enabled $True
```

This command enables TCP/IPv4 on the network adapter named MyAdapter using the component ID.

## PARAMETERS

### -AllBindings
Indicates that the cmdlet sets filters or transports that are not visible by default.

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

### -ComponentID
Specifies as an array the underlying names of the transport or filter in the following form: `ms_xxxx`, such as `ms_tcpip`.

```yaml
Type: String[]
Parameter Sets: ByName, ByInstanceID
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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies an array of transport or filter names shown in the Networking tab under the network adapter properties in Windows Server® 2012 and later.

```yaml
Type: String[]
Parameter Sets: ByName, ByInstanceID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Indicates whether the transport or filter is enabled or disabled.
The acceptable values for this parameter are: $True or $False.

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
Indicates that the cmdlet includes both visible and hidden network adapters in the operation.
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
Specifies an array of network adapter interface descriptions.
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
Specifies an array of network adapter names.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter BindingSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter BindingSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapterBinding](./Disable-NetAdapterBinding.md)

[Enable-NetAdapterBinding](./Enable-NetAdapterBinding.md)

[Get-NetAdapterBinding](./Get-NetAdapterBinding.md)

