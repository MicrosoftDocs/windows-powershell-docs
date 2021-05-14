---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://docs.microsoft.com/powershell/module/webadministration/stop-webapppool?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Stop-WebAppPool

## SYNOPSIS
Stops an application pool.

## SYNTAX

```
Stop-WebAppPool [[-Name] <String>] [-Passthru] [<CommonParameters>]
```

## DESCRIPTION
Stops the specified application pool. If the application pool is already stopped, an exception is thrown.

## EXAMPLES

### -------------- EXAMPLE 1: Stopping an Application Pool --------------
```
IIS:\>Stop-WebAppPool -Name "DefaultAppPool"
```

Stops the application pool named DefaultAppPool.

## PARAMETERS

### -Name
The name of the application pool to stop.

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
Passes an object that represents the application pool to the pipeline.

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

