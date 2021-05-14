---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://docs.microsoft.com/powershell/module/webadministration/stop-website?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Stop-Website

## SYNOPSIS
Stops an IIS Web site.

## SYNTAX

```
Stop-Website [[-Name] <String>] [-Passthru] [<CommonParameters>]
```

## DESCRIPTION
Stops the specified Web site.

## EXAMPLES

### -------------- EXAMPLE 1: Stopping a Web Site --------------
```
IIS:\>Stop-WebSite -Name "Default Web Site"
```

Stops the site named Default Web Site.

## PARAMETERS

### -Name
Name of the Web site to stop.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru
Passes an object that represents the Web site to the pipeline.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-WebAppPool](./Start-WebAppPool.md)

[Start-WebItem](./Start-WebItem.md)

[Start-Website](./Start-Website.md)

[Stop-WebAppPool](./Stop-WebAppPool.md)

[Stop-WebItem](./Stop-WebItem.md)

