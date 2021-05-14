---
external help file: NetAdapter_Cmdlets.xml
Module Name: NetAdapter
online version: https://docs.microsoft.com/powershell/module/netadapter/get-netadaptersriovvf?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetAdapterSriovVf

## SYNOPSIS
Displays the Single-Root I/O Virtualization (SR-IOV) virtual function (VF) settings.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetAdapterSriovVf [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-FunctionID <UInt16[]>]
 [-IncludeHidden] [-SwitchID <UInt32[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetAdapterSriovVf [-AsJob] [-CimSession <CimSession[]>] [-FunctionID <UInt16[]>] [-IncludeHidden]
 [-SwitchID <UInt32[]>] [-ThrottleLimit <Int32>] -InterfaceDescription <String[]>
```

## DESCRIPTION
The **Get-NetAdapterSriovVf** cmdlet displays the Single-Root I/O Virtualization (SR-IOV) virtual function (VF) settings. 
By default a table of VF settings will be displayed that includes the virtual function identifier (ID), virtual function name, network adapter ID, and the current MAC address.
Specifying a single VF will display that VF in more detail.
Additional displayed fields include the permanent MAC address, requester ID, and virtual port (VPort) information.

The network adapter to use is specified by either the name of the network adapter, interface description of the network adapter, or the switch ID of the virtual switch bound to the SR-IOV network adapter.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetAdapterSriovVf -Name "Ethernet 1"
```

This example returns a list of the VFs with the VM names and MAC addresses for the network adapter named Wired Ethernet Connection 1.

### EXAMPLE 2
```
PS C:\> Get-NetAdapterSriovVf -SwitchId 2
```

This example returns a list of the VFs with the VM names and MAC addresses for the network adapter bound to virtual switch 2.

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

### -FunctionID
Specifies the VF ID number on the indicated network adapter to return more detailed information on the VF.

```yaml
Type: UInt16[]
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

### -SwitchID
Specifies the virtual switch ID that identifies the network adapter for one or more VFs.

```yaml
Type: UInt32[]
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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterSriovVfSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-NetAdapterSriov](./Disable-NetAdapterSriov.md)

[Enable-NetAdapterSriov](./Enable-NetAdapterSriov.md)

[Get-NetAdapterSriov](./Get-NetAdapterSriov.md)

[Set-NetAdapterSriov](./Set-NetAdapterSriov.md)

