---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/sync-wssuser?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Sync-WssUser

## SYNOPSIS
Refreshes user account information from a domain controller.

## SYNTAX

```
Sync-WssUser
```

## DESCRIPTION
The **Sync-WssUser** cmdlet refreshes user account information from a domain controller.
By default, synchronization occurs every 30 minutes.
Use this cmdlet to refresh the account information immediately.

## EXAMPLES

### Example 1: Sync account information from a domain controller
```
PS C:\> Sync-WssUser
```

This command synchronizes the account information from a domain controller.

## PARAMETERS

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssUser](./Add-WssUser.md)

[Get-WssUser](./Get-WssUser.md)

[Import-WssUser](./Import-WssUser.md)

[Remove-WssUser](./Remove-WssUser.md)

