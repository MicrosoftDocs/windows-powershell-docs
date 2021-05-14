---
external help file: NetAdapter_Cmdlets.xml
Module Name: NetAdapter
online version: https://docs.microsoft.com/powershell/module/netadapter/rename-netadapter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Rename-NetAdapter

## SYNOPSIS
Renames a network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Rename-NetAdapter [-Name] <String[]> [-NewName] <String> [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Rename-NetAdapter [-NewName] <String> [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden] [-PassThru]
 [-ThrottleLimit <Int32>] -InterfaceDescription <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Rename-NetAdapter [-NewName] <String> [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Rename-NetAdapter** cmdlet renames a network adapter.
Note: Only the name, or interface alias, can be changed and not the interface description.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Rename-NetAdapter -Name Ethernet -NewName ManagementAdapter


This cmdlet renames a network adapter from the current name, by matching the pattern e*t, to the new name ManagementAdapter. A typical match of e*t is the default name Ethernet.
PS C:\>Rename-NetAdapter -Name E*t -NewName ManagementAdapter
```

This example renames a network adapter from the current name of Ethernet to the new name ManagementAdapter.

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
Accept pipeline input: False
Accept wildcard characters: True
```

### -NewName
Specifies the new name and interface alias of the network adapter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

[Restart-NetAdapter](./Restart-NetAdapter.md)

[Set-NetAdapter](./Set-NetAdapter.md)

