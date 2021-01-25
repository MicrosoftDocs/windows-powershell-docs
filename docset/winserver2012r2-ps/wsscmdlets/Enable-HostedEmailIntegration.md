---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Enable-HostedEmailIntegration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 98C2E743-5361-4386-8B81-A5E3F409978F
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Enable-HostedEmailIntegration

## SYNOPSIS
Enables the hosted email integration module.

## SYNTAX

```
Enable-HostedEmailIntegration [-AddInId] <Guid> [-AdminAccount] <String> [-Password] <SecureString>
 [-EnablePasswordSync] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-HostedEmailIntegration** cmdlet enables the hosted email integration module.
Run this cmdlet after you install the hosted email add-in.
The third-party hosted email provider builds the hosted email add-in on the Hosted Email Add-in Framework.

## EXAMPLES

### Example 1: Enable the hosted email integration module
```
PS C:\> $SecureString_pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force
PS C:\> Enable-HostedEmailIntegration -AddId 26a21bda-a627-11d7-9931-806e6f6e6963 -AdminAccount "HEadmin01" -Password $SecureString_pwd -EnablePasswordSync
```

The first command creates a password as a secure string for use in the second command.

The second command enables the hosted email integration module, specifying the administrator account to use and its password that was created in the previous step.

## PARAMETERS

### -AddInId
Specifies the GUID of the hosted email add-in to enable.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AdminAccount
Specifies the name of the administrator account for the hosted email service.

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

### -EnablePasswordSync
Indicates that the hosted email service enables password synchronization.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Password
Specifies the password, as a secure string, of the administration account for the hosted email service.
To obtain a secure string, use the ConvertTo-SecureStringhttp://go.microsoft.com/fwlink/?LinkID=113291 cmdlet.
For more information, type `Get-Help ConvertTo-SecureString`.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Guid,System.String,System.Security.SecureString,System.Management.Automation.SwitchParameter
AddInId
Type: System.Guid
Description: add-in ID for the hosted email integration

AdminAccount
Type: System.String
Description: name of the administrator account

Password
Type: System.Security.SecureString
Description: password of the administrator account

EnablePasswordSync
Type: System.Management.Automation.SwitchParameter
Description: whether to enable password synchronization feature

## OUTPUTS

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/?LinkID=113291)

