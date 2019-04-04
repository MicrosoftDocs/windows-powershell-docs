---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 066EB53D-003C-4AF4-B5C1-51D5BAEBFE81
manager: dansimp
---

# Start-OBRegistration

## SYNOPSIS
Registers the current computer to mob_name_1.

## SYNTAX

```
Start-OBRegistration [-RecoveryService] <CBServiceResource> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Start-OBRegistration** cmdlet registers the server to mob_name_1.
The cmdlet registers the server by uploading a backup certificate to the vault.
You can use the Get-OBCertificateListFromLocalStore cmdlet to get the list of certificates from the local computer certificate store.

This cmdlet supports the *WhatIf* and the *Confirm* parameters.
The cmdlet prompts the user for confirmation by default.
The *WhatIf* parameter gives a verbose description of what the cmdlet does without performing any operation.
The *Confirm* parameter specifies whether the cmdlet should prompt the user.
Specify -`Confirm:$FALSE`  to override the prompt.

ps_mob_user_group_remark

## EXAMPLES

### Example 1: Registers a server
```
The first command gets the list of certificates from the local computer certificate store, and stores the result in the **$Cert** variable.
PS C:\>$Cert = Get-OBCertificateListFromLocalStore

The second command gets the list of backup vaults that can you use to register the current computer for the fifth certificate stored in **$Cert**. The command stores the result in the **$Item** variable.
PS C:\>$Item = Get-OBRecoveryService -Certificate $Cert[4]

The third command registers the current computer by using the first certificate stored in **$Item**.
PS C:\>Start-OBRegistration -RecoveryService $Item[0]
```

This example starts a computer registration.

## PARAMETERS

### -RecoveryService
Specifies a mob_name_2 recovery agent.

```yaml
Type: CBServiceResource
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### None

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](http://go.microsoft.com/fwlink/?LinkID=113291)

[New-Object](http://go.microsoft.com/fwlink/?LinkID=113355)

[Get-OBRecoveryService](./Get-OBRecoveryService.md)
