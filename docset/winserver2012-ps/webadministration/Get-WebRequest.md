---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://docs.microsoft.com/powershell/module/webadministration/get-webrequest?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WebRequest

## SYNOPSIS
Gets the IIS requests that are currently being executed.

## SYNTAX

```
Get-WebRequest [-InputObject <PSObject>] [-AppPool <String>] [-Process <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
Shows IIS requests that are currently being executed.

## EXAMPLES

### -------------- EXAMPLE 1: Get request that are currently being executed --------------
```
IIS:\>Get-Item IIS:\AppPools\DefaultAppPool | Get-WebRequest
```

Returns a list of IIS requests that are currently being executed.

## PARAMETERS

### -AppPool
The application pool from which request information is retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: pool

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Input object from which parameter data is received.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Process
Specifies a process ID for which request information is retrieved.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: proc, procid, pid, wp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

