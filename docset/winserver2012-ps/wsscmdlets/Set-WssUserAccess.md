---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: F8994BB4-0248-4B58-9FB7-F85BD7A53672
manager: dansimp
---

# Set-WssUserAccess

## SYNOPSIS
Modifies the user access setting.

## SYNTAX

```
Set-WssUserAccess [-User] <User> [-GrantAccess] [-RevokeAccess]
```

## DESCRIPTION
The **Set-WssUserAccess** cmdlet modifies the user access setting in sbs_sbs8_2.

## EXAMPLES

### Example 1: Modify user access
```
PS C:\> Set-WSSUserAccess -User $WSSUser -GrantAccess 2
```

This command modifies user access by granting ShareAccess to the user in the variable named **WSSUser**.

## PARAMETERS

### -GrantAccess
Specifies the access to grant to a user.
To set more than one access, you must call the cmdlet for each access.
Valid values for this parameter are:
- 1 RemoteAccess
- 2 ShareAccess
- 3 ComputerAccess
- 4 MediaAccess
- 5 AddInAccess
- 6 DashboardAccess
- 7 HomePageLinks
- 8 NetworkAlertAccess
- 9 VpnAccess

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: InvalidAccess, RemoteAccess, ShareAccess, ComputerAccess, MediaAccess, AddInAccess, DashboardAccess, HomePageLinks, NetworkAlertAccess, VpnAccess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RevokeAccess
Specifies the access to revoke from a user.
Valid values for this parameter are:
- 1 RemoteAccess
- 2 ShareAccess
- 3 ComputerAccess
- 4 MediaAccess
- 5 AddInAccess
- 6 DashboardAccess
- 7 HomePageLinks
- 8 NetworkAlertAccess
- 9 VpnAccess

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: InvalidAccess, RemoteAccess, ShareAccess, ComputerAccess, MediaAccess, AddInAccess, DashboardAccess, HomePageLinks, NetworkAlertAccess, VpnAccess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies a user object.

```yaml
Type: User
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

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

