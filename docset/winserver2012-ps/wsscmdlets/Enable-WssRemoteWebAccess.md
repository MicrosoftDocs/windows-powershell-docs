---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 0EDFB6C2-B7CF-4F32-BA54-4A0663D45F86
manager: dansimp
---

# Enable-WssRemoteWebAccess

## SYNOPSIS
Enables Remote Web Access.

## SYNTAX

```
Enable-WssRemoteWebAccess [-ApplyToExistingUsers] [-DenyAccessByDefault] [-SkipRouter]
```

## DESCRIPTION
The **Enable-WssRemoteWebAccess** cmdlet enables Remote Web Access on the sbs_sbs8_2 server.

To disable Remote Web Access, use the **Disable-WssRemoteWebAccess** cmdlet.

## EXAMPLES

### Example 1: Enable Remote Web Access
```
PS C:\> Enable-WssRemoteWebAccess -SkipRouter
```

This command enables Remote Web Access but skips the router configuration task.

## PARAMETERS

### -ApplyToExistingUsers
Indicates that the cmdlet enables remote access for existing users.
If you specify both *DenyAccessByDefault* and *ApplyToExistingUsers*, the cmdlet disables the remote access permission for existing users.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DenyAccessByDefault
Indicates that the cmdlet denies Remote Web Access by default.
If you specify both *DenyAccessByDefault* and *ApplyToExistingUsers*, the cmdlet disables remote access permission for existing users.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipRouter
Indicates that the cmdlet skips the router configuration task.
Use this parameter when you want to manually configure a router.

```yaml
Type: SwitchParameter
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

[Enable-WssRemoteWebAccess](./Enable-WssRemoteWebAccess.md)

[Repair-WssRemoteWebAccess](./Repair-WssRemoteWebAccess.md)

