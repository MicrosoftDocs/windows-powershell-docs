---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 38F04AF5-A148-4756-8FE6-D6B911319565
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-DhcpServerv6StatelessStore

## SYNOPSIS
Gets the properties of IPv6 stateless store for the specified IPv6 subnet.

## SYNTAX

```
Get-DhcpServerv6StatelessStore [[-Prefix] <IPAddress[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DhcpServerv6StatelessStore** cmdlet gets the properties of IPv6 stateless store for the specified IPv6 subnet prefix.
If the **Prefix** parameter is not specified, then the properties of IPv6 stateless store at the server level are returned.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv6StatelessStore -ComputerName dhcpserver.contoso.com
```

This example gets the server level configuration for DHCPv6 stateless client store.

### EXAMPLE 2
```
PS C:\>Get-DhcpServerv6StatelessStore -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020::
```

This example gets the configuration for DHCPv6 stateless client store for the scope 2001:4898:7020:1020:.

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

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the Dynamic Host Configuration Protocol (DHCP) server service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prefix
Specifies one or more IPv6 subnet prefixes for one or more scopes for which the stateless store properties are to be returned.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6StatelessStore[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Set-DhcpServerv6StatelessStore](./Set-DhcpServerv6StatelessStore.md)

