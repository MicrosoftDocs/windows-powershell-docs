---
external help file: Bitlocker_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: A2806C1A-0703-4800-9356-7F3B4ADE9659
manager: dansimp
---

# Unlock-BitLocker

## SYNOPSIS
Restores access to data on a BitLocker volume.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Unlock-BitLocker [-AdAccountOrGroup] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Unlock-BitLocker [-MountPoint] <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Unlock-BitLocker -Password <SecureString> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Unlock-BitLocker -RecoveryKeyPath <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Unlock-BitLocker -RecoveryPassword <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Unlock-BitLocker** cmdlet restores access to encrypted data on a volume that uses BitLocker Drive Encryption.
You can use the Lock-BitLocker cmdlet to prevent access.

In order to restore access, provide one of the following key protectors for the volume: 

- Active Directory Domain Services (AD DS) account
- Password
- Recovery key
- Recovery password

For an overview of BitLocker, see BitLocker Drive Encryption Overviewhttp://technet.microsoft.com/en-us/library/cc732774.aspx (http://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Unlock a volume
```
PS C:\> $SecureString = ConvertTo-SecureString "fjuksAS1337" -AsPlainText -Force PS C:\>Unlock-BitLocker -MountPoint "E:" -Password $SecureString
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
The cmdlet unlocks the volumes specified.
To obtain a BitLocker volume object, use the Get-BitLockerVolume cmdlet.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Password
Specifies a secure string that contains a password.
The password specified acts as a protector for the volume encryption key.

```yaml
Type: SecureString
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: rp

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### BitLockerVolume[], String[]

## OUTPUTS

### BitLockerVolume[]

## NOTES

## RELATED LINKS

[Disable-BitLocker](./Disable-BitLocker.md)

[Enable-BitLocker](./Enable-BitLocker.md)

[Lock-BitLocker](./Lock-BitLocker.md)

[Resume-BitLocker](./Resume-BitLocker.md)

[Suspend-BitLocker](./Suspend-BitLocker.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

