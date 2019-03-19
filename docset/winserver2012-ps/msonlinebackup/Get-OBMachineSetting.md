---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 57FDC808-82C1-44C0-AB5C-5CBAB8F41E54
---

# Get-OBMachineSetting

## SYNOPSIS
Gets the OBMachineSetting object for the server.

## SYNTAX

```
Get-OBMachineSetting
```

## DESCRIPTION
The **Get-OBMachineSetting** cmdlet gets an OBMachineSetting object for the server.
This object contains the server properties settings, including proxy server settings used by mob_name_1 to access the internet, bandwidth throttling settings, and the encryption passphrase that will be required to decrypt the files during recovery to another server.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-OBMachineSetting
```

This example gets the machine settings for the current protected server.

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBMachineSetting

## NOTES

## RELATED LINKS

[Get-OBMachineUsage](./Get-OBMachineUsage.md)

[Set-OBMachineSetting](./Set-OBMachineSetting.md)

