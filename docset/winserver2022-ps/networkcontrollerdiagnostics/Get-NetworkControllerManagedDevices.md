---
external help file: Debug-NetworkController.psm1-help.xml
Module Name: NetworkControllerDiagnostics
online version:
schema: 2.0.0
---

# Get-NetworkControllerManagedDevices

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Get-NetworkControllerManagedDevices [-RestURI] <String> [[-Credential] <PSCredential>]
 [[-CertificateThumbprint] <String>] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -CertificateThumbprint
Certificate thumbprint to use for Network Controller.
Specify in case of certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Credential to use for Network Controller.
Specify in case of Kerberos deployment.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestURI
The URI to be used for Network Controller REST APIs.
Specify in case of wild card certificate deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
