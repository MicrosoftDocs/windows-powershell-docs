---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsClient-help.xml
Module Name: HgsClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsclient/remove-hgsguardian?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HgsGuardian
---

# Remove-HgsGuardian

## SYNOPSIS
Removes a guardian from the guardian store.

## SYNTAX

### NameViaString (Default)
```
Remove-HgsGuardian [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameViaGuardian
```
Remove-HgsGuardian [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HgsGuardian** cmdlet removes a Host Guardian Service guardian object from the guardian store.

## EXAMPLES

### Example 1: Remove a guardian
```
PS C:\> Remove-HgsGuardian -Name "Guardian11"
```

This command removes the guardian named Guardian11 from the local store.

## PARAMETERS

### -InputObject
The HGS guardian object to remove.

```yaml
Type: CimInstance
Parameter Sets: NameViaGuardian
Aliases: Guardian

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the guardian to remove.

```yaml
Type: String
Parameter Sets: NameViaString
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Export-HgsGuardian](./Export-HgsGuardian.md)

[Get-HgsGuardian](./Get-HgsGuardian.md)

[Import-HgsGuardian](./Import-HgsGuardian.md)

[New-HgsGuardian](./New-HgsGuardian.md)

