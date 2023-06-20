---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssuser?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssUser

## SYNOPSIS
Retrieves a user account by name or security identifier.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WssUser [-Name] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-WssUser [-Sid] <String>
```

## DESCRIPTION
The **Get-WssUser** cmdlet retrieves a sbs_sbs8_2 server user account.
To retrieve a user account by name, specify the login name.
To retrieve a user account by security identifier, specify the SID.
To retrieve all user accounts, use the cmdlet without arguments.

## EXAMPLES

### Example 1: Retrieve a user account by name
```
PS C:\> Get-WSSUser -Name "SarahJones"
```

This command retrieves a user account by name.

## PARAMETERS

### -Name
Specifies the logon name of a user.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sid
Specifies the security identifier of a user.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssUser](./Add-WssUser.md)

[Import-WssUser](./Import-WssUser.md)

[Remove-WssUser](./Remove-WssUser.md)

[Sync-WssUser](./Sync-WssUser.md)

