---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://docs.microsoft.com/powershell/module/webadministration/stop-webitem?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Stop-WebItem

## SYNOPSIS
Stops an application pool or a site.

## SYNTAX

```
Stop-WebItem [-Passthru] [-Protocol <String>] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
TheStop-WebItemcmdlet is used to stop a Site or an application pool.

## EXAMPLES

### -------------- EXAMPLE 1: Stop a Web site --------------
```
IIS:\>Stop-WebItem 'IIS:\Sites\Default Web Site'
```

Stops the site named Default Web Site.
No output is returned.

### -------------- EXAMPLE 2: Stopping a Web site with feedback --------------
```
IIS:\>Stop-WebItem 'IIS:\Sites\Default Web Site' -Passthru
```

Stops the site named Default Web Site and reports whether the site was stopped.

Name ID State Physical Path Bindings

---- -- ----- ------------- --------

Default Web Site 1 Stopped C:\inetpub\wwwroot\Default Web http *:80:

Site

## PARAMETERS

### -PSPath
The path to the site or application pool.

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
Passes an object that represents the Web item to the pipeline.

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
The protocol binding of the site to stop (sites only).

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSObject

## OUTPUTS

### PSObject

## NOTES

## RELATED LINKS

[Get-WebItemState](./Get-WebItemState.md)

[Restart-WebItem](./Restart-WebItem.md)

[Start-WebItem](./Start-WebItem.md)

