---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-weburl?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebURL
---

# Get-WebURL

## SYNOPSIS
Gets information about the URL associated with a website.

## SYNTAX

### InputPSPath (Default)
```
Get-WebURL [[-PSPath] <String[]>] [-Accept <String>] [-ResponseHeaders] [-Content] [<CommonParameters>]
```

### InputURL
```
Get-WebURL [[-Url] <Uri[]>] [-Accept <String>] [-ResponseHeaders] [-Content] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebURL** cmdlet gets information about the URL associated with the specified website.

## EXAMPLES

### Example 1: Request the default website
```
IIS:\> Get-WebURL -PSPath "IIS:\Sites\Default Web Site"
ResponseUri       Contents
-----------       --------
http://localhost/ <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN".
```

This command returns data about the default website.

## PARAMETERS

### -Accept
Specifies an HTTP Accept header.

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

### -Content
The content returned by the request.

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

### -PSPath
Specifies an IIS configuration path to the site for which this cmdlet returns information.

```yaml
Type: String[]
Parameter Sets: InputPSPath
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ResponseHeaders
The HTTP Response headers.

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

### -Url
Specifies the URL for which information is retrieved.

```yaml
Type: Uri[]
Parameter Sets: InputURL
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

