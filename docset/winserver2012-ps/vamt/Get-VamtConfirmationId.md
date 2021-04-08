---
author: Kateyanne
external help file: VAMT_Cmdlets.xml
manager: dansimp
Module Name: VAMT
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/vamt/get-vamtconfirmationid?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VamtConfirmationId

## SYNOPSIS
Acquires confirmation IDs (CIDs) from the Microsoft licensing servers during proxy activation.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VamtConfirmationId [-FileName] <String> [-ProxyPassword <String>] [-ProxyUserName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VamtConfirmationId [-Products] <Product[]> [-ProxyPassword <String>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VamtConfirmationId [-ProxyUserName <String>]
```

## DESCRIPTION
The **Get-VamtConfirmationID** cmdlet acquires the confirmation IDs (CIDs) from the Microsoft licensing servers during proxy activation.
All products either in the Windows PowerShell object or in the .cilx file are updated with the results.

## EXAMPLES

### Example 1
```
PS C:\> get-vamtconfirmationid -filename "c:\users\me\desktop\vamtdata.cilx"
```

This command gets the CIDs for the products in the specified file.

### Example 2
```
PS C:\> $productinfo = get-vamtproduct
PS C:\> $updatedproductinfo = get-vamtconfirmationid -products $productinfo
```

This command gets a product object with all products and gets the confirmation IDs for these products.

## PARAMETERS

### -FileName
Specifies the name of the file that contains the products that need CIDs.
Use the *FileName* parameter during proxy activation to acquire CIDs for all products in the specified .cilx file.
You cannot use the *FileName* parameter together with the *Products* parameter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Products
Specifies the products in dep_nextref_vamt that need CIDs.
By default, if you don't specify a product, CIDs are retrieved for all products in dep_nextref_vamt.
You cannot use the *Products* parameter together with the *FileName* parameter.

```yaml
Type: Product[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -ProxyPassword
Password for a proxy server or gateway, if required for your environment.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -ProxyUserName
User name for a proxy server or gateway, if required for your environment.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Install-VamtConfirmationId](./Install-VamtConfirmationId.md)

