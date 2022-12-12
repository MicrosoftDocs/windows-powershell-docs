---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://learn.microsoft.com/powershell/module/webadministration/remove-webvirtualdirectory?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-WebVirtualDirectory

## SYNOPSIS
Removes an IIS virtual directory.

## SYNTAX

```
Remove-WebVirtualDirectory -Site <String> -Application <String> [-Name] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Removes an IIS virtual directory.

## EXAMPLES

### -------------- EXAMPLE 1: Removing a virtual directory --------------
```
IIS:\>Remove-WebVirtualDirectory -Site "Default Web Site" -Application "testApp" -Name testVirtualDir
```

Removes the virtual directory named testVirtualDir from the Default Web Site.

## PARAMETERS

### -Application
The name of the application that hosts the virtual directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Name
The name of the virtual directory to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Site
The name of the site that hosts the virtual directory to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

## NOTES

## RELATED LINKS

