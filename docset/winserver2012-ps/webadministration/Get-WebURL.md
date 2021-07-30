---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://docs.microsoft.com/powershell/module/webadministration/get-weburl?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WebURL

## SYNOPSIS
Gets information about the URL associated with the specified Web site.

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
Gets information about the URL associated with the specified Web site.

## EXAMPLES

### -------------- EXAMPLE 1: Request the Default Web Site --------------
```
IIS:\>Get-WebURL 'IIS:\Sites\Default Web Site'
```

Returns data about the Default Web Site.

ResponseUri Contents

----------- --------

https://localhost/ \<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN".

## PARAMETERS

### -Accept
An HTTP Accept header.

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
An IIS configuration path to the site for which information is returned.

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
The URL for which information is retrieved.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

