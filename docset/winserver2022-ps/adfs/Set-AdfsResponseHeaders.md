---
description: Updates the response headers that are included in the outgoing HTTP response sent by AD FS to a web browser.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: adfs
ms.date: 10/28/2021
online version: https://docs.microsoft.com/powershell/module/adfs/set-adfsresponseheaders?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsResponseHeaders
---

# Set-AdfsResponseHeaders

## SYNOPSIS
Updates the response headers that are included in the outgoing HTTP response sent by AD FS to a web
browser.

## SYNTAX

### DefaultSet (Default)
```
Set-AdfsResponseHeaders [-RemoveHeaders <String[]>] [-EnablePublicKeyPinning <Boolean>]
 [-PublicKeyPinningReportUri <Uri>] [-PublicKeyPrimary <String>] [-PublicKeySecondary <String>]
 [-EnableCORS <Boolean>] [-EnableResponseHeaders <Boolean>] [-CORSTrustedOrigins <String[]>]
 [-AdditionalPublicKeys <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetHeader
```
Set-AdfsResponseHeaders -SetHeaderName <String> -SetHeaderValue <String> [-RemoveHeaders <String[]>]
 [-EnablePublicKeyPinning <Boolean>] [-PublicKeyPinningReportUri <Uri>] [-PublicKeyPrimary <String>]
 [-PublicKeySecondary <String>] [-EnableCORS <Boolean>] [-EnableResponseHeaders <Boolean>]
 [-CORSTrustedOrigins <String[]>] [-AdditionalPublicKeys <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsResponseHeaders** cmdlet updates the response headers that are included in the
outgoing HTTP response sent by AD FS to a web browser.

You can set common security headers such as **HSTS**, **CSP**,
**X-Frame-Options**, **X-XSS-Protection** and **CORS**. You can also set new custom headers, for
example **TestHeader**.

For more information, see [Customize HTTP security response headers with AD FS](/windows-server/identity/ad-fs/operations/customize-http-security-headers-ad-fs).

## EXAMPLES

### Example 1: Set Strict-Transport-Security header
```powershell
PS> Set-AdfsResponseHeaders -SetHeaderName "Strict-Transport-Security" -SetHeaderValue "max-age=31536000; includeSubDomains"
```

Sets the **Strict-Transport-Security** header to a max age of one year and include subdomains.

## PARAMETERS

### -AdditionalPublicKeys
{{ Fill AdditionalPublicKeys Description }}

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

### -CORSTrustedOrigins
Specifies a list of CORS trusted origins. For example,
`-CORSTrustedOrigins https://example1.com,https://example2.com`

You can allow CORS requests from any origin by including "*" in the list of trusted origins,
although this approach is not recommended due to security vulnerabilities.

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

### -EnableCORS
Enable or disables CORS functionality. By default, CORS functionality is not enabled. When enabled,
you can CORS trusted origins using the **-CORSTrustedOrigins** parameter.

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

### -EnablePublicKeyPinning
{{ Fill EnablePublicKeyPinning Description }}

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

### -EnableResponseHeaders

The response headers are sent if **ResponseHeadersEnabled** is set to **$true** (default value). The
value can be set to False to prevent AD FS including any of the security headers in the HTTP
response. Setting the value to **$false** is not recommended.

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

### -PublicKeyPinningReportUri
{{ Fill PublicKeyPinningReportUri Description }}

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicKeyPrimary
{{ Fill PublicKeyPrimary Description }}

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

### -PublicKeySecondary
{{ Fill PublicKeySecondary Description }}

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

### -RemoveHeaders
Removes a header by using the header name. For example, **-RemoveHeaders "MyCustomHeaderName"**.

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

### -SetHeaderName
Header name to set.

You can set common security headers such as **HSTS**, **CSP**, **X-Frame-Options**,
**X-XSS-Protection** and **CORS**. You can also set new custom headers, for example **TestHeader**.

```yaml
Type: String
Parameter Sets: SetHeader
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SetHeaderValue
String used to set the header's value.

```yaml
Type: String
Parameter Sets: SetHeader
Aliases:

Required: True
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
