---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv6scope?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-DhcpServerv6Scope

## SYNOPSIS
Deletes the IPv6 Scopes from the Dynamic Host Configuration Protocol (DHCP) server service corresponding to the specified prefixes.

## SYNTAX

```
Remove-DhcpServerv6Scope [-Prefix] <IPAddress[]> [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-Force] [-Passthru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-DhcpServerv6Scope** cmdlet deletes the IPv6 Scopes from the Dynamic Host Configuration Protocol (DHCP) server service corresponding to the specified prefixes.
Deleting a scope deletes all of the associated settings and leases, if any are present in the scope.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-DhcpServerv6Scope -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020::
```

This example deletes the specified DHCPv6 scope from the specified DHCP server service.

### EXAMPLE 2
```
PS C:\>Remove-DhcpServerv6Scope -ComputerName dhcpserver.contoso.com -Prefix 2001:4898:7020:1020:: -Force
```

This example deletes the specified DHCPv6 scope from the specified DHCP server service without requesting user confirmation even if the scope is active or contains active client leases.

### EXAMPLE 3
```
PS C:\>Get-DhcpServerv6Scope | Where-Object -FilterScript { $_.State -Eq "Inactive" } | Remove-DhcpServerv6Scope -Force -Passthru
```

This example deletes all of the disabled scopes on the DHCP server service.
The Get-DhcpServerv6Scope cmdlet returns the scope objects and pipes the objects into the Where-Objecthttp://go.microsoft.com/fwlink/p/?LinkID=113423 cmdlet.
The Where-Objecthttp://go.microsoft.com/fwlink/p/?LinkID=113423 cmdlet filters the scope objects for the state being InActive (or disabled) and pipes the objects into this cmdlet, which deletes the disabled scopes passed through the pipeline.
If non-empty scopes are deleted without the **Force** parameter, then the cmdlet displays an error.
This cmdlet does not prompt for user confirmation.
Active scopes that are empty get deleted without the **Force** parameter.

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

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

### -Force
Specifies that the scope will be deleted even if there are active leases in the scope.

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

### -Passthru
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

### -Prefix
Specifies one or more IPv6 subnet prefixes of the scopes being deleted.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: True
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Scope[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkID=113423)

[Add-DhcpServerv6Scope](./Add-DhcpServerv6Scope.md)

[Get-DhcpServerv6Scope](./Get-DhcpServerv6Scope.md)

[Get-DhcpServerv6ScopeStatistics](./Get-DhcpServerv6ScopeStatistics.md)

[Set-DhcpServerv6Scope](./Set-DhcpServerv6Scope.md)

