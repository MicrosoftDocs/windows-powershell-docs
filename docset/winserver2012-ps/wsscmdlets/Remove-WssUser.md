---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/remove-wssuser?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-WssUser

## SYNOPSIS
Deletes a user.

## SYNTAX

```
Remove-WssUser -Name <String>
```

## DESCRIPTION
The **Remove-WssUser** cmdlet deletes a user from a sbs_sbs8_2 server.

## EXAMPLES

### Example 1: Delete a user
```
PS C:\> Remove-WssUser -Name "SarahJones"
```

This command deletes a user from WSS by using the logon name.

## PARAMETERS

### -Name
Specifies the logon name of a user.

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

[Add-WssUser](./Add-WssUser.md)

[Get-WssUser](./Get-WssUser.md)

[Import-WssUser](./Import-WssUser.md)

[Sync-WssUser](./Sync-WssUser.md)

