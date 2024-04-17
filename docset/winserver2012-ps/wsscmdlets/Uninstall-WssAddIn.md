---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/uninstall-wssaddin?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Uninstall-WssAddIn

## SYNOPSIS
Uninstalls an add-in.

## SYNTAX

```
Uninstall-WssAddIn [-Id] <Guid> [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Uninstall-WssAddIn** cmdlet uninstalls an add-in from the server.
When you uninstall an add-in, the functionality provided by add-in is no longer available on the server.

## EXAMPLES

### Example 1: Uninstall an add-in
```
PS C:\> Uninstall-WssAddIn -Id {6617708D-0F98-4898-8D05-9E882C23DCB2}
```

This command uninstalls the add-in that has the package Id 6617708D-0F98-4898-8D05-9E882C23DCB2.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

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

### -Id
Specifies the GUID of an installed package.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssAddIn](./Get-WssAddIn.md)

[Install-WssAddIn](./Install-WssAddIn.md)

