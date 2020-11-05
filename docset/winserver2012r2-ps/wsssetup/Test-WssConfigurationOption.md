---
external help file: Wssg.Setup.Commands.dll-Help.xml
online version: 
schema: 2.0.0
title: Test-WssConfigurationOption
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 4EB4FCD5-6CB3-4E15-B41B-5FFD93E203A8
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Test-WssConfigurationOption

## SYNOPSIS
Validates server name, domain name and domain administrator credentials.

## SYNTAX

### Credential (Default)
```
Test-WssConfigurationOption [-Credential <PSCredential>] [<CommonParameters>]
```

### ComputerName
```
Test-WssConfigurationOption [-Credential <PSCredential>] [-ComputerName <String>] -NetbiosName <String>
 [<CommonParameters>]
```

### AdminAccount
```
Test-WssConfigurationOption [-Credential <PSCredential>] [-ComputerName <String>] -NetbiosName <String>
 -NewAdminCredential <PSCredential> [<CommonParameters>]
```

## DESCRIPTION
The **Test-WssConfigurationOption** cmdlet validates server name, domain name and domain administrator credentials in Windows Server Essential Experience.

## EXAMPLES

### Example 1: Validate a server configuration
```
PS C:\> $PsCredential = Get-Credential
PS C:\> Test-WssConfigurationOption -NetbiosName "Contoso-dom" -ComputerName "Contoso-01" -Credential $PsCredential
```

The first command obtains a credential and stores the result in the **$PsCredential** variable.

The second command validates the configuration for a server named Contoso-01 in the NetBIOS domain named Contoso-dom.

## PARAMETERS

### -ComputerName
Specifies the name of the computer with which to work.

```yaml
Type: String
Parameter Sets: ComputerName, AdminAccount
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
The cmdlet uses the credential supplied by this parameter to connect to the server to test.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetbiosName
Specifies the NetBIOS name of the domain to which the computer being tested belongs.

```yaml
Type: String
Parameter Sets: ComputerName, AdminAccount
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewAdminCredential
Specifies a **PSCredential** object.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
The cmdlet validates the user name and password in the credential you supply, and then creates a new user account by using these credentials.

```yaml
Type: PSCredential
Parameter Sets: AdminAccount
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Boolean
This cmdlet generates a value of $True or $False to represent whether you can configure Windows Server Essential Experience on the target server by using the parameter values that you specify.

## NOTES

## RELATED LINKS

[Get-WssConfigurationStatus](./Get-WssConfigurationStatus.md)

[Remove-WssConfigurationData](./Remove-WssConfigurationData.md)

[Start-WssConfigurationService](./Start-WssConfigurationService.md)

[Test-WssPrecheckResult](./Test-WssPrecheckResult.md)

