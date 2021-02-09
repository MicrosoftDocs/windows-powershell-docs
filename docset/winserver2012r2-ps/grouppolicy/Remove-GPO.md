---
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
online version: 
schema: 2.0.0
title: Remove-GPO
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: A4E0066E-561E-4BD7-AA7F-3CF742AB36B2
---

# Remove-GPO

## SYNOPSIS
Deletes a GPO.

## SYNTAX

### ByGUID (Default)
```
Remove-GPO -Guid <Guid> [-Domain <String>] [-Server <String>] [-KeepLinks] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByName
```
Remove-GPO [-Name] <String> [-Domain <String>] [-Server <String>] [-KeepLinks] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Remove-GPO cmdlet removes the GPO container and data from the directory service and the system volume folder (SysVol).

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> Remove-GPO -guid 50cc3e45-0b14-46dd-8b4d-afa012bc331c -Domain contoso.com -KeepLinks
```

Description

-----------

Removes the GPO that has the GUID 50cc3e45-0b14-46dd-8b4d-afa012bc331c from the contoso.com domain.
Because the KeepLinks parameter is specified, links between the GPO and all sites, and links between the GPO and all containers in the domain are preserved.

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\> Remove-GPO -Name TestGPO
```

Description

-----------

Removes the "TestGPO" GPO from the domain of the user that is running the session (or, for startup and shutdown scripts, the domain of the computer).
Because the KeepLinks parameter is not specified, links between the GPO and all sites, and links between the GPO and all containers in the domain are deleted.

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

### -Domain
Specifies the domain in which you want to remove a GPO.
You must specify the fully qualified domain name (FQDN) of the domain (for example: SalesDomain.Contoso.com).

If you do not specify the Domain parameter, the domain of the computer that you are logged on to is used.

If you specify a domain that differs from the domain of your user object, a trust must exist between the domain from which you want to remove the GPO and the domain of your user object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DomainName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid
Specifies the GPO to delete by its globally unique identifier (GUID).
The GUID uniquely identifies the GPO.

You can also refer to the Guid parameter by its built-in alias, "id".
For more information, see about_Aliases.

```yaml
Type: Guid
Parameter Sets: ByGUID
Aliases: ID, GPOID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeepLinks
Preserves the links to the GPO in the specified domain (including OUs) and all sites when the GPO is removed.

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

### -Name
Specifies the GPO to delete by its display name.

The display name is not guaranteed to be unique in the domain.
If another GPO with the same display name exists in the domain an error occurs.
You can use the Guid parameter to uniquely identify a GPO.

You can also refer to the Name parameter by its built-in alias, "displayname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: ByName
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Server
Specifies the name of the domain controller that this cmdlet contacts to complete the operation.
You can specify either the fully qualified domain name (FQDN) or the host name.
For example:

FQDN: DomainController1.sales.contoso.com

Host Name: DomainController1

If you do not specify the name by using the Server parameter, the PDC emulator is contacted.

You can also refer to the Server parameter by its built-in alias, "dc".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DC

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

### Microsoft.GroupPolicy.Gpo
A GPO to be deleted.
Collections that contain GPOs from different domains are not supported.

## OUTPUTS

### None
This cmdlet does not output any objects.

## NOTES
* When you delete a GPO, by default, all links to that GPO in the domain of the GPO are deleted. To delete a link to a GPO, you must have permission to link Group Policy Objects for the organizational unit or domain. If you do not have rights to delete a link, the GPO is deleted, but the link remains. Links from other domains and sites are not deleted. The link to a deleted GPO appears in the GPMC as Not Found. To delete Not Found links, you must either have permission on the site, domain, or organizational unit containing the link, or ask someone with sufficient rights to delete it.

## RELATED LINKS

[Get-GPO](./Get-GPO.md)

[New-GPO](./New-GPO.md)

