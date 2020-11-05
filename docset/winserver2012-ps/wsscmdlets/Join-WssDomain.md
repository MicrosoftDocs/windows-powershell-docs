---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 1E282B68-8EAA-438D-8F65-4E6C2407E691
manager: dansimp
---

# Join-WssDomain

## SYNOPSIS
Joins the server to a domain.

## SYNTAX

```
Join-WssDomain [-ImportGroup <String>] -DomainName <String> -Password <String> -UserName <String>
```

## DESCRIPTION
The **Join-WssDomain** cmdlet joins the server to a domain.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -DomainName
Specifies the name of a domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImportGroup
Specifies the name of a security group.
The server uses the security group to limit the imported users that are managed through the Dashboard.
By default, the server imports all users in the domain, subject to the maximum number of users of the server.

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

### -Password
Specifies the password of a user account with permission to join the server to the domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the login name of a user account with permission to join the domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Exit-WssDomain](./Exit-WssDomain.md)

[Get-WssDomainNameConfiguration](./Get-WssDomainNameConfiguration.md)

