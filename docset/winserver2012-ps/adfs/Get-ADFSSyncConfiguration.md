---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
ms.assetid: 5A558B39-8693-4E6B-BCAE-CC7B1BE15B0E
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-ADFSSyncConfiguration

## SYNOPSIS
Gets the configuration database synchronization properties of the Federation Service.

## SYNTAX

```
Get-ADFSSyncConfiguration [<CommonParameters>]
```

## DESCRIPTION
The Get-ADFSSyncConfiguration cmdlet retrieves the configuration database synchronization properties of the Federation Service.

## EXAMPLES

### 1:
```
PS C:\>Get-ADFSSyncConfiguration
```

Gets the current synchronization properties and activity for the Federation Service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.SyncPropertiesBase
A class structure that represents the synchronization properties for the Federation Service.

## NOTES
* This cmdlet keeps track of when Active Directory Federation Services (AD FS) 2.0 on a server computer last synchronized its database with other federation servers in your deployment. For example, the PollDuration property specifies the length of the poll interval in seconds.

## RELATED LINKS

[Set-ADFSSyncConfiguration](./Set-ADFSSyncConfiguration.md)

