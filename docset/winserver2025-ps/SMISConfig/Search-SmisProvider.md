---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_SmisProvider_v1.0.cdxml-help.xml
Module Name: SMISConfig
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/smisconfig/search-smisprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Search-SmisProvider
---

# Search-SmisProvider

## SYNOPSIS
Searches for a list of SMI-S providers.

## SYNTAX

```
Search-SmisProvider [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Search-SmisProvider** cmdlet searches for Storage Management Initiative - Specification (SMI-S) providers available on the same subnet as your server as long as they are advertised through the Service Location Protocol v2 (SLPv2).
The cmdlet returns a list of Uniform Resource Identifiers (URIs) that you can use with other cmdlets to register or remove a provider.
If the cmdlet finds no SMI-S providers, it returns nothing.

To register a provider, use the Register-SmisProvider cmdlet.
To remove a registered provider so that it can no longer be used, use the Unregister-SmisProvider cmdlet.
Both cmdlets take a URI as input.

## EXAMPLES

### Example 1: Search for an SMI-S provider
```
PS C:\>Search-SmisProvider
```

This command searches for all SMI-S providers on the same subnet as the server.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Uri[]
This cmdlet returns an array of URIs that represent devices that the cmdlet discovered.

## NOTES

## RELATED LINKS

[Register-SmisProvider](./Register-SmisProvider.md)

[Unregister-SmisProvider](./Unregister-SmisProvider.md)

