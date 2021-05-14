---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/enable-o365integration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-O365Integration
---

# Enable-O365Integration

## SYNOPSIS
Enables the office_365_2 Integration Module.

## SYNTAX

```
Enable-O365Integration [-O365AccountUPN] <String> [-Password] <SecureString> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-O365Integration** cmdlet enables integration between Windows Server Essentials and office_365_1 for an office_365_2 user.
After you enable the office_365_2 Integration Module, you can manage office_365_2 user accounts and licenses from the dashboard.

## EXAMPLES

### Example 1: Enable the Office 365 Integration Module
```
PS C:\> $SecureString_pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force
PS C:\> Enable-O365Integration -O365AccountUPN "Admin@Contoso.onmicrosoft.com" -Password $SecureString_pwd
Office 365 is now integrated with the server.
```

The first command converts the plain text string "P@ssW0rD!" into a secure string and stores the result in the $SecureString_pwd variable.

The second command enables integration between Windows Server Essentials and office_365_2 for the office_365_2 user account named Admin@Contoso.onmicrosoft.com, and the password created in the previous command.

## PARAMETERS

### -O365AccountUPN
The **Enable-O365Integration** cmdlet enables integration between wseblue_1 and office_365_1 for an office_365_2 user.
After you enable the office_365_2 Integration Module, you can manage office_365_2 user accounts and licenses from the dashboard.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Password
Specifies the password, as a secure string, for the user that you specify in the **O365AccountUPN** parameter.
To obtain a secure string, use the ConvertTo-SecureStringhttp://go.microsoft.com/fwlink/?LinkID=113291 cmdlet.
For more information, type `Get-Help ConvertTo-SecureString`.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String,System.Security.SecureString
O365AccountUPN
Type: System.String
Description: user principal name

Password
Type: System.Security.SecureString
Description: user password

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-O365Integration](./Disable-O365Integration.md)

