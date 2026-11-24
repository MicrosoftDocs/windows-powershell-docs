---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsalternatetlsclientbinding?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsAlternateTlsClientBinding
---

# Set-AdfsAlternateTlsClientBinding

## SYNOPSIS
Configures an existing AD FS deployment to use the same port for both device certificate and client certificate authentication.

## SYNTAX

```
Set-AdfsAlternateTlsClientBinding [-Thumbprint <String>] [-Member <String[]>] [-Force <Boolean>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsAlternateTlsClientBinding** cmdlet configures an existing AD FS deployment to use the same port (443) for both device certificate and client certificate authentication (client TLS).
The cmdlet creates an endpoint for user certificate authentication on `certauth`.\<federation service name\>, such as `certauth.contoso.com`.

To change the deployment back to one in which user certificate authentication uses a non-standard port, use the Set-AdfsSslCertificate cmdlet with a new certificate that does not contain a Subject Alternative Name (SAN) for `certauth`.\<federation service name\>.

The **Install-AdfsFarm** cmdlet configures client TLS on port 49443 if the SSL certificate does not contain a Subject Alternative Name (SAN) for `certauth`.\<federation service name\>, such as `certauth.contoso.com`.

Use **Set-AdfsAlternateTlsClientBinding** with a new certificate that contains the SAN entry.
It will configure AD FS to use port 443 for client TLS.

## EXAMPLES

### Example 1: Configure a deployment
```
PS C:\> Set-AdfsAlternateTlsClientBinding -Member "ADFSServer1.contoso.com" -Thumbprint "c67e1ffba186d70c7e00c89596e0cb5645f9874a"
```

This command configures a deployment to use the same port for device certificate authentication and user certificate authentication.
In this example, the certificate that has the specified thumbprint contains a SAN for certauth.contoso.com.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Member
```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AdfsSslCertificate](./Set-AdfsSslCertificate.md)

