---
author: Kateyanne
external help file: DhcpServer_Cmdlets.xml
manager: dansimp
Module Name: DhcpServer
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dhcpserver/invoke-dhcpserverv4failoverreplication?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Invoke-DhcpServerv4FailoverReplication

## SYNOPSIS
Replicates scope configuration between failover partner Dynamic Host Configuration Protocol (DHCP) server services.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Invoke-DhcpServerv4FailoverReplication [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-Force] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Invoke-DhcpServerv4FailoverReplication [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-Force]
 [-ThrottleLimit <Int32>] -ScopeId <IPAddress[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Invoke-DhcpServerv4FailoverReplication** cmdlet replicates scope configuration between failover partner Dynamic Host Configuration Protocol (DHCP) server services.

If the **ScopeId** parameter is specified, then, if the scope is part of a failover relationship, the scope configuration for the specified scopes is replicated to the failover partner DHCP server service.
The scope configuration includes all scope properties, reservations, scope option values, and policies.

If the **Name** parameter is specified, then the configuration for all of the scopes which are part of the failover relationship is replicated to the partner DHCP server service.
If no parameters are specified, then the configuration for all of the failover scopes on the DHCP server service will be replicated to the respective partner DHCP server services.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Invoke-DhcpServerv4FailoverReplication -ComputerName dhcpserver.contoso.com -Name SFO-SIN-Failover
```

This example replicates the configuration of all scopes which are part of the failover relationship named SFO-SIN-Failover on the DHCP server service running on the computer named dhcpserver.contoso.com to the partner DHCP server service.

### EXAMPLE 2
```
PS C:\>Invoke-DhcpServerv4FailoverReplication -ComputerName dhcpserver.contoso.com
```

This example replicates all of the failover scopes on the DHCP server service running on the computer named dhcpserver.contoso.com to one or more respective partner DHCP server services based on one or more failover relationships in which the DHCP server services are included.

### EXAMPLE 3
```
PS C:\>Invoke-DhcpServerv4FailoverReplication -ComputerName dhcpserver.contoso.com -ScopeId 10.10.10.0,20.20.20.0
```

This example replicates the configuration of the scopes 10.10.10.0 and 20.20.20.0 to the respective partner computers running the DHCP server services of the failover relationships in which the scopes are included.

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
Forces the command to run without asking for user confirmation.

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
Specifies the name of the failover relationship.
All scopes for one or more specified relationships are replicated to the partner DHCP server service.

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
Specifies the scope identifier (ID), in IPv4 address format, whose configuration needs to be replicated.

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

### System.String[]

## NOTES

## RELATED LINKS

[Add-DhcpServerv4Failover](./Add-DhcpServerv4Failover.md)

[Add-DhcpServerv4FailoverScope](./Add-DhcpServerv4FailoverScope.md)

[Get-DhcpServerv4Failover](./Get-DhcpServerv4Failover.md)

[Remove-DhcpServerv4Failover](./Remove-DhcpServerv4Failover.md)

[Remove-DhcpServerv4FailoverScope](./Remove-DhcpServerv4FailoverScope.md)

[Set-DhcpServerv4Failover](./Set-DhcpServerv4Failover.md)

