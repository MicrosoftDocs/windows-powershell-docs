---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 741FF2B8-A6E2-4A39-8470-2F7CA6CC7808
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# New-WebBinding

## SYNOPSIS
Adds a new binding to an existing Web site.

## SYNTAX

```
New-WebBinding [[-Name] <String>] [-Protocol <String>] [-Port <UInt32>] [-IPAddress <String>]
 [-HostHeader <String>] [-SslFlags <Int32>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
Adds a new binding to an existing Web site.

## EXAMPLES

### -------------- EXAMPLE 1: Adding a new Site Binding --------------
```
IIS:\>New-WebBinding -Name "Default Web Site" -IPAddress "*" -Port 80 -HostHeader TestSite
```

Creates a new binding on the Default Web Site.

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
The host header of the new binding.

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
The IP address of the new binding.

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
The name of the Web site on which the new binding is created.

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
The port used for the binding.

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
The protocol to be used for the Web binding (usually HTTP, HTTPS, or FTP).

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
Indicates what type of certificate and/or certificate storage the new website supports.
Only the following values are valid: 0 (Regular certificate in Windows certificate storage), 1 (SNI certificate), 2 (central certificate store), or 3 (SNI certificate in central certificate store).

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

