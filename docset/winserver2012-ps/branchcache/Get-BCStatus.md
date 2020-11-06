---
external help file: BranchCacheStatus.cdxml-help.xml
ms.assetid: 2E68D4DA-55B8-46D1-A48C-5BD155CE6558
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-BCStatus

## SYNOPSIS
Retrieves a set of objects that provide BranchCache status and configuration information.

## SYNTAX

```
Get-BCStatus [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-BCStatus** cmdlet retrieves a set of objects that provide BranchCache status and configuration information.
This cmdlet retrieves all of the objects returned by Get-BCClientSettings, Get-BCContentServerSettings, Get-BCHostedCacheServerSettings and Get-BCNetworkSettings.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-BCStatus
```

This example retrieves a set of objects that provide BranchCache status and configuration information.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetBranchCache
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-BCClientConfiguration](./Get-BCClientConfiguration.md)

[Get-BCContentServerConfiguration](./Get-BCContentServerConfiguration.md)

[Get-BCHostedCacheServerConfiguration](./Get-BCHostedCacheServerConfiguration.md)

[Get-BCNetworkConfiguration](./Get-BCNetworkConfiguration.md)

