---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
ms.assetid: FE86231C-AE53-42AF-B38F-9EE7386BF08C
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-ADFSProxyConfiguration

## SYNOPSIS
Gets the configuration properties of the federation server proxy.

## SYNTAX

```
Get-ADFSProxyConfiguration [<CommonParameters>]
```

## DESCRIPTION
The Get-ADFSProxyConfiguration cmdlet retrieves the configuration properties of the federation server proxy in Active Directory Federation Services (AD FS).

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\>Get-ADFSProxyConfiguration
```

Gets the configuration properties for a federation server proxy.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ProxyProperties
A class structure that represents the properties for a federation server proxy in AD FS.

## NOTES
* This cmdlet works only when it is called on a federation server proxy.

## RELATED LINKS

[Set-ADFSProxyConfiguration](./Set-ADFSProxyConfiguration.md)

