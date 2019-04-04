---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: EA301285-F439-438D-986D-1F12D79BD4ED
manager: dansimp
---

# Get-OBRecoveryService

## SYNOPSIS
Gets the list of available vaults.

## SYNTAX

```
Get-OBRecoveryService [-Certificate] <CBCertificate>
```

## DESCRIPTION
The **Get-OBRecoveryService** cmdlet gets the list of backup vaults that you can use to register the current computer with mob_name_1.

ps_mob_user_group_remark

## EXAMPLES

### Example 1: Get the list of backup vaults
```
PS C:\>Get-OBRecoveryService
```

This command gets the list of backup vaults that you can use to register the current computer with mob_name_2.

## PARAMETERS

### -Certificate
Specifies the private key of a certificate.
mob_name_2 uses the private key to obtain the recovery services.

```yaml
Type: CBCertificate
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### OBCertificate

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-OBRegistration](./Start-OBRegistration.md)

[Start-OBRecovery](./Start-OBRecovery.md)

