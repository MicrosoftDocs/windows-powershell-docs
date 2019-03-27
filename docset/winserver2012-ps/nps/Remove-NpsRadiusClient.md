---
external help file: NPS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 575A8489-73DB-4C77-BB77-15971D5D159B
manager: dansimp
---

# Remove-NpsRadiusClient

## SYNOPSIS
Removes a RADIUS client.

## SYNTAX

```
Remove-NpsRadiusClient [-Name] <String>
```

## DESCRIPTION
The **Remove-NpsRadiusClient** cmdlet removes a Remote Authentication Dial-In User Service (RADIUS) client.
A RADIUS client uses a RADIUS server to manage authentication, authorization, and accounting requests that the client sends.
A RADIUS client can be an access server, such as a dial-up server or wireless access point, or a RADIUS proxy.

## EXAMPLES

### Example 1: Remove a RADIUS client
```
PS C:\>Remove-NpsRadiusClient -Name "RadiusClient01"
```

This command removes a RADIUS client named RadiusClient01.

## PARAMETERS

### -Name
Specifies the name of the RADIUS client to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NpsRadiusClient](./Get-NpsRadiusClient.md)

[New-NpsRadiusClient](./New-NpsRadiusClient.md)

[Set-NpsRadiusClient](./Set-NpsRadiusClient.md)

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

