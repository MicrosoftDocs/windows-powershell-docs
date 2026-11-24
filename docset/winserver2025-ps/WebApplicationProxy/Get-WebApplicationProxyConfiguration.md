---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: WebApplicationProxy-help.xml
Module Name: WebApplicationProxy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/webapplicationproxy/get-webapplicationproxyconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebApplicationProxyConfiguration
---

# Get-WebApplicationProxyConfiguration

## SYNOPSIS
Retrieves global Web Application Proxy settings.

## SYNTAX

```
Get-WebApplicationProxyConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebApplicationProxyConfiguration** cmdlet retrieves the Web Application Proxy settings that are not specific to any published application.
To modify the settings, use the Set-WebApplicationProxyConfiguration cmdlet.

## EXAMPLES

### Example 1: Retrieve the Web Application Proxy settings
```
PS C:\>Get-WebApplicationProxyConfiguration

ADFSSignOutUrl                         : https://sts.contoso.com/adfs/ls/?wa=wsignout1.0
ADFSTokenAcceptanceDurationSec         : 120
ADFSTokenSigningCertificatePublicKey   : Automatically Updated
ADFSUrl                                : https://sts.contoso.com/adfs/ls
ADFSWebApplicationProxyRelyingPartyUri : urn:AppProxy:com
ConfigurationChangesPollingIntervalSec : 30
ConfigurationVersion                   : Windows Server 2016
ConnectedServersName                   : {WAP-server1.corp.contoso.com, WAP-server2.corp.contoso.com}
OAuthAuthenticationURL                 : https://sts.contoso.com/adfs/oauth2/authorize
UserIdleTimeoutAction                  : Signout
UserIdleTimeoutSec                     : 0
```

This command retrieves the Web Application Proxy settings.

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#AppProxyGlobalConfiguration

Displays the Web Application Proxy configuration.

## NOTES

## RELATED LINKS

[Web Application Proxy overview](https://technet.microsoft.com/library/dn280944.aspx)

[Publishing Internal Applications using Web Application](https://technet.microsoft.com/library/dn383650.aspx)

[Set-WebApplicationProxyConfiguration](./Set-WebApplicationProxyConfiguration.md)

