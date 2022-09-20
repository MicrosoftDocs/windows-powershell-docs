---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/enable-wssmsointegration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WssMsoIntegration
---

# Enable-WssMsoIntegration

## SYNOPSIS
Enables aad_2 integration.

## SYNTAX

```
Enable-WssMsoIntegration [-MsoUserName] <String> [-Password] <SecureString> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WssMsoIntegration** cmdlet enables integration between Windows Server Essentials and aad_1.
You must integrate these two products before you can further integrate Windows Server Essentials with office_365_1 and wit_1.

## EXAMPLES

### Example 1: Enable integration
```
PS C:\> $Password = ConvertTo-SecureString "PassWord1" -AsPlainText -Force 
PS C:\> Enable-WssMsoIntegration -MsoUserName "PattiFuller@TSQA.Contoso.com" -Password $Password
```

This example enables integration between Windows Server Essentials and aad_2.
To enable integration, supply an online service account and a secure string that contains the password for that account.

The first command creates a secure string by using the ConvertTo-SecureStringhttp://go.microsoft.com/fwlink/?LinkID=113291 cmdlet, and then stores it in the **$Password** variable.
For more information, type `Get-Help ConvertTo-SecureString`.

The second command enables integration.
The command specifies the UPN of the online service account and the password stored in the **$Password** variable.

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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MsoUserName
Specifies the user principal name (UPN) of the account with administrator permissions that is to be used to manage the online user accounts.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Password
Specifies a password for a user, as a secure string.
To obtain a secure string, use the ConvertTo-SecureStringhttp://go.microsoft.com/fwlink/?LinkID=113291 cmdlet.
For more information, type `Get-Help ConvertTo-SecureString`.
The password that you specify belongs to the online service account specified by the **MsoUserName** parameter.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
The MsoUserName in UPN form for the administrator account to be used to administer the online user accounts.

## OUTPUTS

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/?LinkID=113291)

[Disable-WssMsoIntegration](./Disable-WssMsoIntegration.md)

