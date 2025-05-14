---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/stop-webitem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-WebItem
---

# Stop-WebItem

## SYNOPSIS
Stops a site or an application pool.

## SYNTAX

```
Stop-WebItem [-Passthru] [-Protocol <String>] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-WebItem** cmdlet stops a site or an application pool.

## EXAMPLES

### Example 1: Stop a website
```
IIS:\> Stop-WebItem -PSPath "IIS:\Sites\Default Web Site"
```

This command stops the site named Default Web Site.
No output is returned.

### Example 2: Stop a website with feedback
```
IIS:\> Stop-WebItem -PSPath "IIS:\Sites\Default Web Site" -Passthru
Name        ID     State    Physical Path                  Bindings

----        --     -----    -------------                  --------

Default Web Site 1 Stopped  C:\inetpub\wwwroot\Default Web http *:80:

Site
```

This command stops the site named Default Web Site and reports whether the site was stopped.

## PARAMETERS

### -PSPath
Specifies the path to the site or application pool.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru
Passes an object that represents the web item to the pipeline.

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

### -Protocol
Specifies the protocol binding of the site to stop.
This parameter applies to sites only.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSObject

## OUTPUTS

### PSObject

## NOTES

## RELATED LINKS

[Restart-WebItem](./Restart-WebItem.md)

[Start-WebItem](./Start-WebItem.md)

