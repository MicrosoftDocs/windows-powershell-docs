---
external help file: Bitlocker_Cmdlets.xml
Module Name: BitLocker
online version: https://docs.microsoft.com/powershell/module/bitlocker/add-bitlockerkeyprotector?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-BitLockerKeyProtector

## SYNOPSIS
Adds a key protector for a BitLocker volume.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-BitLockerKeyProtector [-ADAccountOrGroup] <String> [-Service] [-ADAccountOrGroupProtector] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-BitLockerKeyProtector [-MountPoint] <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-BitLockerKeyProtector [[-Password] <SecureString>] [-PasswordProtector] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Add-BitLockerKeyProtector [-StartupKeyPath] <String> [[-Pin] <SecureString>] [-TpmAndPinAndStartupKeyProtector]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Add-BitLockerKeyProtector [[-Pin] <SecureString>] [-TpmAndPinProtector] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_6
```
Add-BitLockerKeyProtector [-RecoveryKeyPath] <String> [-RecoveryKeyProtector] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_7
```
Add-BitLockerKeyProtector [[-RecoveryPassword] <String>] [-RecoveryPasswordProtector] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_8
```
Add-BitLockerKeyProtector [-StartupKeyPath] <String> [-StartupKeyProtector] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_9
```
Add-BitLockerKeyProtector [-StartupKeyPath] <String> [-TpmAndStartupKeyProtector] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_10
```
Add-BitLockerKeyProtector [-TpmProtector] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-BitLockerKeyProtector** cmdlet adds a protector for the volume key of the volume protected with BitLocker Drive Encryption.

When a user accesses a drive protected by BitLocker, such as when starting a computer, BitLocker requests the relevant key protector.
For example, the user can enter a PIN or provide a USB drive that contains a key.
BitLocker retrieves the encryption key and uses it to read data from the drive.

You can use one of the following methods or combinations of methods for a key protector: 

- Trusted Platform Module (TPM).
BitLocker uses the computer's TPM to protect the encryption key.
If you specify this protector, users can access the encrypted drive as long as it is connected to the system board that hosts the TPM and the system boot integrity is intact.
In general, TPM-based protectors can only be associated to an operating system volume.
- TPM and Personal Identification Number (PIN).
BitLocker uses a combination of the TPM and a user-supplied PIN.
A PIN is four to twenty digits or, if you allow enhanced PINs, four to twenty letters, symbols, spaces, or numbers. 
- TPM, PIN, and startup key.
BitLocker uses a combination of the TPM, a user-supplied PIN, and input from of a USB memory device that contains an external key. 
- TPM and startup key.
BitLocker uses a combination of the TPM and input from of a USB memory device. 
- Startup key.
BitLocker uses input from of a USB memory device that contains the external key. 
- Password.
BitLocker uses a password. 
- Recovery key.
BitLocker uses a recovery key stored as a specified file in a USB memory device. 
- Recovery password.
BitLocker uses a recovery password. 
- Active Directory Domain Services (AD DS) account.
BitLocker uses domain authentication to unlock data volumes.
Operating system volumes cannot use this type of key protector.

You can add only one of these methods or combinations at a time, but you can run this cmdlet more than once on a volume.

Adding a key protector is a single operation; for example, adding a startup key protector to a volume that uses the TPM and PIN combination as a key protector results in two key protectors, not a single key protector that uses TPM, PIN, and startup key.
Instead, add a protector that uses TPM, PIN, and startup key and then remove the TPM and PIN protector by using the Remove-BitLockerKeyProtector cmdlet.

For a password or PIN key protector, specify a secure string.
You can use the **ConvertTo-SecureString** cmdlet to create a secure string.
You can use secure strings in a script and still maintain confidentiality of passwords.

This cmdlet returns a BitLocker volume object.
If you choose recovery password as your key protector but do not specify a 48-digit recovery password, this cmdlet creates a random 48-bit recovery password.
The cmdlet stores the password as the **RecoveryPassword** field of the **KeyProtector** attribute of the BitLocker volume object.

If you use startup key or recovery key as part of your key protector, provide a path to store the key.
This cmdlet stores the name of the file that contains the key in the **KeyFileName** field of the **KeyProtector** field in the BitLocker volume object.

For an overview of BitLocker, see BitLocker Drive Encryption Overviewhttp://technet.microsoft.com/en-us/library/cc732774.aspx (http://technet.microsoft.com/en-us/library/cc732774.aspx) on TechNet.

## EXAMPLES

### Example 1: Add key protector
```
PS C:\>$SecureString = ConvertTo-SecureString "1234" -AsPlainText -Force PS C:\>Add-BitLockerProtector -MountPoint "C:" -Pin $SecureString -TPMandPinProtector
```

This example adds a combination of the TPM and a PIN as key protector for the BitLocker volume identified with the drive letter C:.

The first command uses the **ConvertTo-SecureString** cmdlet to create a secure string that contains a PIN and saves that string in the $SecureString variable.
For more information about the **ConvertTo-SecureString** cmdlet, type `Get-Help ConvertTo-SecureString`.

The second command adds a protector to the BitLocker volume that has the drive letter C:.
The command specifies that this volume uses a combination of the TPM and the PIN as key protector and provides the PIN saved in the $SecureString variable.

### Example 2: Add a recovery key for all BitLocker volumes
```
PS C:\>Get-BitLockerVolume | Add-BitLockerKeyProtector -RecoveryKeyPath "E:\Recovery\" -RecoveryKeyProtector
```

This command gets all the BitLocker volumes for the current computer and passes them to the Add-BitLockerKeyProtector**** cmdlet by using the pipe operator.
This cmdlet specifies a path to a folder where the randomly generated recovery key will be stored and indicates that these volumes use a recovery key as a key protector.

### Example 3: Add credentials as a key protector
```
PS C:\>Add-BitLockerKeyProtector -MountPoint "C:" -AdAccountOrGroup "Western\SarahJones" -AdAccountOrGroupProtector
```

This command adds an AD DS account key protector to the BitLocker volume specified by the **MountPoint** parameter.
The command specifies an account and specifies that BitLocker uses user credentials as a key protector.
When a user accesses this volume, BitLocker prompts for credentials for the user account Western\SarahJones.

## PARAMETERS

### -ADAccountOrGroup
Specifies an account using the format **Domain\User**.
This cmdlet adds the account you specify as a key protector for the volume encryption key.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: sid

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ADAccountOrGroupProtector
Indicates that BitLocker uses an AD DS account as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: sidp

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountPoint
Specifies an array of drive letters or BitLocker volume objects.
This cmdlet adds a key protector to the volumes specified.
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
Specifies a secure string object that contains a password.
The cmdlet adds the password specified as a protector for the volume encryption key.

```yaml
Type: SecureString
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: pw

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PasswordProtector
Indicates that BitLocker uses a password as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: pwp

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pin
Specifies a secure string object that contains a PIN.
The cmdlet adds the PIN specified, with other data, as a protector for the volume encryption key.

```yaml
Type: SecureString
Parameter Sets: UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: p

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryKeyPath
Specifies a path to a folder.
This cmdlet adds a randomly generated recovery key as a protector for the volume encryption key and stores it in the specified path.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: rk

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryKeyProtector
Indicates that BitLocker uses a recovery key as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: rkp

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPassword
Specifies a recovery password.
If you do not specify this parameter, the cmdlet creates a random password.
You can enter a 48 digit password.
The cmdlet adds the password specified or created as a protector for the volume encryption key.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_7
Aliases: rp

Required: False
Position: 2
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPasswordProtector
Indicates that BitLocker uses a recovery password as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_7
Aliases: rpp

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Service
Indicates that the system account for this computer unlocks the encrypted volume.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupKeyPath
Specifies a path to a startup key.
The cmdlet adds the key stored in the specified path as a protector for the volume encryption key.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_9
Aliases: sk

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupKeyProtector
Indicates that BitLocker uses a startup key as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_8
Aliases: skp

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -TpmAndPinAndStartupKeyProtector
Indicates that BitLocker uses a combination of TPM, a PIN, and a startup key as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: tpskp

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -TpmAndPinProtector
Indicates that BitLocker uses a combination of TPM and a PIN as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: tpp

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -TpmAndStartupKeyProtector
Indicates that BitLocker uses a combination of TPM and a startup key as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_9
Aliases: tskp

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -TpmProtector
Indicates that BitLocker uses TPM as a protector for the volume encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_10
Aliases: tpmp

Required: True
Position: Named
Default value: False
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

### BitLockerVolume[], string[]

## OUTPUTS

### BitLockerVolume[]

## NOTES

## RELATED LINKS

[Backup-BitLockerKeyProtector](./Backup-BitLockerKeyProtector.md)

[Remove-BitLockerKeyProtector](./Remove-BitLockerKeyProtector.md)

[Get-BitLockerVolume](./Get-BitLockerVolume.md)

[Enable-BitLocker](./Enable-BitLocker.md)

