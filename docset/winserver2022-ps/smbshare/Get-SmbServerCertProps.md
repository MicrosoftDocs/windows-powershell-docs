---
external help file: SmbScriptModule.psm1-help.xml
Module Name: SmbShare
online version:
schema: 2.0.0
---

# Get-SmbServerCertProps

## SYNOPSIS
Retrieves an SMB over QUIC-mapped certificate’s properties and tests certificate validity.

## SYNTAX

```
Get-SmbServerCertProps [-Name] <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The Get- SmbServerCertProps cmdlet retrieves the properties of a certificate associated with the SMB server for SMB over QUIC on ‘Windows Server 2022 Datacenter: Azure Edition’. It also tests the validity of the certificate. This cmdlet is not used for Windows or other Windows Server editions. For more information, review SMB over QUIC.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-SmbServerCertProps -Name 2022-ae-02.corp.contoso.com
```

This command retrieves the properties and validity of the “2022-ae-02.corp.contoso.com” SMB over QUIC endpoint certificate mapping.

## PARAMETERS

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

### -Name
Specifies a fully-qualified DNS name or NetBIOS name that must match the certificate’s subject name or an entry in the certificate’s subject alternative names.

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
