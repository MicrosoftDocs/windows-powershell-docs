---
external help file: BitLocker-help.xml
Module Name: bitlocker
schema: 2.0.0
---

# BackupToAAD-BitLockerKeyProtector

## SYNOPSIS
Saves a key protector for a BitLocker volume in Microsoft Entra ID.

## SYNTAX

```
BackupToAAD-BitLockerKeyProtector [-MountPoint] <String[]> [-KeyProtectorId] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **BackupToAAD-BitLockerKeyProtector** cmdlet saves a recovery password key protector for a volume protected by BitLocker Drive Encryption to Microsoft Entra ID. Specify a key to be saved by ID.

## EXAMPLES

### Example 1
```powershell
PS C:\> $BLV = Get-BitLockerVolume -MountPoint "C:"
PS C:\> BackupToAAD-BitLockerKeyProtector -MountPoint "C:" -KeyProtectorId $BLV.KeyProtector[1].KeyProtectorId

```

This example saves a key protector for a specified BitLocker volume.

The first command uses **Get-BitLockerVolume** to obtain a BitLocker volume and store it in the $BLV variable.

The second command backs up the key protector for the BitLocker volume specified by the MountPoint parameter. The command specifies the key protector by using its ID, contained in the BitLocker object stored in $BLV. 

### Example 2
```powershell
PS C:\> BackupToAAD-BitLockerKeyProtector -MountPoint "C:" -KeyProtectorId "{E2611001E-6AD0-4A08-BAAA-C9c031DB2AA6}"
```
This command saves a key protector for a specified BitLocker volume to Microsoft Entra ID. The command specifies the key protector by using its ID.

## PARAMETERS

### -KeyProtectorId
The **KeyProtector** attribute contains an array of key protectors associated to the volume. This command uses standard array syntax to index the KeyProtector object. The key protector that corresponds to the recovery password key protector can be identified by using the KeyProtectorType attribute in the KeyProtector object.


```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MountPoint
The volume to be used by **KeyProtector**.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.String

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
