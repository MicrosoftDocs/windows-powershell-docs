---
external help file: MMAgent_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 16893119-8D8B-4F5B-AA68-D6A10E9EB5A6
manager: dansimp
---

# Get-MMAgent

## SYNOPSIS
Returns the state of application launch prefetching, operation API prefetching functionality, and page combining.

## SYNTAX

```
Get-MMAgent [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-MMAgent** cmdlet reports whether the following features are enabled: 
- Application launch prefetching
- Operation API prefetching functionality
- Page combining

This cmdlet also returns the maximum number of prefetch files for scenarios that the operation recorder API records.

## EXAMPLES

### Example 1: Return the state of prefetching functionality
```
PS C:\> Get-MMAgent
```

This command returns the state of application launch prefetching, operation recorder API prefetching functionality, and page combining.
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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MMAgentComponents

## NOTES

## RELATED LINKS

[Set-MMAgent](./Set-MMAgent.md)

[Enable-MMAgent](./Enable-MMAgent.md)

[Disable-MMAgent](./Disable-MMAgent.md)

