---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverv4failoverscope?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-DhcpServerv4FailoverScope

## SYNOPSIS
Removes the specified scopes from the failover relationship.

## SYNTAX

```
Remove-DhcpServerv4FailoverScope [-Name] <String> [-ScopeId] <IPAddress[]> [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Remove-DhcpServerv4FailoverScope** cmdlet removes the specified scopes from the failover relationship.
If any specified scope that is not part of the specified failover relationship or which does not exist, then a non-terminating error will be returned.
This processing will be done before adding the valid scopes to the failover relationship.
This cmdlet also deletes the scopes from the partner Dynamic Host Configuration Protocol (DHCP) server service.
The scopes are retained on the DHCP server service running on the computer specified in the **ComputerName** parameter or the local computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-DhcpServerv4FailoverScope -ComputerName dhcpserver.contoso.com -Name SFO-SIN-Failover -ScopeId 10.10.10.0,20.20.20.0
```

This example removes the scopes 10.10.10.0 and 20.20.20.0 from the failover relationship named SFO-SIN-Failover.
The specified scopes are deleted from the partner DHCP server service of the failover relationship and retained only on the computer named dhcpserver.contoso.com.

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
Removes a scope from a failover relationship even if the partner server is unreachable.

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

### -Name
Specifies the name of one or more failover relationships from which the scopes are to be removed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### -ScopeId
Specifies the scope identifier (ID), in IPv4 address format, which are removed from the failover relationship.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Failover
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Failover
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Failover](./Add-DhcpServerv4Failover.md)

[Add-DhcpServerv4FailoverScope](./Add-DhcpServerv4FailoverScope.md)

[Get-DhcpServerv4Failover](./Get-DhcpServerv4Failover.md)

[Invoke-DhcpServerv4FailoverReplication](./Invoke-DhcpServerv4FailoverReplication.md)

[Remove-DhcpServerv4Failover](./Remove-DhcpServerv4Failover.md)

[Set-DhcpServerv4Failover](./Set-DhcpServerv4Failover.md)

