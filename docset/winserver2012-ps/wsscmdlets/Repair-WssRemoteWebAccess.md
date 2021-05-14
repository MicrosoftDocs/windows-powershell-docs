---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/repair-wssremotewebaccess?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Repair-WssRemoteWebAccess

## SYNOPSIS
Repairs Remote Web Access.

## SYNTAX

```
Repair-WssRemoteWebAccess [-SkipRouter]
```

## DESCRIPTION
The **Repair-WssRemoteWebAccess** cmdlet repairs Remote Web Access in a sbs_sbs8_2 installation.
The cmdlet initializes and starts the service.

## EXAMPLES

### Example 1: Repair Remote Web Access
```
PS C:\> Repair-WssRemoteWebAccess -SkipRouter
```

This command repairs Remote Web Access but skips the router configuration task.

## PARAMETERS

### -SkipRouter
Indicates that the cmdlet skips the router configuration task.
If you want to manually configure the router, set this parameter to $True

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

[Disable-WssRemoteWebAccess](./Disable-WssRemoteWebAccess.md)

[Enable-WssRemoteWebAccess](./Enable-WssRemoteWebAccess.md)



