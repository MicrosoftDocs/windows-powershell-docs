---
external help file: UnifiedRA_Cmdlets.xml
Module Name: RemoteAccess
online version: https://docs.microsoft.com/powershell/module/remoteaccess/set-vpnauthprotocol?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VpnAuthProtocol

## SYNOPSIS
Sets the authentication method for incoming site-to-site (S2S) VPN interfaces on a Routing and Remote Access (RRAS) server.

## SYNTAX

```
Set-VpnAuthProtocol [-AsJob] [-CertificateAdvertised <X509Certificate2>] [-CimSession <CimSession[]>]
 [-PassThru] [-RootCertificateNameToAccept <X509Certificate2>] [-SharedSecret <String>]
 [-ThrottleLimit <Int32>] [-TunnelAuthProtocolsAdvertised <String>] [-UserAuthProtocolAccepted <String[]>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-VpnAuthProtocol** cmdlet configures how the incoming site-to-site (S2S) VPN Interfaces on a Routing and Remote Access (RRAS) server are authenticated, such as when the server is a responder for incoming connections whose authentication method is EAP or computer certificates (machine certificates).

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-VpnAuthProtocol -UserAuthProtocolAccepted Certificate -PassThru
WARNING: Configuration parameters will be modified after the Remote Access service is restarted. 
 
UserAuthProtocolAccepted      : {Certificate} 
TunnelAuthProtocolsAdvertised : Certificates 
RootCertificateNameToAccept   : 
CertificateAdvertised         :
```

This example changes the authentication method used by the server for incoming connections to Certificate and advertises certificates as authentication mechanism to the peer computers.

### EXAMPLE 2
```
PS C:\>$cert1 = ( Get-ChildItem -Path cert:LocalMachine\root | Where-Object -FilterScript { $_.Subject -Like "*CN=Contoso Root Certification Authority,*" } )




PS C:\>Set-VpnAuthProtocol -RootCertificateNameToAccept $cert1 -PassThru
```

This example sets the root certificate against which all of the incoming connections computer certificates are matched.

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

### -CertificateAdvertised
Specifies the certificate to be sent to a peer computer.
Applicable only if the **TunnelAuthProtocolsAdvertised** parameter is set to Certificate.

```yaml
Type: X509Certificate2
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

### -RootCertificateNameToAccept
Specifies the root certificates that are allowed.
Applicable only if the **UserAuthProtocolAccepted** parameter contains certificates.

```yaml
Type: X509Certificate2
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharedSecret
Specifies the text of the shared secret for the connection.
Applicable only if the **TunnelAuthProtocolsAdvertised** parameter is set to PSK.

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

### -TunnelAuthProtocolsAdvertised
Specifies the remote authentication method used by the RRAS server.
If this parameter value is set to pre-shared key (PSK), then the **SharedSecret** parameter is mandatory.
If this parameter value is set to Certificate, then the **CertificateAdvertised** parameter is mandatory.
Only one of the values can be specified.

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

### -UserAuthProtocolAccepted
Specifies the local authentication protocols that are allowed.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnAuthProtocol
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-VpnS2SInterface](./Add-VpnS2SInterface.md)

[Clear-VpnS2SInterfaceStatistics](./Clear-VpnS2SInterfaceStatistics.md)

[Connect-VpnS2SInterface](./Connect-VpnS2SInterface.md)

[Disconnect-VpnS2SInterface](./Disconnect-VpnS2SInterface.md)

[Get-VpnAuthProtocol](./Get-VpnAuthProtocol.md)

[Get-VpnS2SInterface](./Get-VpnS2SInterface.md)

[Get-VpnS2SInterfaceStatistics](./Get-VpnS2SInterfaceStatistics.md)

[Get-VpnServerIPsecConfiguration](./Get-VpnServerIPsecConfiguration.md)

[Remove-VpnS2SInterface](./Remove-VpnS2SInterface.md)

[Set-VpnS2SInterface](./Set-VpnS2SInterface.md)

[Set-VpnServerIPsecConfiguration](./Set-VpnServerIPsecConfiguration.md)

