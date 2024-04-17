---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfswebconfig?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsWebConfig
---

# Set-AdfsWebConfig

## SYNOPSIS
Modifies web customization configuration settings.

## SYNTAX

```
Set-AdfsWebConfig [-ActiveThemeName <String>] [-CDCCookieReader <Uri>] [-CDCCookieWriter <Uri>]
 [-HRDCookieLifetime <Int32>] [-HRDCookieEnabled <Boolean>] [-ContextCookieEnabled <Boolean>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Set-AdfsWebConfig` cmdlet modifies web customization configuration settings. These settings
impact any protocol that Active Directory Federation Services (AD FS) supports where a web browser
facilitates token requests for home realm discovery (HRD) and authentication.

## EXAMPLES

### Example 1: Set customization configuration properties

```powershell
$pSSetAdfsWebConfigSplat = @{
    ActiveThemeName = "Default"
    CDCCookieReader = 'https://www.Contoso.com/reader.aspx'
    CDCCookieWriter = 'https://www.Contoso.com/writer.aspx'
    ContextCookieEnabled = $True
    HRDCookieEnabled = $True
    HRDCookieLifetime = 30
}
PSSet-AdfsWebConfig @pSSetAdfsWebConfigSplat
```

```Output
ActiveThemeName      : Default
CDCCookieReader      :
CDCCookieWriter      :
HRDCookieLifetime    : 30
HRDCookieEnabled     : True
ContextCookieEnabled : True
```

This command sets properties in the web customization configuration settings.

## PARAMETERS

### -ActiveThemeName

Specifies the name of a web theme to be set as the active web theme in the web customization
configuration. To create a web theme, use the `New-AdfsWebTheme` cmdlet.

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

### -CDCCookieReader

Specifies the Uniform Resource Identifier (URI) of the Common Domain Cookie (CDC) reader.

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

### -CDCCookieWriter

Specifies the URI of the CDC writer.

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

### -ContextCookieEnabled

Indicates whether to enable the context cookie.

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

### -HRDCookieEnabled

Indicates whether to enable the HRD cookie. If you specify a value of `$false`, when AD FS has more
than one claims provider trust enabled, end users must select the home realm in every application
request.

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

### -HRDCookieLifetime

Specifies the lifetime, in days, of an HRD cookie.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Returns an object representing the item with which you are working. By default, this cmdlet does not
generate any output.

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

Shows what would happen if the cmdlet runs. The cmdlet is not run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

By default, this cmdlet doesn't return any output.

### AdfsWebConfig

When you use the **PassThru** parameter, this cmdlet returns an **AdfsWebConfig** object that
represents the modified configuration settings.

## NOTES

## RELATED LINKS

[Get-AdfsWebConfig](./Get-AdfsWebConfig.md)

[New-AdfsWebTheme](./New-AdfsWebTheme.md)
