---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAEntryPoint_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-daentrypoint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DAEntryPoint
---

# Add-DAEntryPoint

## SYNOPSIS
Adds an entry point to a multi-site deployment.

## SYNTAX

```
Add-DAEntryPoint [-ComputerName <String>] [-ServerGpoName <String>] [-Name] <String> [-GslbIP <IPAddress>]
 [-DeployNat] [-NoPrerequisite] [-PassThru] -RemoteAccessServer <String> [-InternalInterface <String>]
 [-InternetInterface <String>] [-ClientIPv6Prefix <String>] -ConnectToAddress <String> [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DAEntrypoint** cmdlet adds an entry point to a multi-site deployment.
This cmdlet checks that the server complies with the prerequisites for DirectAccess deployment, and adds the server as an entry point.

## EXAMPLES

### Example 1
```
PS C:\>Add-DAEntryPoint -Name "Entry Point 2" -InternalInterface CorpNet1 -RemoteAccessServer "da2.domain1.corp.contoso.com" -InternetInterface Internet -ClientIPv6Prefix 3000:0:30:2000::/64 -ConnectToAddress "ep2.da.contoso.com" -PassThru -Force

EntryPointName                 GslbIp                         Servers
--------------                 ------                         -------
Entry Point 2                  0.0.0.0                        {DA2.domain1.corp.contoso.com}


To validate the name of the GPO which was created by this cmdlet, the following script should be used.
PS C:\>$daServer = Get-DAServer -EntrypointName "Entry Point 2"



PS C:\>$daServer.ServerConfiguration.GpoName

domain1.corp.contoso.com\DirectAccess Server Settings - Entry Point 2


In addition, running the Get-DAMultiSite cmdlet displays the newly added entry point.
PS C:\>Get-DAMultiSite

EnterpriseName             : Company Enterprise
GslbFqdn                   :
ManualSiteSelectionAllowed : Enabled
DAEntryPoints              : {Entry Point 1, Entry Point 2}
```

This example adds the edge server named da2.domain1.corp.contoso.com to the multi-site deployment, names the server Entry Point 2 and declares CorpNet1 as the network interface which is connected to the corporate internal network.
Since the company uses IPv6 prefixes, IPHTTPS remote clients will connect via ep2.da.contoso.com using predefined prefix 3000:0:30:2000::/64.

### Example 2
```
PS C:\>Add-DAEntryPoint -Name "Entry Point 2" -InternalInterface CorpNet1 -RemoteAccessServer "da2.domain1.corp.contoso.com" -InternetInterface Internet -ClientIPv6Prefix 3000:0:30:2000::/64 -ConnectToAddress "ep2.da.contoso.com" -ServerGpoName "domain1.corp.contoso.com\EP2ServerGpo"  -PassThru -Force

EntryPointName                 GslbIp                         Servers
--------------                 ------                         -------
Entry Point 2                  0.0.0.0                        {DA2.domain1.corp.contoso.com}


To validate, the following script should be used.
PS C:\>$daServer = Get-DAServer -EntrypointName "Entry Point 2"



PS C:\>$daServer.ServerConfiguration.GpoName

domain1.corp.contoso.com\ EP2ServerGpo
```

This example adds the edge server named da2.domain1.corp.contoso.com to the multi-site deployment, names the server Entry Point 2 and declares CorpNet1 as the network interface which is connected to the corporate internal network using a pre-created GPO domain2.corp.contoso.com\EP2ServerGpo.

### Example 3
```
PS C:\>Add-DAEntryPoint -Name "Entry Point 2" -InternalInterface CorpNet1 -RemoteAccessServer "da2.domain1.corp.contoso.com" -InternetInterface Internet -ClientIPv6Prefix 3000:0:30:2000::/64 -ConnectToAddress "ep2dmz.da.contoso.com" -ServerGpoName "domain1.corp.contoso.com\EP2ServerGpo" -PassThru -Force

EntryPointName                 GslbIp                         Servers
--------------                 ------                         -------
Entry Point 2                  0.0.0.0                        {da2.domain1.corp.contoso.com}
```

This example adds the edge server named da2.domain1.corp.contoso.com to the multi-site deployment, names the server Entry Point 2 and declares CorpNet1 as the network interface which is connected to the corporate internal network behind the NAT named DeployNat , with a defined internet interface named DMZNet1 and directs clients to connect to the entry point through ep2dmz.da.contoso.com.

### Example 4
```
PS C:\>Add-DAEntryPoint -Name "Entry Point 2" -InternalInterface CorpNet1 -RemoteAccessServer "da2.domain1.corp.contoso.com" -InternetInterface Internet -ClientIPv6Prefix 3000:0:30:2000::/64 -ConnectToAddress "ep2.da.contoso.com" -GslbIP "137.5.0.50" -PassThru -Force

EntryPointName                 GslbIp                         Servers
--------------                 ------                         -------
Entry Point 2                  137.5.0.50                     {da2.domain1.corp.contoso.com}
```

This example adds the edge server named da2.domain1.corp.contoso.com to the multi-site deployment, names the server Entry Point 2 and declares CorpNet1 as the network interface which is connected to the corporate internal network using GSLB and the IP address for Entry Point 2 is 137.5.0.50.

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

### -ClientIPv6Prefix
Specifies the IPv6 address prefix assigned to remote clients connecting over IP-HTTPS.
The prefix length must be `59` or `64` bits.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies the name or address, either IPv4 or IPv6, of a server or server cluster in the multi-site deployment.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectToAddress
Specifies the public name, or IPv4 address, of the Remote Access server, or network address translation (NAT) server, to which remote clients connect.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeployNat
Indicates that the server or server cluster is deployed behind a NAT device.

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

### -GslbIP
Specifies the IPv4 or IPv6 dedicated IP address (DIP) of the server, or the virtual IP address (VIP) of the server cluster, to be used for global load balancing.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternalInterface
Specifies the name of the internal network adapter of the first server in the entry point.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InternetInterface
Specifies the name of the external network adapter of the first server in the entry point.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name to be assigned to the entry point.

```yaml
Type: String
Parameter Sets: (All)
Aliases: EntryPointName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoPrerequisite
Indicates that a prerequisite check for DirectAccess deployment requirements should not be performed.

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

### -RemoteAccessServer
Specifies the name or IP address, IPv4 or IPv6, of the server that will be the first server in the entry point.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerGpoName
Specifies the name of the GPO in which DirectAccess server configuration settings for the entry point are stored.
The GPO is created in the domain that contains the server specified in RemoteAccessServer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Net.IPAddress

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAEntryPoint
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DAEntryPoint](./Get-DAEntryPoint.md)

[Remove-DAEntryPoint](./Remove-DAEntryPoint.md)

[Set-DAEntryPoint](./Set-DAEntryPoint.md)

