---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Remove-O365User
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 2DB68198-49CB-4441-8900-1BE69F0BDF20
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-O365User

## SYNOPSIS
Removes an office_365_2 account that is assigned to a local user account.

## SYNTAX

```
Remove-O365User [-LocalAccountName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-O365User** cmdlet removes a office_365_1 account that is assigned to a local user account.

## EXAMPLES

### Example 1: Remove an office_365_2 accountoffice_365_2
```
PS C:\> Remove-O365User -LocalAccountName "PattiFuller"
The Office 365 account was removed.
```

This command removes the office_365_2 account that is assigned to the local user account named PattiFuller.

### 1:
```
PS C:\>
```

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

### -LocalAccountName
Specifies the name of a local Active Directory user account.
The cmdlet removes the office_365_1 account that is assigned to the local user account that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### System.String
LocalAccountName
Type: System.String
Description: local user name

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-O365User](./Get-O365User.md)

[Add-O365User](./Add-O365User.md)

[Enable-O365User](./Enable-O365User.md)

[Disable-O365User](./Disable-O365User.md)

