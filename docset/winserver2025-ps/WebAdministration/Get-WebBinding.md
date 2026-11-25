---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webbinding?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebBinding
---

# Get-WebBinding

## SYNOPSIS
Gets the bindings on an IIS site.

## SYNTAX

```
Get-WebBinding [[-Name] <String>] [-Protocol <String>] [-Port <String>] [-IPAddress <String>]
 [-HostHeader <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebBinding** cmdlet gets information about the bindings configured on an Internet Information Services (IIS) site, such as protocol and port number.

## EXAMPLES

### Example 1: Get the site bindings of the default website
```
IIS:\> Get-WebBinding -Name "Default Web Site"
```

This command gets the bindings configured on the default website.

## PARAMETERS

### -HostHeader
Specifies the host name for which the binding is configured.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPAddress
Specifies the IP address for which the binding is configured.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the site for which this cmdlet returns binding information.

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

### -Port
Specifies the port for which the binding is configured.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Protocol
Specifies the protocol for which the binding is configured.
The protocol is usually HTTP, HTTPS, or FTP.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.IIs.PowerShell.Framework.ConfigurationElement#bindings#binding

## NOTES

## RELATED LINKS

[New-WebBinding](./New-WebBinding.md)

[Remove-WebBinding](./Remove-WebBinding.md)

[Set-WebBinding](./Set-WebBinding.md)
