---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/revoke-adfsproxytrust?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Revoke-ADFSProxyTrust

## SYNOPSIS
Revokes trust for all federation server proxies configured for the Federation Service.

## SYNTAX

```
Revoke-ADFSProxyTrust [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Revokes trust for all federation server proxies by resetting the trust ID for the Federation Service.
This operation is provided for lockdown purposes in the event of an attack or confirmed possible threat to your deployment.
Once performed, operation effectively revokes trust to all configured proxies immediately.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Revoke-ADFSProxyTrust
```

Description

-----------

Revokes all trust between the current federation server and any of its configured federation server proxies.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* This cmdlet should only be used in the vent of a security breach in live deployment. If you wish to practice using this cmdlet, use of a test lab environment to rehearse or validate this lockdown operation is recommended.

## RELATED LINKS

