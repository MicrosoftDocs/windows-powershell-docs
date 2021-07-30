---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/add-wssuser?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WssUser
---

# Add-WssUser

## SYNOPSIS
Adds a new user account.

## SYNTAX

```
Add-WssUser [-AccessLevel <String>] [-FirstName <String>] [-LastName <String>] [-Name] <String>
 [-GroupName <String>] [-AllowRemoteAccess] [-AllowVpnAccess] [-Password] <SecureString> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssUser** cmdlet adds a new user account to the sbs_sbs8_2 server.
Use the parameters to grant the account access to services or set access levels.

## EXAMPLES

### Example 1: Add a user
```
PS C:\> Add-WssUser -AccessLevel "Administrator" -Name "SarahJones" -FirstName "Sarah" -LastName "Jones" -AllowRemoteAccess
```

This command adds a user with administrative access and remote web access to a sbs_sbs8_2 server.

## PARAMETERS

### -AccessLevel
Specifies the access level for a user.
To give the user administrative access, specify Administrator; otherwise, specify User for a standard user.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: User, Administrator

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowRemoteAccess
Indicates that the user can access the Remote Web Access website.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowVpnAccess
Indicates that the user can access the VPN server.

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

### -FirstName
Specifies the first name of a user.

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

### -GroupName
Specifies the name of a group.

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

### -LastName
Specifies the last name of a user.

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

### -Name
Specifies a user account name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies a password for a user, as a secure string.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Users.User
This cmdlet returns the user object created by this cmdlet.

## NOTES

## RELATED LINKS

[Get-WssUser](./Get-WssUser.md)

[Remove-WssUser](./Remove-WssUser.md)

