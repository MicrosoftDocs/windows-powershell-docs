---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4failover?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DhcpServerv4Failover

## SYNOPSIS
Gets the failover relationships configured on the Dynamic Host Configuration Protocol (DHCP) server service for the specific failover relationship name.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-DhcpServerv4Failover [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-DhcpServerv4Failover [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-ThrottleLimit <Int32>] -ScopeId <IPAddress[]>
```

## DESCRIPTION
The **Get-DhcpServerv4Failover** cmdlet gets the failover relationships configured on the Dynamic Host Configuration Protocol (DHCP) server service for the specific failover relationship name.
If the **Name** parameter is not specified, then this cmdlet returns all failover relationships defined on the DHCP server service.
If the **Name** parameter does not match a failover relationship, then a non-terminating error will be returned for the specific **Name** parameter value.

If the **ScopeId** parameter is specified, then the failover relationships of which the specified scopes are included are returned.
The **ScopeId** parameter values should be failover scopes.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DhcpServerv4Failover -ComputerName dhcpserver.contoso.com -Name SFO-SIN-Failover
```

This example gets the failover relationship information for relationship named SFO-SIN-Failover on the DHCP server service running on the computer named dhcpserver.contoso.com.

### EXAMPLE 2
```
PS C:\> Get-DhcpServerv4Failover -ComputerName dhcpserver.contoso.com
```

This example gets the failover relationship information for all of the failover relationships on the DHCP server service running on the computer named dhcpserver.contoso.com.

### EXAMPLE 3
```
PS C:\> Get-DhcpServerv4Failover -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0
```

This example gets the failover relationship information for the failover relationship of which the scope 10.10.10.0 is a part, on the DHCP server service running on the computer named dhcpserver.contoso.com.

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

### -Name
Specifies one or more names of failover relationships for which the properties are returned.

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

### -ScopeId
Specifies one or more scope identifiers (IDs), in IPv4 address format.
The properties of the failover relationships on the DHCP server service to which these scopes are associated are returned.

```yaml
Type: IPAddress[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Failover[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Failover](./Add-DhcpServerv4Failover.md)

[Add-DhcpServerv4FailoverScope](./Add-DhcpServerv4FailoverScope.md)

[Invoke-DhcpServerv4FailoverReplication](./Invoke-DhcpServerv4FailoverReplication.md)

[Remove-DhcpServerv4Failover](./Remove-DhcpServerv4Failover.md)

[Remove-DhcpServerv4FailoverScope](./Remove-DhcpServerv4FailoverScope.md)

[Set-DhcpServerv4Failover](./Set-DhcpServerv4Failover.md)

