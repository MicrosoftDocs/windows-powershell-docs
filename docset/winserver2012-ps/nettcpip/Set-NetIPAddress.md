---
external help file: NetTCPIP_Cmdlets.xml
Module Name: NetTCPIP
online version: https://docs.microsoft.com/powershell/module/nettcpip/set-netipaddress?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NetIPAddress

## SYNOPSIS
Modifies IP address configuration properties of an existing IP address.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetIPAddress [[-IPAddress] <String[]>] [-AddressFamily <AddressFamily[]>] [-AddressState <AddressState[]>]
 [-AsJob] [-CimSession <CimSession[]>] [-InterfaceAlias <String[]>] [-InterfaceIndex <UInt32[]>] [-PassThru]
 [-PolicyStore <String>] [-PreferredLifetime <TimeSpan>] [-PrefixLength <Byte>]
 [-PrefixOrigin <PrefixOrigin[]>] [-SkipAsSource <Boolean>] [-ThrottleLimit <Int32>] [-Type <Type[]>]
 [-ValidLifetime <TimeSpan>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetIPAddress [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-PreferredLifetime <TimeSpan>]
 [-PrefixLength <Byte>] [-SkipAsSource <Boolean>] [-ThrottleLimit <Int32>] [-ValidLifetime <TimeSpan>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-NetIPAddress** cmdlet modifies IP address configuration properties of an existing IP address.
This cmdlet has 2 types of parameters.
One set of parameters identifies the NetIPAddress object to be modified.
These properties require that you use a IPv4 (or IPv6) address as an identifier and you may include additional properties such as InterfaceIndex.
The second set of parameters enables you to set specific properties.
These properties include Type, PrefixLength, valid or preferred lifetime and skip as source.

Note: IPAddress objects do not allow the IPv4 address or IPv6 address property to be modified after creation.
To create a new IPv6 address or IPv6 address, the New-NetIPAddress cmdlet must be used.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-NetIPAddress -InterfaceIndex 12 -IPAddress 192.168.0.1


Note: The **PrefixLength** parameter may also be specified as part of the New-NetIPAddress cmdlet.
PS C:\>Set-NetIPAddress -InterfaceIndex 12 -IPAddress 192.168.0.1 -PrefixLength 24
```

This example adds a new IP address, and uses this cmdlet to change the prefix length.

### EXAMPLE 2
```
PS C:\>$timesp = ( New-TimeSpan -Days 1 )



PS C:\>Set-NetIPAddress -InterfaceIndex 12 -IPAddress 192.168.0.1 -PreferredLifetime $timesp
```

This example modifies an IP address, setting the **ValidLifetime** parameter to one day.

## PARAMETERS

### -AddressFamily
Specifies the IP address family of the IP address.
The acceptable values for this parameter are:

 -- IPv4: IPv4 address information. 

 -- IPv6: IPv6 address information.

```yaml
Type: AddressFamily[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddressState
Specifies the duplicate address detection (DAD) state for the IP address.
The acceptable values for this parameter are:

 -- Deprecated: IP address configuration information for addresses that will no longer be used to establish new connections, but will continue to be used with existing connections. 

 -- Duplicate: IP address configuration information for addresses for which a duplicate IP address has been detected and the current IP address will not be used. 

 -- Invalid: IP address configuration information for addresses that are not valid and will not be used. 

 -- Preferred: IP address configuration information for addresses that are valid and available for use. 

 -- Tentative: IP address configuration information for addresses that are not used for communication, as the uniqueness of those IP addresses is being verified.

```yaml
Type: AddressState[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -InterfaceAlias
Specifies the interface on which the IP address is configured, as defined by the InterfaceAlias.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies the interface on which the IP address is configured, as defined by the InterfaceIndex number.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPAddress
Specifies the IPv4 or IPv6 address.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
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

### -PolicyStore
Specifies the PolicyStore value.
The acceptable values for this parameter are:

 -- ActiveStore: The IP address information is currently valid. 

 -- PersistentStore: The IP address information is persistent across reboots.
When the computer starts, the PersistentStore settings are copied to the ActiveStore. 

The default value is ActiveStore.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredLifetime
Modifies the PreferredLifetime to the specified values.
PreferredLifetime uses time as defined by the TimeSpanhttps://msdn.microsoft.com/library/system.timespan.aspx structure.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrefixLength
Modifies the PrefixLength of the IP address.
The PrefixLength defines the local subnet size, and is also known as a subnet mask.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrefixOrigin
ps_deprecate_para

```yaml
Type: PrefixOrigin[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipAsSource
Modifies the SkipAsSource flag to True or False.
SkipAsSource is used in a multiple IP address scenario in which the only the primary IP address for outgoing traffic.
The IP addresses that have SkipAsSource set to True are not used for outgoing traffic and are not registered in DNS.

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

### -Type
Specifies the Type of the IP address.
The acceptable values for this parameter are:

 -- Unicast: Marks the address as a unicast address. 

 -- Anycast: Marks the address as an anycast address. 

The default value is Unicast.

```yaml
Type: Type[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValidLifetime
Modifies the PreferredLifetime to the specified values.
ValidLifetime uses time as defined by the TimeSpanhttps://msdn.microsoft.com/library/system.timespan.aspx structure.

```yaml
Type: TimeSpan
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPAddress
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[New-TimeSpan](https://go.microsoft.com/fwlink/p/?LinkId=113360)

[Get-NetIPAddress](./Get-NetIPAddress.md)

[New-NetIPAddress](./New-NetIPAddress.md)

[Remove-NetIPAddress](./Remove-NetIPAddress.md)

