---
external help file: Microsoft.KeyDistributionService.Cmdlets.dll-Help.xml
ms.assetid: EA11EBE8-C5AB-42B5-AF52-903CD262849F
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-KdsRootKey

## SYNOPSIS
Retrieves a list of root key values stored by the Microsoft Group Key Distribution Service (KdsSvc).

## SYNTAX

```
Get-KdsRootKey [<CommonParameters>]
```

## DESCRIPTION
The **Get-KdsRootKey** cmdlet retrieves the following information from Active Directory (AD) for each root key: 

 -- The root key identifier 

 -- The root key value 

 -- The Microsoft Group Key Distribution Service (KdsSvc).

This information is required to generate the group keys distributed by the Microsoft Group KdsSvc.

## EXAMPLES

### Example 1: Retrieve a list of root key values
```
PS C:\>Get-KdsRootKey
```

This example retrieves a list of root key values stored in AD.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### System.Collections.Generic.List`1<KdsRootKey^>
A list of master root keys stored in AD.

## NOTES

## RELATED LINKS

[Add-KdsRootKey](./Add-KdsRootKey.md)

[Clear-KdsCache](./Clear-KdsCache.md)

[Get-KdsConfiguration](./Get-KdsConfiguration.md)

[Set-KdsConfiguration](./Set-KdsConfiguration.md)

[Test-KdsRootKey](./Test-KdsRootKey.md)

