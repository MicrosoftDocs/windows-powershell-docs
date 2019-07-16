---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: New-GPStarterGPO
ms.reviewer:
ms.assetid: FDF68866-CC12-4637-A83C-C13F8B6E243F
---

# New-GPStarterGPO

## SYNOPSIS
Creates a Starter GPO.

## SYNTAX

```
New-GPStarterGPO [-Name] <String> [-Comment <String>] [-Domain <String>] [-Server <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-GPStarterGPO** cmdlet creates a Starter GPO with the specified name.
If the Starter GPOs folder does not exist in the SYSVOL when the **New-GPStarterGPO** cmdlet is called, it is created and populated with the eight Starter GPOs that ship with Group Policy.

## EXAMPLES

### Example 1: Create a Starter GPO
```
PS C:\> New-GPStarterGPO -Name StarterSecurity -Comment "Security Template"
```

This command creates a Starter GPO with the display name StarterSecurity.
The Starter GPO is annotated with the specified comment.

## PARAMETERS

### -Comment
Specifies a comment for the new Starter GPO.
The comment string must be enclosed in double-quotation marks or single-quotation marks and can contain a maximum of 2,047 characters.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

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

### -Domain
Specifies the domain for this cmdlet.
You must specify the fully qualified domain name (FQDN) of the domain.

Cross-domain creation of Starter GPOs is not supported.
If you specify a domain that is different from the domain of the user that is running the current session, an error occurs.

If you do not specify the *Domain* parameter, the domain of the user that is running the current session is used.

You can also refer to the *Domain* parameter by its built-in alias, domainname.
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DomainName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the display name for the new Starter GPO.

If another Starter GPO with the same display name exists in the domain, an error occurs.

You can also refer to the *Name* parameter by its built-in alias, displayname.
For more information, see **about_Aliases**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the name of the domain controller that this cmdlet contacts to complete the operation.
You can specify either the fully qualified domain name (FQDN) or the host name.

If you do not specify the name by using the *Server* parameter, the primary domain controller (PDC) emulator is contacted.

You can also refer to the *Server* parameter by its built-in alias, dc.
For more information, see **about_Aliases**.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet does not accept any input.

## OUTPUTS

### Microsoft.GroupPolicy.StarterGpo
This cmdlet returns the Starter GPO that was created.

## NOTES

## RELATED LINKS

[Get-GPStarterGPO](./Get-GPStarterGPO.md)

[New-GPO](./New-GPO.md)

