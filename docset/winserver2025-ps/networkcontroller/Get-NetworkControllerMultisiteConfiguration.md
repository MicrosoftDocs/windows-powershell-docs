---
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
online version: https://learn.microsoft.com/powershell/module/networkcontroller/get-networkcontrollermultisiteconfiguration?view=windowsserver2025-ps
schema: 2.0.0
---

# Get-NetworkControllerMultisiteConfiguration

## SYNOPSIS

Gets Multisite peering configuration parameters

## SYNTAX

```
Get-NetworkControllerMultisiteConfiguration [-ConnectionUri <Uri>]
[-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException]
[<CommonParameters>]
```

## DESCRIPTION

The `Get-NetworkControllerMultisiteConfiguration` cmdlet gets current Multisite settings. Use this
cmdlet to obtain site details, site names and encryption details. This cmdlet can also be used as a
sanity check for the state of a deployment.

## EXAMPLES

### Example 1: Check Peering State

```powershell
Get-NetworkControllerMultisiteConfiguration -ConnectionUri 'https://site1.com' | ConvertTo-JSON
-depth 100
```


## PARAMETERS

### -CertificateThumbprint

Specifies the digital public key X.509 certificate of a user account that has permission to perform
this action. Specify this parameter only if you run this cmdlet on a computer that is not part of
the network controller cluster.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionUri

Specifies the Uniform Resource Identifier (URI) of a Network Controller. 

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies a user credential that has permission to perform this action. The
default is the current user. Specify this parameter only if you run this cmdlet
on a computer that is not part of the network controller cluster.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassInnerException

This thumbprint must also be provided in the **ClientCertificateThumbprint**
parameter in the `Install-NetworkController` or `Set-NetworkController` cmdlet so
that Network Controller can authorize this user. The thumbprint must be provided
only if the network controller client authentication is X509 certificates.
`Get-NetworkController` retrieves that client authentication and authorization
information.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction,
-ErrorVariable, -InformationAction, -InformationVariable, -OutVariable,
-OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

### System.Object

## NOTES

## RELATED LINKS

[Set-NetworkControllerMultisitePrimary](./Set-NetworkControllerMultisitePrimary.md)

[Set-NetworkControllerMultisiteConfiguration](./Set-NetworkControllerMultisiteConfiguration.md)
