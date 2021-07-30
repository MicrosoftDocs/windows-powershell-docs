---
external help file: RemoteDesktop.psm1-help.xml
Module Name: RDMgmt
online version: https://docs.microsoft.com/powershell/module/rdmgmt/set-rdcertificate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-RDCertificate

## SYNOPSIS
Imports and secures a certificate to use with an RDS role.

## SYNTAX

### Reapply (Default)
```
Set-RDCertificate [-Role] <RDCertificateRole> [-Password <SecureString>] [-ConnectionBroker <String>] [-Force]
 [<CommonParameters>]
```

### Import
```
Set-RDCertificate [-Role] <RDCertificateRole> [-ImportPath <String>] [-Password <SecureString>]
 [-ConnectionBroker <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDCertificate** cmdlet imports a certificate to use with a Remote Desktop Services (RDS) role.
The cmdlet helps secure a certificate by using a secure string supplied by the user.
You can use this cmdlet to apply a new secure string for an existing certificate.

## EXAMPLES

### Example 1: Import a certificate to use with RDS
```
PS C:\> $Password = ConvertTo-SecureString -String "Cups34Horses&&" -AsPlainText -Force PS C:\>Set-RDCertificate -Role RDRedirector -ImportPath "C:\Certificates\Redirector07.pfx" -Password $Password -ConnectionBroker "RDCB.Contoso.com"
```

This example imports a certificate to use with an RDS role.

The first command uses the **ConvertTo-SecureString** cmdlet to create a secure string based on a string that the user supplies, and stores it in the **$Password** variable.
For more information, type `Get-Help ConvertTo-SecureString`.

The second command specifies the file name of the certificate to use for the redirector role for the RD Connection Broker named RDCB.Contoso.com.
The command uses the secure string stored in the **$Password** variable to help secure the certificate.

### Example 2: Apply a secure string to a certificate
```
PS C:\> $Password = ConvertTo-SecureString -String "Wings%%83Potato" -AsPlainText -Force PS C:\>Set-RDCertificate -Role RDRedirector -Password $Password -ConnectionBroker "RDCB.Contoso.com"
```

This example applies a new secure string to a certificate used for an RDS role.

The first command uses the **ConvertTo-SecureString** cmdlet to create a secure string based on a string that the user supplies, and stores it in the **$Password** variable.

The second command uses the secure string stored in the **$Password** variable to secure the certificate used for the redirector role for the RD Connection Broker named RDCB.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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
Performs the action without a confirmation message.

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

### -ImportPath
Specifies the location of a certificate as a file that has a .pfx extension.

```yaml
Type: String
Parameter Sets: Import
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies a secure string used to help secure the certificate.
See the Examples section.

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

### -Role
Specifies a certificate type associated with an RDS server role.
The acceptable values for this parameter are:

- RDGateway
- RDWebAccess
- RDRedirector
- RDPublishing

```yaml
Type: RDCertificateRole
Parameter Sets: (All)
Aliases:
Accepted values: RDGateway, RDWebAccess, RDRedirector, RDPublishing

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null
None.

## NOTES

## RELATED LINKS

[Get-RDCertificate](./Get-RDCertificate.md)

[New-RDCertificate](./New-RDCertificate.md)

