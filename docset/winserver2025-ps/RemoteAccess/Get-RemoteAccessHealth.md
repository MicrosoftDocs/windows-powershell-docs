---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessHealth_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-remoteaccesshealth?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RemoteAccessHealth
---

# Get-RemoteAccessHealth

## SYNOPSIS
Obtains the current health of a RemoteAccess (RA) deployment.

## SYNTAX

### Cluster (Default)
```
Get-RemoteAccessHealth [-Cluster] [-ComputerName <String>] [-Refresh] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### EntrypointName
```
Get-RemoteAccessHealth [-ComputerName <String>] [-Refresh] -EntrypointName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RemoteAccessHealth** cmdlet obtains the current health of a RemoteAccess (RA) deployment as follows.

 -- Health of a specific Remote Access server.

 -- Health of a load balancing cluster.

 -- Health of a site, in case of a multi-site deployment: this again corresponds to the health of a single server or health of a cluster at that site.

The health information returned for a single server consists of the following.

 -- Server address.

 -- Rolled up health of the server: This depends on the health of the individual technology features that RA is comprised.
The following rule applies: If all features are healthy, then the server is healthy.
If one or more features are in the yellow health state, then the health of the server is also yellow.
If one or more features are in the red health state, then the health of the server is also red; this applies even if one or more features are in yellow health state.

 -- Time stamp when the health of the server changed.

 -- Health of the individual RA features.
This comprises of the following.

 ---- Health state of a feature: The roll-up of the health of individual pre-defined monitors that determine the health of the feature.
Every monitor causes the feature to go into red or yellow health.
If multiple monitors are unhealthy, then the roll-up rules are similar to the one for server health roll-up defined above.

 ---- Time stamp when the health of the feature last changed.

 ---- If a DA feature is not healthy, then the details of the monitors that are unhealthy.

The health information returned for a cluster is quite similar to the server health and consists of the following.

 -- Rolled up health of cluster: This depends on the health of each of the servers present in the cluster.
The roll-up rules are similar to the feature health roll-up for server.

 -- Time stamp when health of the cluster changed.

 -- Health of the individual servers in the cluster: The health information described above is returned for each of the servers.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-RemoteAccessHealth
Component            RemoteAccessServer   HealthState     TimeStamp            Id              OperationStatus
---------            ------------------   -----------     ---------            --              ---------------
Server               localhost            Error           2/1/2012 1:59:32 AM
6to4                 localhost            OK              2/1/2012 1:59:20 AM
Vpn Addressing       localhost            OK              2/1/2012 1:59:20 AM
Network Security     localhost            OK              2/1/2012 1:59:20 AM
Dns                  localhost            OK              2/1/2012 2:04:10 AM
IP-Https             localhost            OK              2/1/2012 1:59:20 AM
Nat64                localhost            OK              2/1/2012 1:59:19 AM
Dns64                localhost            OK              2/1/2012 1:59:16 AM
IPsec                localhost            OK              2/1/2012 1:59:16 AM
Kerberos             localhost            Disabled        2/1/2012 1:59:16 AM
Domain Controller    localhost            OK              2/1/2012 2:04:10 AM
Management Servers   localhost            Disabled        2/1/2012 1:59:13 AM
Network Location ... localhost            OK              2/1/2012 2:04:11 AM
Otp                  localhost            Disabled        2/1/2012 1:59:13 AM
High Availability    localhost            Error           2/1/2012 1:59:32 AM  {2148401155,... {NLB state, NLB drive...
Isatap               localhost            Disabled        2/1/2012 1:59:13 AM
Vpn Connectivity     localhost            OK              2/1/2012 1:59:13 AM
Teredo               localhost            Disabled        2/1/2012 1:59:13 AM
Network Adapters     localhost            OK              2/1/2012 1:59:13 AM
Services             localhost            Unknown         2/1/2012 2:04:10 AM  3221225474      Server configuration ...
```

This example displays the health of a specific server.

### EXAMPLE 2
```
PS C:\>Get-RemoteAccessHealth -Cluster
Component            RemoteAccessServer   HealthState     TimeStamp            Id              OperationStatus
---------            ------------------   -----------     ---------            --              ---------------
Cluster                                   Error           2/1/2012 1:59:32 AM
Server               N1.CONTOSO.COM       Error           2/1/2012 1:59:32 AM
6to4                 N1.CONTOSO.COM       OK              2/1/2012 1:59:20 AM
Vpn Addressing       N1.CONTOSO.COM       OK              2/1/2012 1:59:20 AM
Network Security     N1.CONTOSO.COM       OK              2/1/2012 1:59:20 AM
Dns                  N1.CONTOSO.COM       OK              2/1/2012 2:04:10 AM
IP-Https             N1.CONTOSO.COM       OK              2/1/2012 1:59:20 AM
Nat64                N1.CONTOSO.COM       OK              2/1/2012 1:59:19 AM
Dns64                N1.CONTOSO.COM       OK              2/1/2012 1:59:16 AM
IPsec                N1.CONTOSO.COM       OK              2/1/2012 1:59:16 AM
Kerberos             N1.CONTOSO.COM       Disabled        2/1/2012 1:59:16 AM
Domain Controller    N1.CONTOSO.COM       OK              2/1/2012 2:04:10 AM
Management Servers   N1.CONTOSO.COM       Disabled        2/1/2012 1:59:13 AM
Network Location ... N1.CONTOSO.COM       OK              2/1/2012 2:04:11 AM
Otp                  N1.CONTOSO.COM       Disabled        2/1/2012 1:59:13 AM
High Availability    N1.CONTOSO.COM       Error           2/1/2012 1:59:32 AM  {2148401155,... {NLB state, NLB drive...
Isatap               N1.CONTOSO.COM       Disabled        2/1/2012 1:59:13 AM
Vpn Connectivity     N1.CONTOSO.COM       OK              2/1/2012 1:59:13 AM
Teredo               N1.CONTOSO.COM       Disabled        2/1/2012 1:59:13 AM
Network Adapters     N1.CONTOSO.COM       OK              2/1/2012 1:59:13 AM
Services             N1.CONTOSO.COM       Unknown         2/1/2012 2:04:10 AM  3221225474      Server configuration ...
Server               N2.CONTOSO.COM       OK              2/1/2012 5:48:35 AM
6to4                 N2.CONTOSO.COM       OK              2/1/2012 5:43:39 AM
Vpn Addressing       N2.CONTOSO.COM       OK              2/1/2012 5:43:39 AM
Network Security     N2.CONTOSO.COM       OK              2/1/2012 5:43:39 AM
Dns                  N2.CONTOSO.COM       OK              2/1/2012 5:48:35 AM
IP-Https             N2.CONTOSO.COM       OK              2/1/2012 5:43:39 AM
Nat64                N2.CONTOSO.COM       OK              2/1/2012 5:43:39 AM
Dns64                N2.CONTOSO.COM       OK              2/1/2012 5:43:38 AM
IPsec                N2.CONTOSO.COM       OK              2/1/2012 5:43:38 AM
Kerberos             N2.CONTOSO.COM       Disabled        2/1/2012 5:43:38 AM
Domain Controller    N2.CONTOSO.COM       OK              2/1/2012 5:43:38 AM
Management Servers   N2.CONTOSO.COM       Disabled        2/1/2012 5:43:35 AM
Network Location ... N2.CONTOSO.COM       OK              2/1/2012 5:48:35 AM
Otp                  N2.CONTOSO.COM       Disabled        2/1/2012 5:43:35 AM
High Availability    N2.CONTOSO.COM       OK              2/1/2012 5:48:35 AM
Isatap               N2.CONTOSO.COM       Disabled        2/1/2012 5:43:35 AM
Vpn Connectivity     N2.CONTOSO.COM       OK              2/1/2012 5:43:35 AM
Teredo               N2.CONTOSO.COM       Disabled        2/1/2012 5:43:35 AM
Network Adapters     N2.CONTOSO.COM       OK              2/1/2012 5:43:35 AM
Services             N2.CONTOSO.COM       OK              2/1/2012 5:48:35 AM
```

This example displays the health of a cluster containing two Remote Access servers.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -Cluster
Indicates that the cmdlet gets the health for the entire cluster.
If you specify both this parameter and the **ComputerName** parameter, the cmdlet gets the health of the cluster to which the computer belongs.
If you specify this parameter in a multisite scenario, the cmdlet gets the health of the cluster in the site for the server on which you run the cmdlet.
You can use the **ComputerName** parameter to specify the computer that runs the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Indicates the IPv4 or IPv6 address, or host name, of the computer on which this cmdlet needs to be run and the health retrieved.
When this parameter is specified, then the health of that RA server is returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntrypointName
Specifies the identity of a site in a multi-site deployment whose health needs to be retrieved.

If both this parameter and **ComputerName** parameter are specified and the computer name does not belong to the site represented by the entry point name, then this parameter takes precedence and the site health is retrieved.

```yaml
Type: String
Parameter Sets: EntrypointName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Refresh
Indicates that the cmdlet recomputes the health details for the computer, cluster, or entry point that you specify for the cmdlet.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessHealthMonitor

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The array of RemoteAccessHealthMonitor objects consists of the following properties for cluster, server and components of the server:

 -- Component name

 -- Remote Access server address

 -- HealthState

 -- TimeStamp

 -- OperationStatus

 -- ID

 -- ErrorDesc

 -- ErrorCause

 -- ErrorResoln

## NOTES

## RELATED LINKS

[Get-DAServer](./Get-DAServer.md)

[Get-RemoteAccess](./Get-RemoteAccess.md)

