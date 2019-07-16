---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
ms.assetid: 07F2D040-9ADD-434F-AE0B-FAACE7134C15
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-ADFSEndpoint

## SYNOPSIS
Gets the endpoints in the Federation Service.

## SYNTAX

### Address (Default)
```
Get-ADFSEndpoint [[-AddressPath] <String[]>] [<CommonParameters>]
```

### FullUrl
```
Get-ADFSEndpoint [-FullUrl] <Uri[]> [<CommonParameters>]
```

## DESCRIPTION
The Get-ADFSEndpoint cmdlet retrieves a specified endpoint from the Federation Service.
The collection of ADFSEndpoint objects is a list of all the supported endpoints that are on the server.
You can use this list to view the configuration of endpoints and enable or disable them.
To see the full list of endpoints, use this cmdlet with no parameters.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Enable-ADFSEndpoint -TargetAddress /adfs/services/trust/13/Windows
```

Description

-----------

Enables the WS-Trust 1.3 endpoint.

## PARAMETERS

### -AddressPath
```yaml
Type: String[]
Parameter Sets: Address
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FullUrl
Specifies the full URL of the endpoint to retrieve.

```yaml
Type: Uri[]
Parameter Sets: FullUrl
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.Endpoint
A class structure that represents the endpoints for the Federation Service.

## NOTES
* Endpoints provide access to the federation server functionality of Active Directory Federation Services (AD FS) 2.0, such as token issuance, Information Card issuance, and the publication of federation metadata. Depending on the type of endpoint, you can enable or disable the endpoint or control whether the endpoint is published to AD FS 2.0 proxies.

## RELATED LINKS

[Disable-ADFSEndpoint](./Disable-ADFSEndpoint.md)

[Enable-ADFSEndpoint](./Enable-ADFSEndpoint.md)

[Set-ADFSEndpoint](./Set-ADFSEndpoint.md)

