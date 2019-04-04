---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 5422C3D5-5FDF-4A2A-A56E-F16991399747
manager: dansimp
---

# Get-OBRecoverableSource

## SYNOPSIS
Get the list of datasources recoverable from this server or the specified OBBackupServer object.

## SYNTAX

```
Get-OBRecoverableSource [[-Server] <CBBackupServer>]
```

## DESCRIPTION
The **Get-OBRecoverableSource** cmdlet gets the list of datasources recoverable from this server or the specified OBBackupServer object.
This list is then used to get item level recovery.

ps_mob_user_group_remark

## EXAMPLES

### Example 1: Get recoverable data sources
```
PS C:\>Get-OBRecoverableSource
```

This example returns all recoverable data sources.

### Example 2: Get recoverable data sources for backup servers
```
PS C:\>Get-OBAlternateBackupServer | Get-OBRecoverableSource
```

This command returns the recoverable data sources for the backup servers that are associated with the backup account.

## PARAMETERS

### -Server
Specifies the server from which data needs to be recovered.

```yaml
Type: CBBackupServer
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBRecoverableSource[]

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](http://go.microsoft.com/fwlink/?LinkID=113291)

[New-Object](http://go.microsoft.com/fwlink/?LinkID=113355)

[Get-OBAlternateBackupServer](./Get-OBAlternateBackupServer.md)
