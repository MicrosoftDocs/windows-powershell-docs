---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: adfs
ms.date: 09/30/2021
online version: https://docs.microsoft.com/powershell/module/adfs/set-adfsresponseheaders?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsResponseHeaders
---

# Set-AdfsResponseHeaders

## SYNOPSIS
{{ Fill in the Synopsis }}

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
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

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
{{ Fill CORSTrustedOrigins Description }}

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
{{ Fill EnableCORS Description }}

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
{{ Fill EnableResponseHeaders Description }}

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
{{ Fill RemoveHeaders Description }}

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
{{ Fill SetHeaderName Description }}

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
{{ Fill SetHeaderValue Description }}

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
