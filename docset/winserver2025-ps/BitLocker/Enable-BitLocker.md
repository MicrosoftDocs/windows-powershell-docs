---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BitLocker-help.xml
Module Name: BitLocker
ms.date: 12/14/2021
online version: https://learn.microsoft.com/powershell/module/bitlocker/enable-bitlocker?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-BitLocker
---

# Enable-BitLocker

## SYNOPSIS

Enables BitLocker Drive Encryption for a volume.

## SYNTAX

### PasswordProtector

```PowerShell
Enable-BitLocker [-MountPoint] <String[]> -PasswordProtector [-Password] <SecureString>
[-EncryptionMethod <BitLockerVolumeEncryptionMethodOnEnable>] [-HardwareEncryption]
[-SkipHardwareTest] [-UsedSpaceOnly][-WhatIf] [-Confirm] [<CommonParameters>]
```

### RecoveryPasswordProtector

```PowerShell
Enable-BitLocker [-MountPoint] <String[]> -RecoveryPasswordProtector [[-RecoveryPassword] <String>]
[-EncryptionMethod <BitLockerVolumeEncryptionMethodOnEnable>] [-HardwareEncryption]
[-SkipHardwareTest] [-UsedSpaceOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StartupKeyProtector

```PowerShell
Enable-BitLocker [-MountPoint] <String[]> -StartupKeyProtector [-StartupKeyPath] <String>
[-EncryptionMethod <BitLockerVolumeEncryptionMethodOnEnable>] [-HardwareEncryption]
[-SkipHardwareTest] [-UsedSpaceOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TpmAndStartupKeyProtector

```PowerShell
Enable-BitLocker [-MountPoint] <String[]> -TpmAndStartupKeyProtector [-StartupKeyPath] <String>
[-EncryptionMethod <BitLockerVolumeEncryptionMethodOnEnable>] [-HardwareEncryption]
[-SkipHardwareTest] [-UsedSpaceOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TpmAndPinAndStartupKeyProtector

```PowerShell
Enable-BitLocker [-MountPoint] <String[]> -TpmAndPinAndStartupKeyProtector -StartupKeyPath <String>
[-Pin] <SecureString> [-EncryptionMethod <BitLockerVolumeEncryptionMethodOnEnable>]
[-HardwareEncryption] [-SkipHardwareTest] [-UsedSpaceOnly] [-WhatIf] [-Confirm]
[<CommonParameters>]
```

### AdAccountOrGroupProtector

```PowerShell
Enable-BitLocker [-MountPoint] <String[]> -AdAccountOrGroupProtector [-AdAccountOrGroup] <String>
[-Service] [-EncryptionMethod <BitLockerVolumeEncryptionMethodOnEnable>] [-HardwareEncryption]
[-SkipHardwareTest] [-UsedSpaceOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TpmAndPinProtector

```PowerShell
Enable-BitLocker [-MountPoint] <String[]> -TpmAndPinProtector [-Pin] <SecureString>
[-EncryptionMethod <BitLockerVolumeEncryptionMethodOnEnable>] [-HardwareEncryption]
[-SkipHardwareTest] [-UsedSpaceOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TpmProtector

```PowerShell
Enable-BitLocker [-MountPoint] <String[]> -TpmProtector
[-EncryptionMethod <BitLockerVolumeEncryptionMethodOnEnable>] [-HardwareEncryption]
[-SkipHardwareTest] [-UsedSpaceOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RecoveryKeyProtector

```PowerShell
Enable-BitLocker [-MountPoint] <String[]> -RecoveryKeyProtector [-RecoveryKeyPath] <String>
[-EncryptionMethod <BitLockerVolumeEncryptionMethodOnEnable>] [-HardwareEncryption]
[-SkipHardwareTest] [-UsedSpaceOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The **Enable-BitLocker** cmdlet enables BitLocker Drive Encryption for a volume.

When you enable encryption, you must specify a volume, either by its drive letter or by its
BitLocker volume object.

You must also establish a key protector. BitLocker uses a key protector to encrypt the volume
encryption key. When a user accesses a BitLocker encrypted drive, such as when starting a computer,
BitLocker requests the relevant key protector. For example, the user can enter a PIN or provide a
USB drive that contains a key. BitLocker decrypts the encryption key and uses it to read data from
the drive. You can use one of the following methods or combinations of methods for a key protector:

- **Trusted Platform Module (TPM):** BitLocker uses the computer's TPM to protect the encryption
  key. If you select this key protector, users can access the encrypted drive as long as it is
  connected to the system board that hosts the TPM and system boot integrity is intact. In general,
  TPM-based protectors can only be associated to an operating system volume.

- **TPM and Personal Identification Number (PIN):** BitLocker uses a combination of the TPM and a
  user-supplied PIN. A PIN is four to twenty digits or, if you allow enhanced PINs, is four to
  twenty letters, symbols, spaces, or numbers.

- **TPM, PIN, and startup key:** BitLocker uses a combination of the TPM, a user-supplied PIN, and
  input from of a USB memory device that contains an external key.

- **TPM and startup key:** BitLocker uses a combination of the TPM and a USB flash drive that
  contains the external key.

- **Startup key:** BitLocker uses a USB flash drive that contains the external key.

- **Password:** BitLocker uses a password.

- **Recovery key:** BitLocker uses a recovery key stored as a specified file.

- **Recovery password:** BitLocker uses a recovery password.

- **Active Directory Domain Services (AD DS) account:** BitLocker uses domain authentication.

You can specify only one of these methods or combinations when you enable encryption, but you can
use the **Add-BitLockerKeyProtector** cmdlet to add other protectors.

For a password or PIN key protector, specify a secure string. You can use the
**ConvertTo-SecureString** cmdlet to create a secure string. You can use secure strings in a script
and still maintain confidentiality of passwords.

We strongly recommend specifying the encryption method. By default, BitLocker uses XTS-AES-128. You
can opt XTS-AES-256 for stronger security. However, if you are encrypting a removable media and
intend to use it on Windows 8.1 or Windows Server 2012 R2, you must opt either AES-128 or AES-256
for backward compatibility. You may request hardware encryption but we strongly advise
against it. For further guidance, see the
[ADV180028 Security Advisory](https://msrc.microsoft.com/update-guide/vulnerability/ADV180028).

This cmdlet returns a BitLocker volume object. If you choose recovery password as your key protector
but do not specify a 48-digit recovery password, this cmdlet generates a random one for you, and
stores it in the **RecoveryPassword** field of the **KeyProtector** attribute of the BitLocker
volume object.

If you use startup key or recovery key as part of your key protector, provide a path to store the
key. This cmdlet stores the name of the file that contains the key in the **KeyFileName** field of
the **KeyProtector** field in the BitLocker volume object.

If you use the **Enable-BitLocker** cmdlet on an encrypted volume or on a volume with
encryption in process, it takes no action. If you use the cmdlet on a drive that has encryption
paused, it resumes encryption on the volume.

By default, this cmdlet encrypts the entire drive. If you use the *UsedSpaceOnly* parameter, it only
encrypts the used space on the disk. This option can significantly reduce encryption time.

It is common practice to add a recovery password for an operating system volume using the
**Add-BitLockerKeyProtector** cmdlet, save the recovery password using the
**Backup-BitLockerKeyProtector** cmdlet, and then enable BitLocker on that volume. This procedure
ensures that you have a recovery option.

For an overview of BitLocker, see the
[BitLocker Drive Encryption Overview](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732774(v=ws.11)).

## EXAMPLES

### Example 1: Enable BitLocker

```PowerShell
$SecureString = ConvertTo-SecureString "1234" -AsPlainText -Force
Enable-BitLocker -MountPoint "C:" -EncryptionMethod Aes256 -UsedSpaceOnly -Pin $SecureString -TPMandPinProtector
```

This example enables BitLocker for a specified drive using the TPM and a PIN for key protector.

The first command uses the **ConvertTo-SecureString** cmdlet to create a secure string that contains a PIN and saves that string in the $SecureString variable.
For more information about the **ConvertTo-SecureString** cmdlet, type `Get-Help ConvertTo-SecureString`.

The second command enables BitLocker encryption for the BitLocker volume that has the drive letter C:.
The cmdlet specifies an encryption algorithm and the PIN saved in the $SecureString variable.
The command also specifies that this volume uses a combination of the TPM and the PIN as key protector.
The command also specifies to encrypt the used space data on the disk, instead of the entire volume.
When the system writes data to the volume in the future, that data is encrypted.

### Example 2: Enable BitLocker with a recovery key

```PowerShell
Get-BitLockerVolume | Enable-BitLocker -EncryptionMethod Aes128 -RecoveryKeyPath "E:\Recovery\" -RecoveryKeyProtector
```

This command gets all the BitLocker volumes for the current computer and passes pipes them to the **Enable-BitLocker** cmdlet by using the pipe operator.
This cmdlet specifies an encryption algorithm for the volume or volumes.
This cmdlet specifies a path to a folder where the randomly generated recovery key will be stored and indicates that these volumes use a recovery key as a key protector.

### Example 3: Enable BitLocker with a specified user account

```PowerShell
Enable-BitLocker -MountPoint "C:" -EncryptionMethod Aes128 -AdAccountOrGroup "Western\SarahJones" -AdAccountOrGroupProtector
```

This command encrypts the BitLocker volume specified by the *MountPoint* parameter, and uses the AES 128 encryption method.
The command also specifies an account and specifies that BitLocker uses user credentials as a key protector.
When a user accesses this volume, BitLocker prompts for credentials for the user account Western\SarahJones.

## PARAMETERS

### -AdAccountOrGroup

Specifies an account using the format Domain\User.
This cmdlet adds the account you specify as a key protector for the volume encryption key.

```yaml
Type: String
Parameter Sets: AdAccountOrGroupProtector
Aliases: sid

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdAccountOrGroupProtector

Indicates that BitLocker uses an AD DS account as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: AdAccountOrGroupProtector
Aliases: sidp

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

### -EncryptionMethod

Specifies an encryption method for the encrypted drive. For further guidance, see the
[ADV180028 Security Advisory](https://msrc.microsoft.com/update-guide/vulnerability/ADV180028).

```yaml
Type: BitLockerVolumeEncryptionMethodOnEnable
Parameter Sets: (All)
Aliases:
Accepted values: Aes128, Aes256, XtsAes128, XtsAes256

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HardwareEncryption

Indicates that the volume uses hardware encryption. We strongly advise against hardware encryption.
For further guidance, see the
[ADV180028 Security Advisory](https://msrc.microsoft.com/update-guide/vulnerability/ADV180028).

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

### -MountPoint

Specifies an array of drive letters or BitLocker volume objects.
This cmdlet enables protection for the volumes specified.
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

Specifies a secure string object that contains a password.
The password specified acts as a protector for the volume encryption key.

```yaml
Type: SecureString
Parameter Sets: PasswordProtector
Aliases: pw

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PasswordProtector

Indicates that BitLocker uses a password as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: PasswordProtector
Aliases: pwp

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pin

Specifies a secure string object that contains a PIN.
BitLocker uses the PIN specified, with other data, as a protector for the volume encryption key.

```yaml
Type: SecureString
Parameter Sets: TpmAndPinAndStartupKeyProtector, TpmAndPinProtector
Aliases: p

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryKeyPath

Specifies a path to a folder.
This cmdlet adds a randomly generated recovery key as a protector for the volume encryption key and stores it in the specified path.

```yaml
Type: String
Parameter Sets: RecoveryKeyProtector
Aliases: rk

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryKeyProtector

Indicates that BitLocker uses a recovery key as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: RecoveryKeyProtector
Aliases: rkp

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPassword

Specifies a recovery password.
If you do not specify this parameter, but you do include the *RecoveryPasswordProtector* parameter, the cmdlet creates a random password.
You can enter a 48-digit password.
The password specified or created acts as a protector for the volume encryption key.

```yaml
Type: String
Parameter Sets: RecoveryPasswordProtector
Aliases: rp

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPasswordProtector

Indicates that BitLocker uses a recovery password as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: RecoveryPasswordProtector
Aliases: rpp

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Service

Indicates that the system account for this computer unlocks the encrypted volume.

```yaml
Type: SwitchParameter
Parameter Sets: AdAccountOrGroupProtector
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipHardwareTest

Indicates that BitLocker does not perform a hardware test before it begins encryption.
BitLocker uses a hardware test as a dry run to make sure that all the key protectors are correctly set up and that the computer can start without issues.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: s

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupKeyPath

Specifies a path to a startup key.
The key stored in the specified path acts as a protector for the volume encryption key.

```yaml
Type: String
Parameter Sets: StartupKeyProtector, TpmAndStartupKeyProtector, TpmAndPinAndStartupKeyProtector
Aliases: sk

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupKeyProtector

Indicates that BitLocker uses a startup key as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: StartupKeyProtector
Aliases: skp

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TpmAndPinAndStartupKeyProtector

Indicates that BitLocker uses a combination of the TPM, a PIN, and a startup key as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: TpmAndPinAndStartupKeyProtector
Aliases: tpskp

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TpmAndPinProtector

Indicates that BitLocker uses a combination of the TPM and a PIN as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: TpmAndPinProtector
Aliases: tpp

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TpmAndStartupKeyProtector

Indicates that BitLocker uses a combination of the TPM and a startup key as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: TpmAndStartupKeyProtector
Aliases: tskp

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TpmProtector

Indicates that BitLocker uses the TPM as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: TpmProtector
Aliases: tpmp

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsedSpaceOnly

Indicates that BitLocker does not encrypt unallocated disk space.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: qe

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

### BitLockerVolume[], String[]

## OUTPUTS

### BitLockerVolume[]

## NOTES

## RELATED LINKS

[Disable-BitLocker](./Disable-BitLocker.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

[Lock-BitLocker](./Lock-BitLocker.md)

[Resume-BitLocker](./Resume-BitLocker.md)

[Suspend-BitLocker](./Suspend-BitLocker.md)

[Unlock-BitLocker](./Unlock-BitLocker.md)
