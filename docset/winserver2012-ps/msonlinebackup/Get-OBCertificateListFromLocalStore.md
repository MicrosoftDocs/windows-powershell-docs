---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 0329C809-022A-4147-97C0-512A060FEFFA
---

# Get-OBCertificateListFromLocalStore

## SYNOPSIS
Gets the list of certificates from the local computer certificate store.

## SYNTAX

```
Get-OBCertificateListFromLocalStore
```

## DESCRIPTION
The **Get-OBCertificateListFromLocalStore** cmdlet gets the list of certificates from the local computer certificate store.
You can use the certificates that the cmdlet returns to register the current computer with mob_name_1.
You can use the Start-OBRegistration cmdlet to register the current computer to mob_name_1.

ps_mob_user_group_remark

## EXAMPLES

### Example 1: Get certificates from the local certificate store
```
PS C:\>Get-OBCertificateListFromLocalStore
```

This command gets the list of certificates from the local computer certificate store.

## PARAMETERS

## INPUTS

## OUTPUTS

### OBCertificate[]
List of certificates that you can use to register the server.

## NOTES

## RELATED LINKS

[Get-OBRecoveryService](./Get-OBRecoveryService.md)

