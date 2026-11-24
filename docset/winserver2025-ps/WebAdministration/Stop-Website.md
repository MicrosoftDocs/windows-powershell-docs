---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/stop-website?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Website
---

# Stop-Website

## SYNOPSIS
Stops an IIS website.

## SYNTAX

```
Stop-Website [[-Name] <String>] [-Passthru] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-Website** cmdlet stops the specified Internet Information Services (IIS) website.

## EXAMPLES

### Example 1: Stop a website
```
IIS:\> Stop-WebSite -Name "Default Web Site"
```

This command stops the site named Default Web Site.

## PARAMETERS

### -Name
Specifies the name of the website that this cmdlet stops.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru
Passes an object that represents the website to the pipeline.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Website](./Get-Website.md)

[New-Website](./New-Website.md)

[Remove-Website](./Remove-Website.md)

[Start-WebAppPool](./Start-WebAppPool.md)

[Start-WebItem](./Start-WebItem.md)

[Start-Website](./Start-Website.md)

[Stop-WebAppPool](./Stop-WebAppPool.md)

[Stop-WebItem](./Stop-WebItem.md)

