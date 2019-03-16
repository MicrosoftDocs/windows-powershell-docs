---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 1AA5F8EB-9D0C-4A8B-AD80-790FAE3ED651
---

# Start-OBRecovery

## SYNOPSIS
Recovers the array of OBRecoverableItem objects with the specified recovery options in the OBRecoverableOptions object.

## SYNTAX

```
Start-OBRecovery [-RecoverableItem] <CBRecoverableItem[]> [[-RecoveryOption] <CBRecoveryOption>]
 [[-EncryptionPassphrase] <SecureString>] [-Async] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Start-OBRecovery** cmdlet recovers the array of OBRecoverableItem objects with the specified recovery options in OBRecoverableOptions object.
In case of Alternate Server Recovery, the credential and encryption passphrase object would be required to do the recovery.

If no recovery option is specified, the following default options will be used. 
 1)   Restore to original location. 
 2)   Create copies in case of conflict. 
 3)   Restore ACLs of the files.

When recovering data to an alternate server restore flow the cmdlet will display an error message if the OBRecoverableOptions object is not specified because there is no default original location in a recovery from another server.

This cmdlet supports WhatIf and Confirm parameters with a medium impact.
The medium impact signifies that the cmdlet will not prompt the user for confirmation by default.
The WhatIf parameter gives a verbose description of what the cmdlet does without performing any operation.
The Confirm parameter specifies whether the cmdlet should prompt the user.
Using -Confirm:$FALSE will override the prompt.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$sources = Get-OBRecoverableSource



PS C:\>$RP = Get-OBRecoverableItem -Source $sources[0]



PS C:\>$passphrase = Read-Host -Prompt "Enter encryption passphrase" -AsSecureString



PS C:\>$pwd = ConvertTo-SecureString -String Notag00dpa55word -AsPlainText -Force



PS C:\>$cred = New-Object -TypeName System.Management.Automation.PsCredential -ArgumentList contoso\johnj99, $pwd



PS C:\>$RO = New-OBRecoveryOption -DestinationPath C:\\test -OverwriteType Overwrite



PS C:\>Start-OBRecovery -RecoverableItem $RP -RecoveryOption $RO -EncryptionPassphrase $passphrase -Credential $cred -Async
```

This example starts a recovery job.

## PARAMETERS

### -Async
Allows the user to indicate that the cmdlet should run asynchronously.
This is useful with cmdlets that take a long time to complete.
The control returns to the user immediately after the operation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionPassphrase
Specifies the encryption passphrase to be used to decrypt the data for recovery.
This should be same as the latest encryption passphrase set for backup.
This is required in case of Alternate Server Recovery.
In case of Alternate Server Recovery this encryption passphrase should match with the latest encryption passphrase set for backup on the original server.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoverableItem
Specifies the items to be recovered.

```yaml
Type: CBRecoverableItem[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryOption
Specifies whether the items recovered should overwrite any existing copies or whether copies of existing items should be created during recovery.

```yaml
Type: CBRecoveryOption
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
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

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Client.Cmdlets.OBJob

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](http://go.microsoft.com/fwlink/?LinkID=113291)

[New-Object](http://go.microsoft.com/fwlink/?LinkID=113355)

[Read-Host](http://go.microsoft.com/fwlink/?LinkID=113371)

[Get-OBRecoverableItem](./Get-OBRecoverableItem.md)

[Get-OBRecoverableSource](./Get-OBRecoverableSource.md)

[New-OBRecoveryOption](./New-OBRecoveryOption.md)

