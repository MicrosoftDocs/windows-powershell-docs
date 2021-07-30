---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssuseraccess?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssUserAccess
---

# Set-WssUserAccess

## SYNOPSIS
Modifies the user access setting.

## SYNTAX

```
Set-WssUserAccess [-GrantAccess <UserAccess>] [-RevokeAccess <UserAccess>] [-User] <User> [<CommonParameters>]
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
Type: UserAccess
Parameter Sets: (All)
Aliases: 
Accepted values: RemoteAccess, ShareAccess, ComputerAccess, MediaAccess, VpnAccess, DashboardAccess, HomePageLinks, NetworkAlertAccess

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
Type: UserAccess
Parameter Sets: (All)
Aliases: 
Accepted values: RemoteAccess, ShareAccess, ComputerAccess, MediaAccess, VpnAccess, DashboardAccess, HomePageLinks, NetworkAlertAccess

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
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

