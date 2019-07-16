---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: 42FC4F44-1435-4584-9B44-3369751985AB
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Enable-AdfsClient
ms.reviewer:
---

# Enable-AdfsClient

## SYNOPSIS
Enables the use of an OAuth 2.0 client registration by AD FS.

## SYNTAX

### Name (Default)
```
Enable-AdfsClient [[-TargetName] <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ClientId
```
Enable-AdfsClient [-TargetClientId] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Enable-AdfsClient [-TargetClient] <AdfsClient> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-AdfsClient** cmdlet enables the use of an OAuth 2.0 client registration by Active Directory Federation Services (AD FS).
Use this cmdlet to enable a registered OAuth 2.0 client that is currently disabled.
If AD FS receives a request for authorization from an OAuth 2.0 client that is registered with  AD FS but not enabled, it will deny access to the resource.

## EXAMPLES

### Example 1: Enable an OAuth 2.0 client
```
PS C:\> Enable-AdfsClient -TargetName "Payroll Application"
```

This command enables the registered OAuth 2.0 client identified by the name Payroll Application.

## PARAMETERS

### -PassThru
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

### -TargetClient
Specifies the registered OAuth 2.0 client to enable.

```yaml
Type: AdfsClient
Parameter Sets: InputObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetClientId
Specifies the client identifier for the registered OAuth 2.0 client to enable.

```yaml
Type: String
Parameter Sets: ClientId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the registered OAuth 2.0 client to enable.

```yaml
Type: String
Parameter Sets: Name
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsClient](./Add-AdfsClient.md)

[Disable-AdfsClient](./Disable-AdfsClient.md)

[Get-AdfsClient](./Get-AdfsClient.md)

[Remove-AdfsClient](./Remove-AdfsClient.md)

[Set-AdfsClient](./Set-AdfsClient.md)

