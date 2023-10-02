---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://learn.microsoft.com/powershell/module/dhcpserver/get-dhcpserverv4policyiprange?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DhcpServerv4PolicyIPRange

## SYNOPSIS
Gets one or more IP ranges from a policy in the specified scope.

## SYNTAX

```
Get-DhcpServerv4PolicyIPRange [-ScopeId] <IPAddress> [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DhcpServerv4PolicyIPRange** cmdlet gets one or more IP ranges from a policy in the specified scope.
If the **Name** parameter is not specified, then this cmdlet gets the IP ranges for all policies in the specified scope.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerv4PolicyIPRange -ScopeId 10.10.10.0 -Name HyperVPolicy
```

This example gets the IP address ranges associated with policy named HyperVPolicy that is defined inside the scope 10.10.10.0.

### EXAMPLE 2
```
PS C:\>Get-DhcpServerv4PolicyIPRange -ScopeId 10.10.10.0
```

This example gets all of the IP address ranges associated with any policy defined inside the scope 10.10.10.0.

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

### -Name
Specifies the name of the policy for which the associated IP ranges are to be returned.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScopeId
Specifies the scope identifier, in IPv4 address format, which contains the specified policy.

```yaml
Type: IPAddress
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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Policy
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Scope
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4PolicyIPRange[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4PolicyIPRange](./Add-DhcpServerv4PolicyIPRange.md)

[Remove-DhcpServerv4PolicyIPRange](./Remove-DhcpServerv4PolicyIPRange.md)

