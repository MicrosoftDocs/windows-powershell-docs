---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 032FA55C-A237-4BB9-BF53-2F85F0C3628E
manager: dansimp
---

# Exit-WssDomain

## SYNOPSIS
Removes a server from a domain.

## SYNTAX

```
Exit-WssDomain [-Force] [-Password <String>] [-UserName <String>]
```

## DESCRIPTION
The **Exit-WssDomain** cmdlet removes the server from the domain to which it is currently joined.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies the password of a user account with permission to leave the domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the login name of a user account with permission to remove the server from the domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Join-WssDomain](./Join-WssDomain.md)

[Get-WssDomainNameConfiguration](./Get-WssDomainNameConfiguration.md)

[Set-WssDomainNameConfiguration](./Set-WssDomainNameConfiguration.md)

