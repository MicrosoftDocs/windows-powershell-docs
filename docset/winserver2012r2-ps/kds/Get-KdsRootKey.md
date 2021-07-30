---
external help file: Microsoft.KeyDistributionService.Cmdlets.dll-Help.xml
Module Name: KDS
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/kds/get-kdsrootkey?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-KdsRootKey
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

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

