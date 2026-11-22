---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/enable-iissharedconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-IISSharedConfig
---

# Enable-IISSharedConfig

## SYNOPSIS
Enables shared configuration.

## SYNTAX

```
Enable-IISSharedConfig [-PhysicalPath] <String> [[-UserName] <String>] [[-Password] <SecureString>]
 [[-KeyEncryptionPassword] <SecureString>] [-DontCopyRemoteKeys] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-IISSharedConfig** cmdlet enables the IIS shared configuration feature.
Before enabling shared configuration, this operation backs up the keys.

You can disable shared configuration through IIS Manager or with the **Disable-IISSharedConfig** cmdlet.

## EXAMPLES

### Example 1: Enable shared configuration
```
PS C:\> $KeyEncryptionPassword = ConvertTo-SecureString -AsPlainText -String "SecurePa$$w0rd" -Force
#For automation scenarios
PS C:\> $KeyEncryptionPassword = Read-Host -AsSecureString
#For UI scenarios
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> Enable-IISSharedConfig -PhysicalPath "C:\export" -KeyEncryptionPassword $KeyEncryptionPassword -UserName "administrator" -Password $Password
```

Passwords must be in **SecureString** format.
The first command uses ConvertTo-SecureString to convert the specified password, and then stores it in the $KeyEncryptionPassword variable.
Using **ConvertTo-SecureString** is useful in automation scenarios.

The second command uses Read-Host to read console input for the key encryption password, and then stores it in the $KeyEncryptionPassword variable.
Using **Read-Host** is a more secure method for UI scenarios.

The third command uses **Read-Host** to get the password for the user account that has permission to perform the operation.

The fourth command enables shared configuration using the exported configuration and keys at C:\export.

### Example 2: Enable shared configuration without importing the keys
```
PS C:\> Enable-IISSharedConfig -PhysicalPath "C:\export" -DontCopyRemoteKeys
```

This command enables shared configuration, but does not import the keys into the local key store.

## PARAMETERS

### -DontCopyRemoteKeys
Indicates that IIS uses the currently active keys, and will try to use the configuration specified by the *PhysicalPath* parameter.
If this exported configuration has secrets encrypted with a different key, IIS will now be unable to decrypt these secrets.

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

### -KeyEncryptionPassword
Specifies the key encryption password for the exported keys.
This value is initially specified with the **Export-IISConfiguration** cmdlet or through IIS Manager.

*KeyEncryptionPassword* is required if you don't specify a value for *DontCopyRemoteKeys*.
If you specify a value for *DontCopyRemoteKeys*, you cannot use this parameter.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
Specifies the password of the account for accessing the physical location.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PhysicalPath
Specifies the location of the exported configuration and keys.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
Specifies the user name of the account to access the physical location.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Security.SecureString

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Disable-IISSharedConfig](./Disable-IISSharedConfig.md)

[Get-IISSharedConfig](./Get-IISSharedConfig.md)

