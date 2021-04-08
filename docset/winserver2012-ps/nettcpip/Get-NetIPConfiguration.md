---
author: Kateyanne
external help file: NetTCPIP_Cmdlets.xml
manager: dansimp
Module Name: NetTCPIP
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/nettcpip/get-netipconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetIPConfiguration

## SYNOPSIS
Gets useful network information including usable interfaces, IP addresses and DNS servers.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetIPConfiguration [[-InterfaceAlias] <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetIPConfiguration [-All]
```

### UNNAMED_PARAMETER_SET_3
```
Get-NetIPConfiguration [-CimSession <CimSession>] [-Detailed]
```

### UNNAMED_PARAMETER_SET_4
```
Get-NetIPConfiguration [-InterfaceIndex] <Int32>
```

## DESCRIPTION
The **Get-NetIPConfiguration** cmdlet gets useful network information including usable interfaces, IP addresses and DNS servers.
Additional parameters show if the computer is connected to the Internet (Network Profile information), link layer address information and if DHCP is enabled.

If no parameters are specified, then this cmdlet gets IP configuration properties for all non-virtual connected interfaces on a computer.

This cmdlet does not get the prefix length, which is also known as the subnet mask.
The prefix length is an addressing detail retrieved by the Get-NetIPAddress cmdlet.
See the Get-NetIPAddress cmdlet for more information about retrieving the prefix length.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetIPConfiguration
```

This example gets IP configuration information.
When this cmdlet is run without parameters, it gets the IP configuration information for all of the non-virtual connected interfaces on the computer.

### EXAMPLE 2
```
PS C:\>GIP
```

This example uses the alias for this cmdlet.
`GIP` gets IP configuration information.
When this cmdlet is run without parameters, it gets the IP configuration information for all of the non-virtual connected interfaces on the computer.

### EXAMPLE 3
```
PS C:\>Get-NetIPConfiguration -All
```

This example gets the IP configuration information for all of the interfaces on the computer, including virtual interfaces, loopback interfaces, and disconnected interfaces.

### EXAMPLE 4
```
PS C:\>Get-NetIPConfiguration -Verbose
```

This example gets IP configuration information.
By using the **Verbose** parameter, the networking cmdlets are shown to gather and format the information displayed in this cmdlet.
More information about how to use cmdlets in Windows PowerShell® can be learned by reading the output of this cmdlet with the **Verbose** parameter.

### EXAMPLE 5
```
PS C:\>Get-NetIPConfiguration -InterfaceIndex 12
```

This example gets the IP configuration information for the interface at the index 12.

### EXAMPLE 6
```
PS C:\>Get-NetIPConfiguration | Get-NetIPAddress
```

This example gets the IP address information, including PrefixLength, for the interfaces determined by this cmdlet.

## PARAMETERS

### -All
Indicates that the IP configuration properties for all of the interfaces on a computer are retrieved, including virtual interfaces, loopback interfaces, as well as disconnected interfaces.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Type: CimSession
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Detailed
Indicates that additional interface and computer configuration information are retrieved, including computer name, link layer address, network profile, MTU length, and DHCP status.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies the alias of the interface for which to get the IP configuration properties.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies the index of the interface for which to get the IP configuration properties.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-DNSClientServerAddress](../dnsclient/Get-DnsClientServerAddress.md)

[Get-NetAdapter](../netadapter/Get-NetAdapter.md)

[Get-NetIPAddress](./Get-NetIPAddress.md)

[Get-NetIPInterface](./Get-NetIPInterface.md)

[Get-NetRoute](./Get-NetRoute.md)

