---
external help file: WSUS_Cmdlets.xml
Module Name: UpdateServices
online version: https://docs.microsoft.com/powershell/module/updateservices/set-wsusclassification?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WsusClassification

## SYNOPSIS
Sets whether the classifications of updates that Windows Server Update Services (WSUS) synchronizes are enabled or disabled.

## SYNTAX

```
Set-WsusClassification [-Disable] -Classification <WsusClassification> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-WsusClassification** cmdlet enables or disables the category of updates (for example security or critical) to be synchronized.

Using this cmdlet without filtering results.
The Get-WsusClassification cmdlet must be run, then the results are piped it into this cmdlet.

Using this cmdlet with filtered results.
The Get-WsusClassification cmdlet must be run, then results are filtered using the Where-Objecthttps://go.microsoft.com/fwlink/?LinkID=113423 cmdlet and piped into this cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-WsusClassification | Where-Object -FilterScript {$_.Classification.Title -Eq "Drivers"} | Set-WsusClassification -Disable
```

This example specifies that you do not want driver updates.

## PARAMETERS

### -Classification
Specifies the classification of updates that are to be synchronized.
If the **Disable** parameter is used, then this parameter specifies the classification of updates that are not to be synchronized.
This parameter value is piped from the Get-WsusClassification cmdlet.

```yaml
Type: WsusClassification
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Disable
Specifies that updates are not to be synchronized for the specified classification.

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

[Get-WsusClassification](./Get-WsusClassification.md)

