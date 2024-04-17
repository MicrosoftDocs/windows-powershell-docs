---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAClient_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-daclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DAClient
---

# Set-DAClient

## SYNOPSIS
Configures the properties related to a DirectAccess (DA) client.

## SYNTAX

```
Set-DAClient [-ComputerName <String>] [-ForceTunnel <String>] [-OnlyRemoteComputers <String>]
 [-Downlevel <String>] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DAClient** cmdlet configures the properties related to a DirectAccess (DA) client.

The DA client properties consist of the following.

 -- Force tunneling.

 -- Support for down-level clients.

 -- Support for remote computers only.

The DA client configuration is a global configuration and is applicable to all of the client computers in the DA deployment.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-DAClient -ForceTunnel "Enabled" -OnlyRemoteComputers "Enabled" -PassThru
OnlyRemoteComputers   : Enabled
Downlevel    : Disabled
ForceTunnelingStatus  : Enabled
ForceTunnelingNrptSuffix  : .
```

This example configures DA only for remote laptops and computers and mandatorily route traffic through the corporate network.
A default Name Resolution Policy Table (NRPT) entry is added to indicate that all traffic to any suffix should be sent to the corporate network.
This is a global setting and will be applied across clients.

### EXAMPLE 2
```
PS C:\>$certs = Get-ChildItem -Path Cert:\LocalMachine\Root



PS C:\>$IPSecRootCert = $certs[13]



PS C:\>Set-DAServer -IPSecRootCertificate $IPSecRootCert -UserAuthentication TwoFactor



PS C:\>Set-DAClient -Downlevel "Enabled"
OnlyRemoteComputers   : Enabled
Downlevel    : Enabled
ForceTunnelingStatus  : Enabled
ForceTunnelingNrptSuffix  : .
```

This example enables Windows® 7 clients to connect to the corporate networking over DA.
There are multiple steps involved in achieving this configuration.
By default PKI is disabled during DA installation and it needs to be enabled.
This is achieved by provisioning an IPsec root certificate on the DA server using the Set-DAServer cmdlet.
The enterprise needs to have a certification authority (CA) which will provision this certificate for all domain joint computers.
The first two steps list out the certificates present in the root certificate store of the server computer and pick an appropriate one.
In this case it happens to be the 13th certificate in the list.
This certificate is then assigned as the IPsec root certificate to enable PKI.
Once this is done the Down-level parameter in this cmdlet is set to Enabled to enable DA for Windows® 7 clients.
This causes appropriate policies to be configured on Windows® 7 computer only.

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

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.

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

### -Downlevel
Specifies that the appropriate policies should be deployed on down-level clients (firstref_client_7) clients for allowing connection to a Windows Server® 2012 DA server.
The acceptable values for this parameter are: Enabled or Disabled.

This parameter can be configured only when multi-site is not deployed.
If a user tries to configure it in a multi-site deployment, then this cmdlet displays an error.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ForceTunnel
Specifies that force tunneling should be enabled or disabled.
The acceptable values for this parameter are: Enabled or Disabled.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OnlyRemoteComputers
Allows a user to enable or disable deployment of DA only on remote computers such as laptops and notebooks.
The acceptable values for this parameter are: Enabled or Disabled.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAClientSettings

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAClientSettings object contains the following properties:

 -- The status of force tunneling.

 -- The NRPT object (for force tunnel properties).

 -- The status of the policy to deploy DA only on laptops and notebooks and not on all computers in the domain.

 -- The status of whether appropriate policies should be deployed on down-level clients (Windows® 7) to enable them to connect to the Windows Server 2012 DA server.

## NOTES

## RELATED LINKS

[Get-ChildItem](https://go.microsoft.com/fwlink/p/?LinkId=204557)

[Add-DAClient](./Add-DAClient.md)

[Get-DAClient](./Get-DAClient.md)

[Remove-DAClient](./Remove-DAClient.md)

[Set-DAServer](./Set-DAServer.md)

