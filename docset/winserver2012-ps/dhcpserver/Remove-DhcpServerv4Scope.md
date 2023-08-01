---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv4scope?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-DhcpServerv4Scope

## SYNOPSIS
Deletes the specified IPv4 scopes from the  Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

```
Remove-DhcpServerv4Scope [-ScopeId] <IPAddress[]> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-Force] [-Passthru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-DhcpServerv4Scope** cmdlet deletes the specified IPv4 scopes from the Dynamic Host Configuration Protocol (DHCP) server service.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Remove-DhcpServerv4Scope -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0, 20.20.20.0
```

This example deletes the specified scopes from the DHCP server service.

### EXAMPLE 2
```
PS C:\> Remove-DhcpServerv4Scope -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0, 20.20.20.0 -Force
```

This example deletes the specified scopes from the DHCP server service.
This cmdlet does not prompt the user for confirmation even if the scopes are active or contain active client leases.

### EXAMPLE 3
```
PS C:\> Get-DhcpServerV4Scope | Where-Object -FilterScript { $_.State -Eq "Inactive" } | Remove-DhcpServerv4Scope -Force -Passthru
```

This example deletes all of the disabled scopes on the DHCP server service.
The Get-DhcpServerv4Scope cmdlet returns the scope objects and pipes the scope objects into the Where-Objecthttp://go.microsoft.com/fwlink/p/?LinkId=113423 cmdlet.
The Where-Objecthttp://go.microsoft.com/fwlink/p/?LinkId=113423 cmdlet returns the scope objects which are filtered for the state being InActive, or disabled, and pipes the filtered scope objects into this cmdlet, which deletes the disabled scopes passed through the pipeline.

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
Deletes the scope even if active leases exist in the scope.

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

### -ScopeId
Specifies one or more scope identifiers (IDs), in IPv4 address format, to be deleted.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkId=113423)

[Add-DhcpServerv4Scope](./Add-DhcpServerv4Scope.md)

[Get-DhcpServerv4Scope](./Get-DhcpServerv4Scope.md)

[Get-DhcpServerv4ScopeStatistics](./Get-DhcpServerv4ScopeStatistics.md)

[Set-DhcpServerv4Scope](./Set-DhcpServerv4Scope.md)

