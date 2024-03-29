---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/show-adauthenticationpolicyexpression?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Show-ADAuthenticationPolicyExpression
---

# Show-ADAuthenticationPolicyExpression

## SYNOPSIS
Displays the Edit Access Control Conditions window update or create security descriptor definition language (SDDL) security descriptors.

## SYNTAX

### AllowedToAuthenticateFrom
```
Show-ADAuthenticationPolicyExpression [-WhatIf] [-Confirm] [-AllowedToAuthenticateFrom]
 [-AuthType <ADAuthType>] [-Credential <PSCredential>] [[-SDDL] <String>] [-Server <String>]
 [[-Title] <String>] [<CommonParameters>]
```

### AllowedToAuthenticateTo
```
Show-ADAuthenticationPolicyExpression [-WhatIf] [-Confirm] [-AllowedToAuthenticateTo] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [[-SDDL] <String>] [-Server <String>] [[-Title] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Show-ADAuthenticationPolicyExpression** cmdlet creates or modifies an SDDL security descriptor using the **Edit Access Control Conditions** window.

## EXAMPLES

### Example 1: Retrieve the AllowedToAuthenticateFrom settings and store in a file
```
PS C:\> Show-ADAuthenticationPolicyExpression -AllowedToAuthenticateFrom > someFile.txt 
PS C:\> New-ADAuthenticationPolicy -Name "TestAuthenticationPolicy" -UserAllowedToAuthenticateFrom (Get-Acl .\AuthSettings.txt).sddl
```

This command retrieves the AllowedToAuthenticateFrom access control list (ACL) by opening the **Edit Access Control Conditions** window and stores the ACL in a file named AuthSettings.txt.
The file is then used to apply a new authentication policy to the retrieved ACL.

### Example 2: Set the UserAllowedToAuthenticateFrom property
```
PS C:\> New-ADAuthenticationPolicy -Name "testAuthenticationPolicy" -UserAllowedToAuthenticateFrom (Show-ADAuthenticationPolicyExpression -AllowedToAuthenticateFrom)
```

This example uses the New-ADAuthenticationPolicy cmdlet to create an authentication policy, and then sets the **UserAllowedToAuthenticateFrom** property by specifying the **Show-ADAuthenticationPolicyExpression** cmdlet as the value for the parameter.

## PARAMETERS

### -AllowedToAuthenticateFrom
Indicates that the AllowedToAuthenticateFrom listings for an object are displayed in the **Edit Access Control Conditions** window.

```yaml
Type: SwitchParameter
Parameter Sets: AllowedToAuthenticateFrom
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowedToAuthenticateTo
Indicates that the **AllowedToAuthenticateTo** listings for an object are displayed in the **Edit Access Control Conditions** window.

```yaml
Type: SwitchParameter
Parameter Sets: AllowedToAuthenticateTo
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthType
Specifies the authentication method to use.
The acceptable values for this parameter are:

- Negotiate or 0
- Basic or 1

The default authentication method is Negotiate.
A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: Negotiate, Basic

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

### -Credential
Specifies a user account that has permission to perform the task.
The default is the current user.
Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the [Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936) cmdlet.

By default, the cmdlet uses the credentials of the currently logged on user unless the cmdlet is run from an Active Directory Domain Services Windows PowerShell provider drive.
If you run the cmdlet in an Active Directory provider drive, the account associated with the drive is the default.

If you specify credentials that do not have permission to perform the task, the cmdlet returns an error.

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

### -SDDL
Specifies the SDDL of the security descriptor.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to which to connect, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:  

Domain name values:

- A fully qualified domain name
- A NetBIOS name

Directory server values:  

- A fully qualified directory server name
- A NetBIOS name
- A fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the **Server** value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

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

### -Title
Specifies a title for the SDDL security descriptor.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or System.String
This cmdlet accepts a SDDL security descriptor.

## OUTPUTS

### System.Object
This cmdlet outputs a SDDL security descriptor.

## NOTES

## RELATED LINKS

[New-ADAuthenticationPolicy](./New-ADAuthenticationPolicy.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

