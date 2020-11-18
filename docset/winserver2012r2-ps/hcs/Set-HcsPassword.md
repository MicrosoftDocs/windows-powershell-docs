---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-HcsPassword
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 6AE90E8A-F16B-4010-AA62-FC87E15406C7
---

# Set-HcsPassword

## SYNOPSIS
Sets the password for a user account.

## SYNTAX

```
Set-HcsPassword -User <HcsUser> -Password <SecureString> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HcsPassword** cmdlet sets the password for a specified user account.

The password must meet the following requirements for password complexity: 

- SSAdmin.
Minimum of eight characters and maximum of 15 characters.
Use this type of account to access Windows PowerShell Interface for StorSimple. 
- SnapShotManager.
Minimum of 14 characters and maximum of 15 characters.
Use this type of account to access for StorSimple SnapShot Manager.

Passwords must contain characters from at least three of the following classes: 

- English upper case letters: A, B, C, ...Z 
- English lower case letters: a, b, c, ...z 
- Westernized Arabic numerals: 0, 1, 2, ...9 
- Non-alphanumeric special characters, such as ?, !, %, $, #

## EXAMPLES

### Example 1: Set a password for a user
```
PS C:\> Set-HcsPassword -User ApplicationHost
WARNING: A script or application on the 10.111.172.232 remote computer is 
sending a prompt request. When prompted, enter sensitive information such as 
credentials or password only if you trust the remote computer and the 
application or script requesting it.

cmdlet Set-HcsPassword at command pipeline position 1
Supply values for the following parameters:
Password: ***************

WARNING: A script or application on the 10.111.172.232 remote computer is 
sending a prompt request. When prompted, enter sensitive information such as 
credentials or password only if you trust the remote computer and the 
application or script requesting it.
Confirm Password: ***************

Changing your application host password will interrupt connectivity from the 
StorSimple Snapshot Manager to this device until you update the StorSimple 
Snapshot Manager with the new application host password. Are you sure you wish 
to continue?
[Y] Yes  [N] No  [?] Help (default is "Y"): y
```

This command sets the password that StorSimple SnapShot Manager uses to connect to the device.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

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

### -Password
Specifies a password.
Specify a secure string for this parameter.
To obtain a secure string, use the ConvertTo-SecureStringhttp://go.microsoft.com/fwlink/?LinkID=113291 cmdlet.
For more information, type `Get-Help ConvertTo-SecureString`.
The cmdlet sets the password that you specify.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies the user name for which to change the password.

```yaml
Type: HcsUser
Parameter Sets: (All)
Aliases: 
Accepted values: SSAdmin, SnapshotManager

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

###  
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/?LinkID=113291)

