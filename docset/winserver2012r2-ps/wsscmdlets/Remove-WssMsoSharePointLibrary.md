---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/remove-wssmsosharepointlibrary?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WssMsoSharePointLibrary
---

# Remove-WssMsoSharePointLibrary

## SYNOPSIS
Removes a sp_online_2 library.

## SYNTAX

```
Remove-WssMsoSharePointLibrary [-Library] <SharePointLibrary> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssMsoSharePointLibrary** cmdlet removes a sp_online_1 library.
A office_365_1 site stores the sp_online_2 library.

## EXAMPLES

### Example 1: Remove a SharePoint library
```
PS C:\> $Library = Get-WssMsoSharePointLibrary | Select-Object -First 1
PS C:\> Remove-WssMsoSharePointLibrary -Library $Library
```

The first command uses the Get-WssMsoSharePointLibrary cmdlet to get a library, and stores the result in the $Library variable.

The second command removes the library named $Library.

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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Library
Specifies a sp_online_2 library object.
The cmdlet removes the library that you specify.

```yaml
Type: SharePointLibrary
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### Microsoft.WindowsServerSolutions.O365Integration.SharePointLibrary
Library

Type: Microsoft.WindowsServerSolutions.O365Integration.SharePointLibrary

Description: SharePoint library

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMsoSharePointLibrary](./Get-WssMsoSharePointLibrary.md)

[New-WssMsoSharePointLibrary](./New-WssMsoSharePointLibrary.md)

[Set-WssMsoSharePointLibrary](./Set-WssMsoSharePointLibrary.md)

