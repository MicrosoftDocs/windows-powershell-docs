---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssdomainnameconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WssDomainNameConfiguration

## SYNOPSIS
Changes the domain name configuration of the server.

## SYNTAX

```
Set-WssDomainNameConfiguration [-DomainName] <String> [-CertificatePath] <String>
 [[-CertificateFilePassword] <SecureString>] [-NoCertificateVerification]
```

## DESCRIPTION
The **Set-WssDomainNameConfiguration** cmdlet changes the domain name configuration settings of the server.
You can use this cmdlet to change the domain name of the server and configure the Secure Sockets Layer (SSL) certificate binding to the Web Server, terminal server, and virtual private network (VPN) server.

## EXAMPLES

### Example 1: Change the domain name configuration of the server
```
PS C:\>$SecureString_pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force PS C:\> Set-WssDomainNameConfiguration -CertificateFilePassword $SecureString_pwd -CertificatePath "c:\cert.pfx" -DomainName "Contoso.com" -NoCertificateVerification
```

The first command converts the plain text string "P@ssW0rD!" into a secure string and stores the result in the **$SecureString_pwd** variable.

The second command specifies the domain name of the server, sets the password stored in the **$SecureString_pwd** variable, sets the path for the SSL certificate file, and specifies that the server skips verification of the SSL certificate.

## PARAMETERS

### -CertificateFilePassword
Specifies the password, as a secure string, for the SSL certificate file.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificatePath
Specifies the path of the SSL certificate file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the domain name for the server.

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

### -NoCertificateVerification
Indicates that the server skips verification of the SSL certificate.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssDomainNameConfiguration](./Get-WssDomainNameConfiguration.md)

[Join-WssDomain](./Join-WssDomain.md)

[Exit-WssDomain](./Exit-WssDomain.md)

