---
external help file: WSUS_Cmdlets.xml
Module Name: UpdateServices
online version: https://docs.microsoft.com/powershell/module/updateservices/set-wsusproduct?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WsusProduct

## SYNOPSIS
Sets whether the product representing the category of updates to synchronize is enabled or disabled.

## SYNTAX

```
Set-WsusProduct [-Disable] -Product <WsusProduct> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-WsusProduct** cmdlet enables or disables the product representing the category of updates to synchronized.
In order to use this cmdlet, the Get-WsusProduct cmdlet must be run (optionally using the Where-Objecthttp://go.microsoft.com/fwlink/?LinkID=113423 cmdlet to filter its results) with its results piped into this cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-WsusServer | Get-WsusProduct | Where-Object -FilterScript {$_.product.title -Eq "Antigen"} | Set-WsusProduct
```

This example specifies that you want updates for the Antigen product.

## PARAMETERS

### -Disable
Specifies that updates are not to be synchronized for the specified product.

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

### -Product
Specifies the product for which the updates are to be synchronized.
If the **Disable** parameter is used, then this parameter specifies the product for which the updates are not to be synchronized.
This parameter value is piped from the Get-WsusProduct cmdlet.

```yaml
Type: WsusProduct
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423)

[Get-WsusProduct](./Get-WsusProduct.md)

