---
external help file: Microsoft.AzureStack.HCI.Billing.Management.PowerShell.dll-Help.xml
Module Name: azurestackhci
online version:
schema: 2.0.0
---

# Set-AzureStackHCIRegistrationCertificate

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Set-AzureStackHCIRegistrationCertificate -ServiceEndpoint <String> -TenantId <String> -AppId <String>
 -AADAuthority <String> -BillingServiceApiScope <String> -GraphServiceApiScope <String>
 [-CertificateThumbprint <String>] -CloudId <String> [[-ComputerName] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
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

### -AADAuthority
{{ Fill AADAuthority Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: Auth

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AppId
{{ Fill AppId Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: AI

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BillingServiceApiScope
{{ Fill BillingServiceApiScope Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: BillingSc

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint
{{ Fill CertificateThumbprint Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: CertTh

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudId
{{ Fill CloudId Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: CldId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
{{ Fill ComputerName Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Credential
{{ Fill Credential Description }}

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GraphServiceApiScope
{{ Fill GraphServiceApiScope Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: GraphSc

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceEndpoint
{{ Fill ServiceEndpoint Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: SE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TenantId
{{ Fill TenantId Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases: TI

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
