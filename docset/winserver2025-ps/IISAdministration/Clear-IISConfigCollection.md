---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/clear-iisconfigcollection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-IISConfigCollection
---

# Clear-IISConfigCollection

## SYNOPSIS
Clears an IIS configuration collection.

## SYNTAX

```
Clear-IISConfigCollection [-ConfigCollection] <ConfigurationElementCollection> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Clear-IISConfigCollection** cmdlet clears a given Internet Information Services (IIS) collection by removing all the elements and putting a clear tag, which is generally \<clear\>.
This prevents from the collection to inherit collection elements from higher levels, if any.

## EXAMPLES

### Example 1: Clear the defaultDocument settings for Default Web Site, which inherits from Server level and defined in applicationHost.config.
```
PS C:\> Get-IISConfigSection -SectionPath "system.webServer/defaultDocument" -CommitPath "Default Web Site" | Get-IISConfigCollection -CollectionName "files" | Clear-IISConfigCollection -Confirm:$False
```

This command adds lines in web.config which is the configuration file of Default Web Site.

## PARAMETERS

### -ConfigCollection
Specifies the **ConfigurationCollection** object for which the collection elements will be cleared.
If a **ConfigurationCollection** is previously obtained and assigned to a variable, you cannot pass it to this cmdlet through the pipeline because the pipeline engine will try to enumerate, passing **ConfigurationElement** objects instead.
Try either passing the whole **Get-IISConfigCollection** cmdlet into the pipeline or use it as a parameter for correct results.

```yaml
Type: ConfigurationElementCollection
Parameter Sets: (All)
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

### Microsoft.Web.Administration.ConfigurationElementCollection

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-IISConfigCollection](./Get-IISConfigCollection.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

