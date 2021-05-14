---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/import-wssuser?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Import-WssUser

## SYNOPSIS
Imports a user from Active Directory.

## SYNTAX

```
Import-WssUser -SamAccountName <String>
```

## DESCRIPTION
The **Import-WssUser** cmdlet imports a user from Active Directory (AD).
Following the import, use the UI to manage the user in sbs_sbs8_2 server.

## EXAMPLES

### Example 1: Import a user
```
PS C:\> Import-WssUser -Name "SarahJones"
```

This command imports a user from AD.

## PARAMETERS

### -SamAccountName
Specifies the Security Account Manager (SAM) name for a user.

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

[Remove-WssUser](./Remove-WssUser.md)

[Sync-WssUser](./Sync-WssUser.md)

