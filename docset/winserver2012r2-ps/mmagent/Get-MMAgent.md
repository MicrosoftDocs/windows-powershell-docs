---
external help file: ps_mmagent_v1.0.cdxml-help.xml
Module Name: MMAgent
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/mmagent/get-mmagent?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MMAgent
---

# Get-MMAgent

## SYNOPSIS
Returns the state of application launch prefetching, operation API prefetching functionality, page combining, and application prelaunching.

## SYNTAX

```
Get-MMAgent [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MMAgent** cmdlet reports whether the following features are enabled: 
- Application launch prefetching 
- Operation API prefetching functionality
- Page combining
- Application prelaunching

This cmdlet also returns the maximum number of prefetch files for scenarios that the operation recorder API records.

## EXAMPLES

### Example 1: Return the state of prefetching functionality
```
PS C:\> Get-MMAgent
```

This command returns the state of application launch prefetching, application prelaunching, operation recorder API prefetching functionality, and page combining.
This command also returns the maximum number of prefetch files for scenarios that the operation recorder API records.

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MMAgentComponents

## NOTES

## RELATED LINKS

[Debug-MMAppPrelaunch](./Debug-MMAppPrelaunch.md)

[Set-MMAgent](./Set-MMAgent.md)

[Enable-MMAgent](./Enable-MMAgent.md)

[Disable-MMAgent](./Disable-MMAgent.md)

