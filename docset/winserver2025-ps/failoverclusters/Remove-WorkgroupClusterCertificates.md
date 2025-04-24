---
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
online version:
schema: 2.0.0
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
- Cert:\CurrentUser\My
- Cert:\CurrentUser\CA

Certificates are filtered for those issued by issuers starring with PKU2UAuthority.

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
{{ Fill Authority Description }}

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
Indicates whether to force the removal of certificates without prompting for confirmation.
By default, the value is $false.

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

## OUTPUTS

## NOTES

## RELATED LINKS
