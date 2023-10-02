---
external help file: NetAdapter_Cmdlets.xml
Module Name: NetAdapter
online version: https://learn.microsoft.com/powershell/module/netadapter/disable-netadapterbinding?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-NetAdapterBinding

## SYNOPSIS
Disables a binding to a network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-NetAdapterBinding [-Name] <String[]> [-AllBindings] [-AsJob] [-CimSession <CimSession[]>]
 [-ComponentID <String[]>] [-DisplayName <String[]>] [-IncludeHidden] [-PassThru] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-NetAdapterBinding [-AllBindings] [-AsJob] [-CimSession <CimSession[]>] [-ComponentID <String[]>]
 [-DisplayName <String[]>] [-IncludeHidden] [-PassThru] [-ThrottleLimit <Int32>]
 -InterfaceDescription <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Disable-NetAdapterBinding [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Disable-NetAdapterBinding** cmdlet disables a binding to a network adapter.
Running this cmdlet causes loss of network connectivity depending on the binding that is disabled.
Note: Disabling some adapter bindings can automatically enable other network adapter bindings.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Disable-NetAdapterBinding -Name MyAdapter -DisplayName "Internet Protocol Version 4 (TCP/IPv4)"
```

This example disables TCP/IPv4 on the network adapter named MyAdapter using the display name Internet Protocol Version 4 (TCP/IPv4) and restarts the network adapter.

### EXAMPLE 2
```
PS C:\>Disable-NetAdapterBinding -Name MyAdapter -ComponentID ms_tcpip
```

This example disables TCP/IPv4 on the network adapter named MyAdapter using the component ID ms_tcpip and restarts the network adapter.

### EXAMPLE 3
```
PS C:\>Disable-NetAdapterBinding -Name MyAdapter -DisplayName "Inter* (TCP/IPv4)"
```

This example disables TCP/IPv4 on network adapter named MyAdapter using a wildcard character in the display name and restarts the network adapter.

## PARAMETERS

### -AllBindings
Disables all protocols and filters associated with this network adapter that can be disabled.
Some protocols and filters may be mandatory and therefore cannot be disabled.
Note: Disabling some network adapter bindings can cause other network adapter bindings to automatically be enabled.
Each network adapter binding is disabled only once so after running with this parameter there may still be network adapter bindings that are enabled.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: False
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

### -ComponentID
Specifies the underlying name of the transport or filter in the following form. 

 - `ms_xxxx`, such as `ms_tcpip`.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -DisplayName
Specifies the transport or filter name shown in the Networking tab under the network adapter properties in Windows Server® 2012 and later.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -IncludeHidden
Specifies both visible and hidden network adapters.
If a wildcard character is used to identify a network adapter, then the wildcard character is matched against both hidden and visible adapters.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: ifAlias, InterfaceAlias

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter BindingSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterBindingSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Enable-NetAdapterBinding](./Enable-NetAdapterBinding.md)

[Get-NetAdapterBinding](./Get-NetAdapterBinding.md)

[Set-NetAdapterBinding](./Set-NetAdapterBinding.md)

