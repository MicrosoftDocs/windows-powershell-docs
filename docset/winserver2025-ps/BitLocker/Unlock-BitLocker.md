---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BitLocker-help.xml
Module Name: BitLocker
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/bitlocker/unlock-bitlocker?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Unlock-BitLocker
---

# Unlock-BitLocker

## SYNOPSIS
Restores access to data on a BitLocker volume.

## SYNTAX

### OnlyPasswordParameterSet
```
Unlock-BitLocker [-MountPoint] <String[]> -Password <SecureString> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### OnlyRecoveryPasswordParameterSet
```
Unlock-BitLocker [-MountPoint] <String[]> -RecoveryPassword <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### OnlyRecoveryKeyParameterSet
```
Unlock-BitLocker [-MountPoint] <String[]> -RecoveryKeyPath <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### OnlyAdAccountOrGroupParameterSet
```
Unlock-BitLocker [-MountPoint] <String[]> [-AdAccountOrGroup] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Unlock-BitLocker** cmdlet restores access to encrypted data on a volume that uses BitLocker Drive Encryption.
You can use the **Lock-BitLocker** cmdlet to prevent access.

In order to restore access, provide one of the following key protectors for the volume:

- Active Directory Domain Services (AD DS) account
- Password
- Recovery key
- Recovery password

For an overview of BitLocker, see [BitLocker Drive Encryption Overview](https://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Unlock a volume
```
PS C:\> $SecureString = ConvertTo-SecureString "fjuksAS1337" -AsPlainText -Force
PS C:\> Unlock-BitLocker -MountPoint "E:" -Password $SecureString
```

This example unlocks a specified BitLocker volume by using a password.

The first command uses the **ConvertTo-SecureString** cmdlet to create a secure string that contains a password and saves it in the $SecureString variable.
For more information about the **ConvertTo-SecureString** cmdlet, type `Get-Help ConvertTo-SecureString`.

The second command unlocks the specified BitLocker volume by using the password saved in the $SecureString variable.

## PARAMETERS

### -AdAccountOrGroup
Indicates that BitLocker requires account credentials to unlock the volume.
In order to use this parameter, the account for the current user must be a key protector for the volume.

```yaml
Type: SwitchParameter
Parameter Sets: OnlyAdAccountOrGroupParameterSet
Aliases:

Required: True
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

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
The cmdlet unlocks the volumes specified.
To obtain a BitLocker volume object, use the **Get-BitLockerVolume** cmdlet.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Password
Specifies a secure string that contains a password.
The password specified acts as a protector for the volume encryption key.

```yaml
Type: SecureString
Parameter Sets: OnlyPasswordParameterSet
Aliases: pw

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryKeyPath
Specifies the path to a folder where recovery keys are stored.
The key stored in the specified path, if found, acts as a protector for the volume encryption.

```yaml
Type: String
Parameter Sets: OnlyRecoveryKeyParameterSet
Aliases: rk

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPassword
Specifies a recovery password.
The password specified acts as a protector for the volume encryption key.

```yaml
Type: String
Parameter Sets: OnlyRecoveryPasswordParameterSet
Aliases: rp

Required: True
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

### BitLockerVolume[], String[]

## OUTPUTS

### BitLockerVolume[]

## NOTES

## RELATED LINKS

[Disable-BitLocker](./Disable-BitLocker.md)

[Enable-BitLocker](./Enable-BitLocker.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

[Lock-BitLocker](./Lock-BitLocker.md)

[Resume-BitLocker](./Resume-BitLocker.md)

[Suspend-BitLocker](./Suspend-BitLocker.md)

