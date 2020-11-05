---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 59096265-31B1-4338-BBBD-D998D1F0435C
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-WebApplication

## SYNOPSIS
Removes a Web application from an IIS Web site.

## SYNTAX

```
Remove-WebApplication [-Site <String>] [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Removes a Web application from an IIS Web site.

## EXAMPLES

### -------------- EXAMPLE 1: Adding a Web application and removing it --------------
```
IIS:\>New-WebApplication -Name TestApp -Site "Default Web Site" -PhysicalPath "$env:systemdrive\inetpub\TestApp" "Sleep for 5 seconds before Web App is removed"; Sleep 5 Remove-WebApplication -Name TestApp -Site "Default Web Site"
```

This example demonstrates how to create a Web application named TestApp on the Default Web Site.
The application is then removed after 5 seconds.

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

### -Name
The name of the application to remove from the site.

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
The name of the site from which the application is removed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

