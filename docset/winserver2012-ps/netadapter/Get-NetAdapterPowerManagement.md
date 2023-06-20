---
external help file: NetAdapter_Cmdlets.xml
Module Name: NetAdapter
online version: https://learn.microsoft.com/powershell/module/netadapter/get-netadapterpowermanagement?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetAdapterPowerManagement

## SYNOPSIS
Gets the power management features of the network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetAdapterPowerManagement [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetAdapterPowerManagement [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden] [-ThrottleLimit <Int32>]
 -InterfaceDescription <String[]>
```

## DESCRIPTION
The **Get-NetAdapterPowerManagement** cmdlet gets the state of the power management features of a Power Management capable network adapter. You need to run this cmdlet in an elevated (Run as Administrator) Windows PowerShell session.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetAdapterPowerManagement -Name *
```

This example gets all of the power management capable network adapters.

### EXAMPLE 2
```
PS C:\> Get-NetAdapterPowerManagement -Name Ethernet
```

This example gets the power management properties of the network adapter named Ethernet.

### EXAMPLE 3
```
PS C:\> Get-NetAdapterPowerManagement -Name Ethernet | Format-List -Property *
```

This example displays all of the power management properties of the network adapter named Ethernet.

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

Required: False
Position: 1
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter PowerManagementSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/?LinkID=113302)

[Disable-NetAdapterPowerManagement](./Disable-NetAdapterPowerManagement.md)

[Enable-NetAdapterPowerManagement](./Enable-NetAdapterPowerManagement.md)

[Set-NetAdapterPowerManagement](./Set-NetAdapterPowerManagement.md)

