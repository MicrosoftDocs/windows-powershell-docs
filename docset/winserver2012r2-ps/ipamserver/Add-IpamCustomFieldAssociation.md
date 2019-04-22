---
external help file: IpamCustomFieldAssociation.cdxml-help.xml
Module Name: IpamServer
online version: 
schema: 2.0.0
title: Add-IpamCustomFieldAssociation
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 81BD475F-0724-4AC9-B648-E9B705BB0EEA
---

# Add-IpamCustomFieldAssociation

## SYNOPSIS
Adds an association between values for custom fields that are defined in IPAM.

## SYNTAX

```
Add-IpamCustomFieldAssociation [-CustomFieldOne] <String> [-CustomFieldTwo] <String>
 [-AssociationValue] <String[]> [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-IpamCustomFieldAssociation** cmdlet adds an association between values for two custom fields that are defined in IP Address Management (IPAM).
Specify the custom fields by using the **CustomFieldOne** and **CustomFieldTwo** parameters.
Specify the associations as an array of pairs of values in the format CustomFieldValue01:CustomFieldValue02.

Use the Get-IpamCustomFieldAssociation cmdlet to see existing associations.
Use the Set-IpamCustomFieldAssociation cmdlet to modify associations.
Use the Remove-IpamCustomFieldAssociation cmdlet to remove associations.

## EXAMPLES

### Example 1: Create a custom association between two fields
```
PS C:\> Add-IpamCustomFieldAssociation  -CustomFieldOne "VmmLogicalNetwork" -CustomFieldTwo "NetworkSite" -AssociationValue "Storage:Site01","Storage:Site02","Public:Site03" -PassThru
CustomFieldOne   : VmmLogicalNetwork

CustomFieldTwo   : NetworkSite

AssociationValue : {Public:Site03, Storage:Site02, Storage:Site01
```

This command adds an association between values of two custom fields, VmmLogicalNetwork and NetworkSite.
The command specifies three pairs of values.
The command includes the **PassThru** parameter, so it displays results to the console.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -AssociationValue
Specifies an array of value pairs.
Each pair, a string, includes two values that are separated by a colon (:).
The first value in a pair corresponds to the custom field that is specified by the **CustomFieldOne** parameter.
The second value corresponds to the custom field that is specified by the **CustomFieldTwo** parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -CustomFieldOne
Specifies a custom field.
This field corresponds to the first value in a pair that is specified through the **AssociationValue** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CustomField1

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomFieldTwo
Specifies a custom field.
This field corresponds to the second value in a pair that is specified through the **AssociationValue** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CustomField2

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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

### IpamCustomFieldAssociation
An object that represents an association between values of one custom field and values of another custom field.

## NOTES

## RELATED LINKS

[Get-IpamCustomFieldAssociation](./Get-IpamCustomFieldAssociation.md)

[Set-IpamCustomFieldAssociation](./Set-IpamCustomFieldAssociation.md)

[Remove-IpamCustomFieldAssociation](./Remove-IpamCustomFieldAssociation.md)

