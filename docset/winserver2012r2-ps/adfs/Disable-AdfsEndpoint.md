---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Disable-AdfsEndpoint
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: EC488965-7310-4586-83EC-791BB06838A1
---

# Disable-AdfsEndpoint

## SYNOPSIS
Disables an endpoint of AD FS.

## SYNTAX

### Address
```
Disable-AdfsEndpoint [[-TargetAddressPath] <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TargetObject
```
Disable-AdfsEndpoint [-TargetEndpoint] <Endpoint> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FullUrl
```
Disable-AdfsEndpoint [-TargetFullUrl] <Uri> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-AdfsEndpoint** cmdlet disables an endpoint of Active Directory Federation Services (AD FS).

## EXAMPLES

### Example 1: Disable an endpoint
```
PS C:\>Disable-AdfsEndpoint -TargetAddressPath "/adfs/services/trust/13/Windows"
```

This command disables the WS-Trust 1.3 endpoint on the current federation server.

## PARAMETERS

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

### -TargetAddressPath
Specifies the address path of the endpoint.
The cmdlet disables the endpoint that you specify.
An example of such a path is /adfs/portal/updatepassword.

```yaml
Type: String
Parameter Sets: Address
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetEndpoint
Specifies the endpoint to disable.
This value is typically taken from the pipeline.

```yaml
Type: Endpoint
Parameter Sets: TargetObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetFullUrl
Specifies the full URL of the endpoint to disable.

```yaml
Type: Uri
Parameter Sets: FullUrl
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.IdentityServer.PowerShell.Resources.Endpoint
A class that represents an endpoint for the Federation Service.

## OUTPUTS

### None

## NOTES
* Endpoints provide access to the federation server functionality of Active Directory Federation Services (AD FS), such as token issuance and the publishing of federation metadata. Depending on the type of endpoint, you can enable or disable the endpoint or control whether the endpoint is published to Web Application Proxy.

## RELATED LINKS

[Enable-AdfsEndpoint](./Enable-AdfsEndpoint.md)

[Get-AdfsEndpoint](./Get-AdfsEndpoint.md)

[Set-AdfsEndpoint](./Set-AdfsEndpoint.md)

