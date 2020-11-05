---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssMsoSharePointLibrary
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: BD3E7662-A7E9-470D-A4C6-5B1D4383D7C2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssMsoSharePointLibrary

## SYNOPSIS
Sets the properties of a sp_online_2 library.

## SYNTAX

```
Set-WssMsoSharePointLibrary [-Library] <SharePointLibrary> [[-Name] <String>] [[-Description] <String>]
 [-EnableVersioning] [-ForceCheckout] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssMsoSharePointLibrary** cmdlet sets the properties of a sp_online_1 library.
A office_365_1 site stores the sp_online_2 library.

## EXAMPLES

### Example 1: Set properties of a SharePoint library
```
PS C:\> $Library = Get-WssMsoSharePointLibrary | Select-Object -First 1
PS C:\> Set-WssMSOSharePointLibrary -Library $Library -Name "New Name" -Description "New Description" -ForceCheckout -EnableVersioning
```

The first command uses the Get-WssMsoSharePointLibrary cmdlet to get a library, and stores the result in the $Library variable.

The second command sets the properties of a library by using the $Library variable.
The command also sets the **ForceCheckout** and **EnableVersioning** parameters.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Description
Specifies a description of a sp_online_2 library.
The cmdlet modifies the properties of a library with the description you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableVersioning
Indicates that versioning is enabled for this library.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ForceCheckout
Indicates that force checkout is enabled for this library.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Library
Specifies a  sp_online_2 library object.
The cmdlet modifies the library that you specify.

```yaml
Type: SharePointLibrary
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a library.
The cmdlet modifies the name of a sp_online_2 library with the name that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.O365Integration.SharePointLibrary
Library

Type: Microsoft.WindowsServerSolutions.O365Integration.SharePointLibrary

Description: SharePoint library

## OUTPUTS

### SharePointLibrary

## NOTES

## RELATED LINKS

[Get-WssMsoSharePointLibrary](./Get-WssMsoSharePointLibrary.md)

[New-WssMsoSharePointLibrary](./New-WssMsoSharePointLibrary.md)

[Remove-WssMsoSharePointLibrary](./Remove-WssMsoSharePointLibrary.md)

