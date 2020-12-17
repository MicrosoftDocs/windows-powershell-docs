---
external help file: NPS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 1DA52B73-64A9-42E7-9316-371E09E2348A
manager: dansimp
---

# Get-NpsRadiusClient

## SYNOPSIS
Gets RADIUS clients.

## SYNTAX

```
Get-NpsRadiusClient
```

## DESCRIPTION
The **Get-NpsRadiusClient** cmdlet gets Remote Authentication Dial-In User Service (RADIUS) clients.
A RADIUS client uses a RADIUS server to manage authentication, authorization, and accounting requests that the client sends.
A RADIUS client can be an access server, such as a dial-up server or wireless access point, or a RADIUS proxy.

## EXAMPLES

### Example 1: Get all RADIUS clients
```
PS C:\>$MyRadiusClients = Get-NpsRadiusClient
```

This command gets a list of all RADIUS clients and puts the list in the variable named **$MyRadiusClients**.

## PARAMETERS

## INPUTS

## OUTPUTS

### NpsRadiusClient[]

## NOTES

## RELATED LINKS



[New-NpsRadiusClient](./New-NpsRadiusClient.md)

[Remove-NpsRadiusClient](./Remove-NpsRadiusClient.md)

[Set-NpsRadiusClient](./Set-NpsRadiusClient.md)

