---
description: Remove certificates issued by a specific issuer from the local machine and current user certificate stores.
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
online version:
schema: 2.0.0
ms.date: 04/24/2025
---

# Remove-WorkgroupClusterCertificates

## SYNOPSIS
Removes certificates issued by a specific issuer from the local machine and current user certificate stores.

## SYNTAX

```
Remove-WorkgroupClusterCertificates [[-Authority] <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The Remove-WorkgroupClusterCertificates function removes certificates from the following certificate stores:
- Cert:\LocalMachine\My
- Cert:\LocalMachine\Local Cert Issuer
- Cert:\LocalMachine\Root
- Cert:\CurrentUser\My
- Cert:\CurrentUser\CA

Certificates are filtered for those issued by an issuer name that starts with the value specified in the **Authority** parameter (by default, "PKU2UAuthority*").

## EXAMPLES

### EXAMPLE 1
```
Remove-WorkgroupClusterCertificates -Force
```

Removes all certificates issued by "CN=PKU2UAuthority*" from the certificate stores without prompting for confirmation.

### EXAMPLE 2
```
Remove-WorkgroupClusterCertificates
```

Prompts for confirmation before removing each certificate issued by "CN=PKU2UAuthority*" from the certificate stores.

## PARAMETERS

### -Authority
Specifies the issuer name prefix to match when removing certificates. Only certificates issued by an issuer whose name starts with this value will be removed. The default is "PKU2UAuthority*".

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: PKU2UAuthority*
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates whether to force the removal of certificates without prompting for confirmation. By default, the value is $false.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe a string value for the Authority parameter to this cmdlet.

## OUTPUTS

### None
This cmdlet does not generate any output. It performs the operation of removing certificates from the specified certificate stores.

## NOTES

## RELATED LINKS
