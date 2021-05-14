---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://docs.microsoft.com/powershell/module/webadministration/get-webappdomain?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WebAppDomain

## SYNOPSIS
Gets the application domains in which the specified IIS worker process is running.

## SYNTAX

```
Get-WebAppDomain [-InputObject <PSObject>] [-ApplicationPool <String>] [-ProcessId <UInt32>]
 [<CommonParameters>]
```

## DESCRIPTION
Gets the application domains in which the specified IIS worker process is running.

## EXAMPLES

### -------------- EXAMPLE 1: Get the application domain of a running Worker Process --------------
```
IIS:\>Get-WebAppDomain -ProcessId 5872 -ApplicationPool DefaultAppPoolGet-ChildItem IIS:\AppPools\DefaultAppPool\WorkerProcesses
```

The example gets the application domains loaded in the specified Worker Process.
The process ID can be retrieved by looking at the WorkerProcesses node below the AppPools node, for example:

## PARAMETERS

### -ApplicationPool
The application pool for which the application domains are returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases: apppool, pool

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
The input object from which parameter data is received.

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

### -ProcessId
The ID of the worker process for which the application domain is returned.

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

