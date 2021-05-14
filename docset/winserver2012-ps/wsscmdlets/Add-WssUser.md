---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/add-wssuser?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-WssUser

## SYNOPSIS
Adds a new user account.

## SYNTAX

```
Add-WssUser [-Name] <String> [-Password] <SecureString> [-AccessLevel <String>] [-AllowRemoteAccess]
 [-AllowVpnAccess] [-FirstName <String>] [-LastName <String>]
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
Position: 1
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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### User

## NOTES

## RELATED LINKS

[Get-WssUser](./Get-WssUser.md)

[Import-WssUser](./Import-WssUser.md)

[Remove-WssUser](./Remove-WssUser.md)

[Sync-WssUser](./Sync-WssUser.md)

