---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
keywords: powershell, cmdlet
ms.assetid: 2AB404FC-1CE1-4B6E-A457-3505180340F9
manager: dansimp
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Start-IISSite
ms.author: v-kaunu
ms.reviewer:
---

# Start-IISSite

## SYNOPSIS
Starts an existing site on the IIS server.

## SYNTAX

```
Start-IISSite [-Name] <String> [-Passthru] [<CommonParameters>]
```

## DESCRIPTION
The **Start-IISSite** cmdlet starts an existing site on the Internet Information Services (IIS) server.

## EXAMPLES

### Example 1: Start an IIS web site
```
PS C:\> Start-IISSite -Name "Default Web Site"
```

This command starts an IIS web site named Default Web Site

## PARAMETERS

### -Name
Specifies the name of the IIS web site

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Passthru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### Microsoft.Web.Administration.Site

## NOTES

## RELATED LINKS

[Get-IISSite](./Get-IISSite.md)

[New-IISSite](./New-IISSite.md)

[Remove-IISSite](./Remove-IISSite.md)

[Stop-IISSite](./Stop-IISSite.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

