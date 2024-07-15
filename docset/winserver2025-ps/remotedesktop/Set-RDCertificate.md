---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rdcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDCertificate
---

# Set-RDCertificate

## Synopsis
Imports or applies a certificate to use with an RDS role.

## Syntax

### Reapply (default)
```PowerShell
Set-RDCertificate [-Role] <RDCertificateRole> [-Password <SecureString>] [-ConnectionBroker <String>] [-Force]
 [<CommonParameters>]
```

### Import
```PowerShell
Set-RDCertificate [-Role] <RDCertificateRole> [-ImportPath <String>] [-Password <SecureString>]
 [-ConnectionBroker <String>] [-Force] [<CommonParameters>]
```

### Thumbprint
```PowerShell
Set-RDCertificate [-Role] <RDCertificateRole> [-Thumbprint <String>] [-ConnectionBroker <String>] [-Force]
 [<CommonParameters>]
```

## Description

The **Set-RDCertificate** cmdlet imports a certificate or applies an installed certificate to use with a Remote Desktop Services (RDS) role. You can use this cmdlet to secure an existing certificate by using a secure string supplied by the user.

## Examples

### Example 1: import a certificate to use with RDS

The following example imports a certificate to use with an RDS role.
```PowerShell
PS C:\>$Password = ConvertTo-SecureString -String "Cups34Horses&&" -AsPlainText -Force
PS C:\>Set-RDCertificate -Role RDRedirector -ImportPath "C:\Certificates\Redirector07.pfx" -Password $Password -ConnectionBroker "RDCB.Contoso.com"
```

The first part of the example uses the **ConvertTo-SecureString** cmdlet to create a secure string based on a string that the user supplies and stores it in the **$Password** variable. For more information, see [ConvertTo-SecureString](/powershell/module/microsoft.powershell.security/ConvertTo-SecureString?view=powershell-6). You can also enter the `Get-Help ConvertTo-SecureString` cmdlet into your PowerShell window.

The second part of the example specifies the file name of the certificate to use for the redirector role for the RD Connection Broker named RDCB.Contoso.com. The cmdlet uses the secure string stored in the **$Password** variable to help secure the certificate.

### Example 2: apply a secure string to a certificate

The following example cmdlet applies a new secure string to an RDS role certificate.
```PowerShell
PS C:\>$Password = ConvertTo-SecureString -String "Wings%%83Potato" -AsPlainText -Force
PS C:\>Set-RDCertificate -Role RDRedirector -Password $Password -ConnectionBroker "RDCB.Contoso.com"
```

The first part of the example uses the **ConvertTo-SecureString** cmdlet to create a secure string based on a string that the user supplies and stores it in the **$Password** variable.

The second part of the example uses the secure string stored in the **$Password** variable to secure the certificate used for the redirector role for the RD Connection Broker named RDCB.Contoso.com.

### Example 3: apply an installed certificate to use with RDS

The following example applies an existing certificate to use with an RDS role.
```PowerShell
PS C:\>Set-RDCertificate -Role RDRedirector -Thumbprint fedd995b45e633d4ef30fcbc8f3a48b627e9a28b -ConnectionBroker "RDCB.Contoso.com"
```

The first part of the example specifies the thumbprint of the certificate to use for the RD Connection Broker's redirector role, which in this example is named "RDCB.Contoso.com." The certificate must be installed in the "localmachine\my" store on each server running the specified RDS role. The `-Thumbprint` parameter is only available in Windows Server 2019.

## Parameters

### -ConnectionBroker
This parameter specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.

If you don't specify a value, the cmdlet uses the local computer's fully qualified domain name (FQDN).

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
This parameter performs the action without a confirmation message.

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
This parameter specifies the location of a certificate as a file that has a .pfx extension.

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
This parameter specifies a secure string used to help secure the certificate.

See the Examples section.

```yaml
Type: SecureString
Parameter Sets: Reapply, Import
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Role
This parameter specifies a certificate type associated with an RDS server role.

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

### -Thumbprint
This parameter specifies the thumbprint of the certificate to use. Currently, it is only available in Windows Server 2019.

```yaml
Type: String
Parameter Sets: Thumbprint
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the following common parameters: *-Debug*, *-ErrorAction*, *-ErrorVariable*, *-InformationAction*, *-InformationVariable*, *-OutVariable*, *-OutBuffer*, *-PipelineVariable*, *-Verbose*, *-WarningAction*, and *-WarningVariable*.

For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### None

## Outputs

### System.Object

## Notes

## Related links

[Get-RDCertificate](./Get-RDCertificate.md)

[New-RDCertificate](./New-RDCertificate.md)

[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)
