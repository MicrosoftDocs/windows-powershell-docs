---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/export-iisconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-IISConfiguration
---

# Export-IISConfiguration

## SYNOPSIS
Exports the IIS configuration and machine keys.

## SYNTAX

```
Export-IISConfiguration [-PhysicalPath] <String> [[-UserName] <String>] [[-Password] <SecureString>]
 [[-KeyEncryptionPassword] <SecureString>] [-DontExportKeys] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Export-IISConfiguration** cmdlet exports the IIS configuration and machine keys to a specified location.

The exported configuration is available only to administrators through the access control list (ACL).

You can encrypt the machine keys with the *KeyEncryptionPassword* parameter.

You must supply a valid username and password to access the export location.
If you do not want to export the keys, specify the *DontExportKeys* parameter.

## EXAMPLES

### Example 1: Export a configuration
```
PS C:\> $KeyEncryptionPassword = ConvertTo-SecureString -AsPlainText -String "SecurePa$$w0rd" -Force
#Automation scenarios
PS C:\> $KeyEncryptionPassword = Read-Host -AsSecureString
#UI scenarios
PS C:\> Export-IISConfiguration -PhysicalPath "C:\export" -KeyEncryptionPassword $keyEncryptionPassword
PS C:\> Export-IISConfiguration -PhysicalPath "C:\export" -DontExportKeys -Force
```

Passwords must be in **SecureString** format.
The first command uses ConvertTo-SecureString to convert the specified password, and then stores it in the $KeyEncryptionPassword variable.
Using **ConvertTo-SecureString** is useful in automation scenarios.

The second command uses Read-Host to read console input for the key encryption password, and then stores it in the $KeyEncryptionPassword variable.
Using **Read-Host** is a more secure method for UI scenarios.

The third command exports the keys and configuration to C:\export, and encrypts the key with the specified password.

The fourth command exports the configuration without the keys.
Because the *Force* parameter is specified, this command overwrites the previous configuration.
The exported keys in C:\export are not deleted.

## PARAMETERS

### -DontExportKeys
Indicates that this operation does not export the keys.

To enable the IIS shared configuration feature with this exported configuration, run the **Enable-IISSharedConfig** cmdlet with the *DontCopyRemoteKeys* switch parameter.

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

You can use this value with Enable-IISSharedConfig to enable shared configuration with the configuration that this cmdlet exports.

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
Specifies the location to which to export the configuration and  keys.

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

