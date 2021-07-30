---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/hcs/set-hcswebproxy?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HcsWebProxy
---

# Set-HcsWebProxy

## SYNOPSIS
Sets the web proxy configuration.

## SYNTAX

```
Set-HcsWebProxy [-ConnectionURI] <String> [-Authentication] <WebProxyAuthType> [-Username <String>]
 [-Password <SecureString>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HcsWebProxy** cmdlet sets the web proxy configuration for this device.
After you set the configuration, you must enable the web proxy by using the Enable-HcsWebProxy cmdlet.

## EXAMPLES

### Example 1: Configure a web proxy
```
PS C:\> Set-HcsWebProxy -Authentication None -ConnectionURI "https://myproxy:8080"
ConnectionURI                                Authentication Username                                          IsEnabled
-------------                                -------------- --------                                          ---------
https://myproxy:8080                                    None                                                       False
```

This command configures the web proxy that has the URI https://myproxy:8080.
The proxy uses no authentication.

### Example 2: Configure a web proxy with NTLM authentication
```
PS C:\> Set-HcsWebProxy -Authentication NTLM -ConnectionURI "https://myproxy:8080" -Username "ENarvaez"
WARNING: A script or application on the remote computer 10.122.103.105 is sending a prompt request. When you are
prompted, enter sensitive information, such as credentials or passwords, only if you trust the remote computer and the
application or script that is requesting the data.
Password: ****
WARNING: A script or application on the remote computer 10.122.103.105 is sending a prompt request. When you are
prompted, enter sensitive information, such as credentials or passwords, only if you trust the remote computer and the
application or script that is requesting the data.
Confirm Password: ****

ConnectionURI                                Authentication Username                                          IsEnabled
-------------                                -------------- --------                                          ---------
https://myproxy:8080                                    NTLM ENarvaez                                              False
```

This command configures the web proxy to use NTLM authentication for user named ENarvaez.

### Example 3: Configure a web proxy with Basic authentication
```
PS C:\> Set-HcsWebProxy -Authentication Basic -ConnectionURI "https://myproxy:8080" -Password $Null -Username "ENarvaez" 
ConnectionURI                                Authentication Username                                          IsEnabled
-------------                                -------------- --------                                          ---------
https://myproxy:8080                                   Basic ENarvaez                                              False
```

This command configures the web proxy to use Basic authentication with no password.

## PARAMETERS

### -Authentication
Specifies the type of authentication to use.
The acceptable values for this parameter are:

- None
- Basic
- NTLM

```yaml
Type: WebProxyAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: None, Basic, NTLM

Required: True
Position: 2
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

### -ConnectionURI
Specifies the URI for the web proxy server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### -Password
Specifies a password.
Specify a secure string for this parameter.
The cmdlet uses this password to connect to the web proxy.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Username
Specifies a user name for the web proxy.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Platform.Support.WebProxyInfo
The WebProxyInfo object has the following properties:

- String ConnectionURI 
- WebProxyAuthType Authentication 
- String Username 
- IsEnabled

## NOTES

## RELATED LINKS

[Disable-HcsWebProxy](./Disable-HcsWebProxy.md)

[Enable-HcsWebProxy](./Enable-HcsWebProxy.md)

[Get-HcsWebProxy](./Get-HcsWebProxy.md)

