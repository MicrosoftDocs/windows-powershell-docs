---
author: Kateyanne
description: 
external help file: IpamCustomFieldAssociation.cdxml-help.xml
manager: jasgro
Module Name: IpamServer
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/ipamserver/set-ipamcustomfieldassociation?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IpamCustomFieldAssociation
---

# Set-IpamCustomFieldAssociation

## SYNOPSIS
Modifies associations of values for custom fields defined in IPAM.

## SYNTAX

```
Set-IpamCustomFieldAssociation [-CustomFieldOne] <String> [-CustomFieldTwo] <String>
 [-AddAssociationValue <String[]>] [-RemoveAssociationValue <String[]>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IpamCustomFieldAssociation** cmdlet modifies association of values for between two custom fields defined in IP Address Management (IPAM).
Specify the custom fields by using the **CustomFieldOne** and **CustomFieldTwo** parameters.
Specify the values to add or remove as an array of pairs of values in the format CustomFieldValue01,CustomFieldValue02.

The cmdlet removes values specified by the **RemoveAssociationValue** parameter, and then adds values specified by the **AddAssociationValue** parameter.
If you attempt to remove values that do not exist, the cmdlet returns an error, and does not make any changes.

Use the Get-IpamCustomFieldAssociation cmdlet to see existing associations.
Use the Add-IpamCustomFieldAssociation cmdlet to create associations.
Use the Remove-IpamCustomFieldAssociation cmdlet to remove associations.

## EXAMPLES

### Example 1: Modify an association
```
PS C:\> Set-IpamCustomFieldAssociation -CustomFieldOne "VmmLogicalNetwork" -CustomFieldTwo "NetworkSite" -AddAssociateValue "Storage:Site03" -RemoveAssociationValue "Public:Site03" -PassThru
CustomFieldOne   : VmmLogicalNetwork

CustomFieldTwo   : NetworkSite

AssociationValue : {Storage:Site01, Storage:Site03, Storage:Site02}
```

This command modifies an existing association between two custom fields, VmmLogicalNetwork and NetworkSite.
The command specifies values to add and remove.
The command includes the **PassThru** parameter, so it displays results to the console.

## PARAMETERS

### -AddAssociationValue
Specifies an array of value pairs.
Each pair, a string, includes two values that are separated by a colon (:).
The first value in a pair corresponds to the custom field that is specified by the **CustomFieldOne** parameter.
The second value corresponds to the custom field that is specified by the **CustomFieldTwo** parameter.

The cmdlet adds the specified pairs.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
This field corresponds to the first value in a pair specified by using the **AddAssociationValue** or **RemoveAssociationValue** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomFieldTwo
Specifies a custom field.
This field corresponds to the second value in a pair specified by using the **AddAssociationValue** or **RemoveAssociationValue** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

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

### -RemoveAssociationValue
Specifies an array of value pairs.
Each pair, a string, includes two values that are separated by a colon (:).
The first value in a pair corresponds to the custom field that is specified by the **CustomFieldOne** parameter.
The second value corresponds to the custom field that is specified by the **CustomFieldTwo** parameter.

The cmdlet removes the specified pairs.
If you specify a pair that does not exist, the cmdlet returns an error.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Add-IpamCustomFieldAssociation](./Add-IpamCustomFieldAssociation.md)

[Remove-IpamCustomFieldAssociation](./Remove-IpamCustomFieldAssociation.md)

