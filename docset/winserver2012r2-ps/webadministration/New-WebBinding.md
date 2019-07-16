---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: New-WebBinding
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 741FF2B8-A6E2-4A39-8470-2F7CA6CC7808
ms.author: v-anbarr
ms.reviewer: brianlic
---

# New-WebBinding

## SYNOPSIS
Adds a binding to a website.

## SYNTAX

```
New-WebBinding [[-Name] <String>] [-Protocol <String>] [-Port <UInt32>] [-IPAddress <String>]
 [-HostHeader <String>] [-SslFlags <Int32>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **New-WebBinding** cmdlet adds a new binding to an existing website.

## EXAMPLES

### Example 1: Adding a new site binding
```
IIS:\>New-WebBinding -Name "Default Web Site" -IPAddress "*" -Port 80 -HostHeader "TestSite"
```

This command creates a binding on the default website.

## PARAMETERS

### -Force
Forces the creation of the binding.

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

### -HostHeader
Specifies the host header of the new binding.

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
Specifies the IP address of the new binding.

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
Specifies the name of the website on which this cmdlet creates the new binding.

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
Specifies the port for the new binding.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Protocol
Specifies the protocol for the new binding.
This protocol is usually HTTP, HTTPS, or FTP.

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

### -SslFlags
Indicates what type of certificate and certificate storage the new website supports.
The acceptable values for this parameter are:

- 0: Regular certificate in Windows certificate storage. 
- 1: SNI certificate. 
- 2: Central certificate store.
- 3: SNI certificate in central certificate store.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WebBinding](./Get-WebBinding.md)

[Remove-WebBinding](./Remove-WebBinding.md)

[Set-WebBinding](./Set-WebBinding.md)

