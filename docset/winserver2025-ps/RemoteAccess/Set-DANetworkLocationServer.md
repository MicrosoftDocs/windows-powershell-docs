---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DANetworkLocationServer_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-danetworklocationserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DANetworkLocationServer
---

# Set-DANetworkLocationServer

## SYNOPSIS
Configures the Network Location Server (NLS).

## SYNTAX

### ExternalServer (Default)
```
Set-DANetworkLocationServer [-Url] <String> [-CheckReachability] [-ComputerName <String>] [-Force] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### OnDAServer
```
Set-DANetworkLocationServer [-ComputerName <String>] [-Force] [-PassThru] [-Certificate <X509Certificate2>]
 [-NlsOnDAServer] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DANetworkLocationServer** cmdlet configures the Network Location Server (NLS).
The NLS can be present on the DirectAccess (DA) server or on some other highly available server

NLS configuration is applicable globally.
It is either present on every DA server or when present on a separate, highly available server it acts as the NLS for all DA clients.
Hence this cmdlet is not impacted by multi-site deployments.

The IIS role and IP and Domain Restrictions role service are required on the DA server if it has to be configured as the NLS.
These roles get automatically installed during Remote Access installation itself.

If the NLS is already configured on the DA server and this cmdlet is used to move it to a different computer, then this cmdlet does not uninstall IIS and IP and Domain Restrictions roles.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DANetworkLocationServer -NlsOnDAServer -PassThru
Certificate NLS cannot be located on the Remote Access server. Do you want DirectAccess to create and use a self-signed certificate?
Confirm

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is ꞌYꞌ): Y

NlsLocation  : DirectAccessServer
Url          :
Reachability :
Certificate  : [Subject]
CN=directaccess-nls.corp.contoso.com
[Issuer]
CN=directaccess-nls.corp.contoso.com
[Serial Number]
6C70EDD2DEAEF2AF46B30823778E0CE2
[Not Before]
11/29/2011 9:45:22 PM
[Not After]
11/29/2016 1:55:22 PM
[Thumbprint]
49D3CE5C1E51F9AA18D4415A8EEA7291DDC4D917
```

This example configures the NLS on the DA server.
This cmdlet first looks for an appropriate certificate on the DA computer itself.
Since it is not able to find one it decides to create a self-signed certificate and prompts the user to accept before going ahead and creating one.

### EXAMPLE 2
```
PS C:\>$a = Get-ChildItem -Path cert:\localmachine\my



PS C:\>$cert = $a | Where-Object -Property Subject -Value CN=edge1.corp.contoso.com -Clike



PS C:\>Set-DANetworkLocationServer -NlsOnDAServer -Certificate $cert
```

This example looks for an appropriate certificate for NLS and manually uses the certificate to configure the NLS on the DA server.

All the certificates will be retrieved from local computer store.
This list will be filtered on the certificate for our DA server edge1 to obtain the SSL certificate required.
This certificate is then passed to this cmdlet to configure NLS.
Since DA NLS configuration is global it will be created on all Client GPOs.

### EXAMPLE 3
```
PS C:\>Set-DANetworkLocationServer -Url https://nsl.corp.contoso.com -CheckReachability -PassThru
Confirm

If the NLS is moved to another computer, then clients without updated GPOs will not be able to connect to the new location. When these clients are located in the internal network they will not be able to connect to internal resources as expected.
PS C:\>
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is ꞌYꞌ): Y

NlsLocation  : ExternalServer
Url          : https://nsl.corp.contoso.com/
Reachability : True
Certificate  :
```

This example configures an external server as the NLS by specifying the URL https://nsl.corp.contoso.com hosted on that server.
Since the NLS is configured on the DA server in the setup this cmdlet will prompt, that the users which do not receive the new policies resulting from this change will not be able to access internal resources when inside the corporate network as they will be detected to be outside the corporate network.
Once the user confirms to the prompt, this cmdlet first checks whether the given URL is reachable and if it is reachable then it sets this URL in the DA configuration.

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

### -Certificate
Specifies the certificate to be used when the NLS is configured to be on the DA server.

```yaml
Type: X509Certificate2
Parameter Sets: OnDAServer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CheckReachability
Performs a reachability check to the specified URL and configures the NLS on that server only if the URL is reachable.

```yaml
Type: SwitchParameter
Parameter Sets: ExternalServer
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

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the DA server computer specific tasks should be run.

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

### -Force
Forces the command to run without asking for user confirmation.

When suppressed the cmdlet assumes user confirmation for the following conditions.

 -- Creation of self-signed certificate when configuring the NLS on the DA server.

 -- Moving the NLS from the DA server to an external server: The corresponding URL on the DA server is decommissioned.
Clients outside corpnet will not receive the updated policies.
When the clients enter corporate network, the URL will be inaccessible and the clients will be detected to be outside corporate network.
As a result the client will not be able to access corporate resources.

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

### -NlsOnDAServer
Specifies that NLS should be configured on the DA Server, that is the server on which the cmdlet is run.

In order for the DA server to act as a NLS an appropriate certificate is required to be installed on the server.
By default the cmdlet looks for a certificate on the server.
In case of multi-site, load balancing configuration, or multi-site and load balancing configuration the certificate has to be present on all of the servers.

If a certificate is not found, then a self-signed certificate is created for this purpose.
Before creating the self-signed certificate the cmdlet asks for user confirmation.
If the user wishes to specify a certificate explicitly, then the **Certificate** parameter can be used.

```yaml
Type: SwitchParameter
Parameter Sets: OnDAServer
Aliases:

Required: True
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

### -Url
Specifies the URL of a website hosted on a highly available external server which is used as the NLS that provides clients with location information.

```yaml
Type: String
Parameter Sets: ExternalServer
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.Security.Cryptography.X509Certificates.X509Certificate2

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DANetworkLocationServer

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DANetworkLocationServer object consists of the following properties:

 -- If the NLS is configured on the DA server or on a different server.

 -- The URL used for detecting whether a remote computer is inside or outside the corporate network (if NLS is configured on a different server).

 -- The certificate used for NLS (if it is configured on the DA server).

 -- Reachability of the NLS (if on a different server).

## NOTES

## RELATED LINKS

[Get-ChildItem](https://go.microsoft.com/fwlink/?LinkId=204557)

[Where-Object](https://go.microsoft.com/fwlink/?LinkId=113423)

[Get-DANetworkLocationServer](./Get-DANetworkLocationServer.md)

