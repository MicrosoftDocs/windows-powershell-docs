---
external help file: NetAdapter_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: CC6BD443-FDEB-4B8A-B897-725FE316B809
manager: dansimp
---

# Disable-NetAdapterSriov

## SYNOPSIS
Disables Single-Root I/O Virtualization (SR-IOV) on the network adapter.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-NetAdapterSriov [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden] [-NoRestart]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-NetAdapterSriov [-AsJob] [-CimSession <CimSession[]>] [-NoRestart] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Disable-NetAdapterSriov [-AsJob] [-CimSession <CimSession[]>] [-IncludeHidden] [-NoRestart] [-PassThru]
 [-ThrottleLimit <Int32>] -InterfaceDescription <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Disable-NetAdapterSriov** cmdlet disables Single-Root I/O Virtualization (SR-IOV) on the network adapter.
SR-IOV enables network traffic to bypass the software switch layer of the Hyper-V virtualization stack.
As a result, the I/O overhead in the software emulation layer is reduced and can achieve network performance that is nearly the same performance as in non-virtualized environments.

This cmdlet prevents the adapter from using SR-IOV until enabled again.
While SR-IOV is disabled, Windows Server® 2012 and later will not attempt to allocate a virtual function (VF) to a virtual machine (VM).
If VFs from this network adapter are allocated to any VM, then the VFs are revoked and each VM interface reverted to the synthetic network path.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Disable-NetAdapterSriov -Name "Ethernet 1"
```

This example disables SR-IOV on the network adapter named Ethernet 1 and restarts the network adapter.

### EXAMPLE 2
```
PS C:\>$netAdapter3 = Get-NetAdapter -Name "Ethernet 3"



PS C:\>Disable-NetAdapterSriov -InputObject $netAdapter3


A version of the cmdlet that uses the pipeline to select the network adapter named Ethernet 3 and pipes that object into this cmdlet.
PS C:\> Get-NetAdapter -Name "Ethernet 3" | Disable-NetAdapterSriov
```

This example gets a network adapter named Ethernet 3, and disables the network adapter before restarting the network adapter.

### EXAMPLE 3
```
PS C:\> Disable-NetAdapterSriov -Name "Ethernet 2" -NoRestart
```

This example disables SR-IOV on the network adapter named Ethernet 1 without restarting the network adapter.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterSriovSettingData[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterSriovSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The output object contains the network adapter object with SR-IOV disabled.

## NOTES

## RELATED LINKS

[Enable-NetAdapterSriov](./Enable-NetAdapterSriov.md)

[Get-NetAdapter](./Get-NetAdapter.md)

[Get-NetAdapterSriov](./Get-NetAdapterSriov.md)

[Get-NetAdapterSriovVf](./Get-NetAdapterSriovVf.md)

[Get-NetAdapterSriov](./Get-NetAdapterSriov.md)

