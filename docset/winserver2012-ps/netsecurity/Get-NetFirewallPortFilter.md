---
external help file: NetSecurity_Function.xml
Module Name: NetSecurity
online version: https://docs.microsoft.com/powershell/module/netsecurity/get-netfirewallportfilter?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetFirewallPortFilter

## SYNOPSIS
Retrieves port filter objects from the target computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetFirewallPortFilter [-All] [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>]
 [-PolicyStore <String>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetFirewallPortFilter [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>] [-PolicyStore <String>]
 [-ThrottleLimit <Int32>] -AssociatedNetFirewallRule <CimInstance>
```

### UNNAMED_PARAMETER_SET_3
```
Get-NetFirewallPortFilter [-AsJob] [-CimSession <CimSession[]>] [-DynamicTransport <DynamicTransport[]>]
 [-GPOSession <String>] [-PolicyStore <String>] [-Protocol <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-NetFirewallPortFilter [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>] [-PolicyStore <String>]
 [-ThrottleLimit <Int32>] -AssociatedNetIPsecRule <CimInstance>
```

## DESCRIPTION
The **Get-NetFirewallPortFilter** cmdlet returns the port filter objects associated with the input rules.

Port filter objects represent the port and protocol conditions associated with the firewall and IPsec rules.
The **Protocol**, **LocalPort**, **RemotePort**, **IcmpType** and **DynamicTransport** parameters of a single rule are represented in a single rule are represented in a separate NetFirewallPortFilter object.
The filter to rule relationship is always one-to-one and is managed automatically.
Rule parameters associated with filters can only be queried using filter objects.

This cmdlet displays the ports and protocols associated with firewall and IPsec rules.
This allows for rule querying based on the **Protocol**, **LocalPort**, **RemotePort**, **IcmpType** and **DynamicTransport** parameters; this cmdlet returns filter objects that may be further queried with the Where-Objecthttps://go.microsoft.com/fwlink/p/?LinkId=113423 cmdlet.
The cmdlet also allows the interface type filters to be obtained by **Protocol**, **LocalPort**, **RemotePort**, **IcmpType** and **DynamicTransport** parameter query.
The resultant filters are passed into the Get-NetFirewallRule or Get-NetIPsecRule cmdlet to return the rules queried by port or protocol.

To modify the port and protocol conditions, two methods can be used starting with the port filters returned by this cmdlet and optional additional querying.

The array of NetFirewallPortFilter objects can be piped into the Get-NetFirewallRule or Get-NetIPsecRule cmdlet, which returns the rules associated with the filters.
These rules are then piped to the Set-NetFirewallRule or Set-NetIPsecRule cmdlet where the interface properties can be configured.

Alternatively, piping the array of NetFirewallPortFilter objects directly into the Set-NetFirewallInterfaceTypeFilter cmdlet allows the **Protocol**, **LocalPort**, **RemotePort**, **IcmpType** and **DynamicTransport** parameters of the rules to be modified.

## EXAMPLES

### Example 1
```
PS C:\>Get-NetFirewallPortFilter -PolicyStore ActiveStore


This cmdlet displays the same information in a dynamically sized formatted table.
PS C:\>Get-NetFirewallPortFilter -PolicyStore ActiveStore | Format-Table -Property *
```

This example retrieves the port conditions associated with all the rules in the active store.
Note: Running this cmdlet without specifying the policy store retrieves the persistent store.

### Example 2
```
PS C:\>Get-NetFirewallRule -DisplayName "Contoso Messenger" | Get-NetFirewallPortFilter
```

This example gets the port properties of a particular firewall rule.

### Example 3
```
PS C:\>Get-NetFirewallRule -DisplayName "Play To streaming server" | Get-NetFirewallPortFilter | Set-NetFirewallPortFilter -LocalPort 10246


This task can alternatively be done with this cmdlet.
PS C:\>Set-NetFirewallRule -DisplayName "Play To streaming server" -LocalPort 10246
```

This example modifies the local port field of a particular firewall rule.

### Example 4
```
PS C:\>Get-NetFirewallPortFilter | Where-Object -Property { $_.LocalPort -Eq "10246" } | Set-NetFirewallPortFilter -LocalPort Any
```

This example modifies all of the rules associated with a specific port.

### Example 5
```
PS C:\>Get-NetFirewallRule -DisplayGroup "File and Printer Sharing" | Get-NetFirewallPortFilter | Where-Object -Property { $_.RemotePort -Eq "137" } | Set-NetFirewallPortFilter -LocalPort Any
```

This example modifies the interface type associated with all of the firewall rules in a specified group.

### Example 6
```
PS C:\>Get-NetFirewallPortFilter -DynamicTransport ProximitySharing | Get-NetFirewallRule | Set-NetFirewall -Action Block
```

This example shows how to locate the built-in network isolation rule permitting ProximitySharing and blocks it so that the proximity pairing is disallowed.

## PARAMETERS

### -All
Indicates that all of the port filters within the specified policy store are retrieved.

```yaml
Type: SwitchParameter
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

### -AssociatedNetFirewallRule
Gets the port filter object associated with the specified firewall rule to be retrieved. 

This parameter represents a firewall rule, which defines how traffic is filtered by the firewall.
See the New-NetFirewallRule cmdlet for more information.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AssociatedNetIPsecRule
Gets the phase 1 authentication sets that are associated, via the pipeline, with the input IPsec rule to be retrieved. 

A NetIPsecRule object represents an IPsec rule, which determines IPsec behavior.
An IPsec rule can be associated with Phase1AuthSet, Phase2AuthSet, and NetIPsecQuickMode cryptographic sets.
See the New-NetIPsecMainModeRule cmdlet for more information.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -DynamicTransport
Specifies based upon different kinds of dynamic transports.
Some kinds of dynamic transports, like proximity sharing, abstract the network layer details away, meaning standard network layer conditions like protocols and ports cannot be used to identify them.
For instance, Proximity Apps and Proximity Sharing are dynamic transports. 
The acceptable values for this parameter are: Any, ProximityApps, or ProximitySharing 

The default value is Any. 
Note: A rule can be queried for this condition, or modified by using the security filter object.

```yaml
Type: DynamicTransport[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GPOSession
Specifies the network GPO from which to retrieve the rules to be retrieved. 

This parameter is used in the same way as the **PolicyStore** parameter.
When modifying GPOs in Windows PowerShell®, each change to a GPO requires the entire GPO to be loaded, modified, and saved back.
On a busy Domain Controller (DC), this can be a slow and resource-heavy operation.
A GPO Session loads a domain GPO onto the local computer and makes all changes in a batch, before saving it back.
This reduces the load on the DC and speeds up the Windows PowerShell cmdlets.
To load a GPO Session, use the Open-NetGPO cmdlet.
To save a GPO Session, use the Save-NetGPO cmdlet.

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

### -PolicyStore
Specifies the policy store from which to retrieve the rules to be retrieved. 

A policy store is a container for firewall and IPsec policy. 
The acceptable values for this parameter are:

 -- PersistentStore: Sometimes called static rules, this store contains the persistent policy for the local computer.
This policy is not from GPOs, and has been created manually or programmatically (during application installation) on the computer.
Rules created in this store are attached to the ActiveStore and activated on the computer immediately. 

 -- ActiveStore: This store contains the currently active policy, which is the sum of all policy stores that apply to the computer.
This is the resultant set of policy (RSOP) for the local computer (the sum of all GPOs that apply to the computer), and the local stores (the PersistentStore, the static Windows service hardening (WSH), and the configurable WSH). 

 ---- GPOs are also policy stores.
Computer GPOs can be specified as follows. 

 ------ `-PolicyStore hostname`. 

 ---- Active Directory GPOs can be specified as follows. 

 ------ `-PolicyStore domain.fqdn.com\GPO_Friendly_Namedomain.fqdn.comGPO_Friendly_Name`. 

 ------ Such as the following. 

 -------- `-PolicyStore localhost`

 -------- `-PolicyStore corp.contoso.com\FirewallPolicy`

 ---- Active Directory GPOs can be created using the New-GPO cmdlet or the Group Policy Management Console.


 -- RSOP: This read-only store contains the sum of all GPOs applied to the local computer. 

 -- SystemDefaults: This read-only store contains the default state of firewall rules that ship with Windows Server® 2012. 

 -- StaticServiceStore: This read-only store contains all the service restrictions that ship with Windows Server 2012.
Optional and product-dependent features are considered part of Windows Server 2012 for the purposes of WFAS. 

 -- ConfigurableServiceStore: This read-write store contains all the service restrictions that are added for third-party services.
In addition, network isolation rules that are created for Windows Store application containers will appear in this policy store. 

The default value is PersistentStore. 
Note: The Set-NetFirewallRule cmdlet cannot be used to add an object to a policy store.
An object can only be added to a policy store at creation time with the Copy-NetFirewallRule cmdlet or with the New-NetFirewallRule cmdlet.

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

### -Protocol
Specifies that network packets with matching IP addresses match this rule.
This parameter specifies the protocol for an IPsec rule. 
The acceptable values for this parameter are:

 -- Protocols by number:  0 through 255. 

 -- Protocols by name:  TCP, UDP, ICMPv4, or ICMPv6. 

If a port number is identified by using port1 or port2, then this parameter must be set to TCP or UDP. 

The values ICMPv4 and ICMPv6 create a rule that exempts ICMP network traffic from the IPsec requirements of another rule. 

The default value is Any. 
Note: Querying for rules with this parameter can only be performed using filter objects.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetConSecRule[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetFirewallRule
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetProtocolPortFilter[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-Table](https://go.microsoft.com/fwlink/p/?LinkId=113303)

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkId=113423)

[Get-NetFirewallRule](./Get-NetFirewallRule.md)

[Get-NetIPSecRule](./Get-NetIPsecRule.md)

[New-NetFirewallRule](./New-NetFirewallRule.md)

[New-NetIPSecRule](./New-NetIPsecRule.md)

[Set-NetFirewallInterfaceFilter](./Set-NetFirewallInterfaceFilter.md)

[Set-NetFirewallPortFilter](./Set-NetFirewallPortFilter.md)

[Set-NetFirewallRule](./Set-NetFirewallRule.md)

[Set-NetIPSecRule](./Set-NetIPsecRule.md)

[New-GPO](../grouppolicy/New-GPO.md)

