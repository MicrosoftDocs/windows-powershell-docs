---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adaccountauthenticationpolicysilo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADAccountAuthenticationPolicySilo
---

# Set-ADAccountAuthenticationPolicySilo

## SYNOPSIS
Modifies the authentication policy or authentication policy silo of an account.

## SYNTAX

```
Set-ADAccountAuthenticationPolicySilo [-WhatIf] [-Confirm] [-AuthenticationPolicy <ADAuthenticationPolicy>]
 [-AuthenticationPolicySilo <ADAuthenticationPolicySilo>] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADAccount> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADAccountAuthenticationPolicySilo** cmdlet modifies the authentication policy or authentication policy silo of an account.
This cmdlet assigns authentication policy silo objects and authentication policy object to an Active Directory Domain Services account.
In order for the account to belong to an authentication policy silo, you must use the **Grant-ADAuthenticationPolicySiloAccess** cmdlet to grant access to the object.

The *Identity* parameter specifies the Active Directory Domain Services authentication policy to modify.
You can identify an authentication policy by its distinguished name, GUID or name.
You can also use the *Identity* parameter to specify a variable that contains an authentication policy object, or you can use the pipeline operator to pass an authentication policy object to the *Identity* parameter.

## EXAMPLES

### Example 1: Assign an authentication policy silo and authentication policy
```
PS C:\> Set-ADAccountAuthenticationPolicySilo -Identity User01 -AuthenticationPolicySilo AuthenticationPolicySilo01 -AuthenticationPolicy AuthenticationPolicy01
```

This example assigns the authentication policy silo named AuthenticationPolicySilo01 and the authentication policy named AuthenticationPolicy01 to the user account named User01.

### Example 2: Assign an authentication policy silo and authentication policy by using a filter
```
PS C:\> Get-ADComputer -Filter 'Name -like "NewComputer*"' | Set-ADAccountAuthenticationPolicySilo -AuthenticationPolicySilo AuthenticationPolicySilo02 -AuthenticationPolicy AuthenticationPolicy02
```

This example first uses the **Get-ADComputer** cmdlet to get all computer accounts that match the filter specified by the Filter parameter.
The output of this command is passed to **Set-ADAccountAuthenticationPolicySilo** to assign the authentication policy silo named AuthenticationPolicySilo02 and the authentication policy named AuthenticationPolicy02 to them.

## PARAMETERS


### -AuthenticationPolicy
Specifies an Active Directory Domain Services authentication policy object.
Specify the authentication policy object in one of the following formats:

- A distinguished name
- GUID
- Name

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

The cmdlet searches the default naming context or partition to find the object.
If the cmdlet finds two or more objects, the cmdlet returns a non-terminating error.

```yaml
Type: ADAuthenticationPolicy
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationPolicySilo
Specifies an Active Directory Domain Services authentication policy silo object.
Specify the authentication policy silo object in one of the following formats:

- A distinguished name
- GUID
- Name

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

The cmdlet searches the default naming context or partition to find the object.
If the cmdlet finds two or more objects, the cmdlet returns a non-terminating error.

```yaml
Type: ADAuthenticationPolicySilo
Parameter Sets: (All)
Aliases:

Required: False
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
Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the **Get-Credential** cmdlet.

By default, the cmdlet uses the credentials of the currently logged on user unless the cmdlet is run from an Active Directory Domain Services Windows PowerShell provider drive.
If you run the cmdlet in a provider drive, the account associated with the drive is the default.

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

### -Identity
Specifies an Active Directory Domain Services object.
Specify the Active Directory Domain Services object in one of the following formats:

- distinguished name
- GUID
- Name

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

The cmdlet searches the default naming context or partition to find the object.
If the cmdlet finds two or more objects, the cmdlet returns a non-terminating error.

```yaml
Type: ADAccount
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -Server
Specifies the Active Directory Domain Services instance to which to connect, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
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

### Microsoft.ActiveDirectory.Management.ADAccount

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Grant-ADAuthenticationPolicySiloAccess](./Grant-ADAuthenticationPolicySiloAccess.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

