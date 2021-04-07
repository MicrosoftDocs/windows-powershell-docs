---
author: Kateyanne
description: 
external help file: PS_SmisProvider_v1.0.cdxml-help.xml
manager: jasgro
Module Name: SMISConfig
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/smisconfig/search-smisprovider?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
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

To register a provider, use the **Register-SmisProvider** cmdlet.
To remove a registered provider so that it can no longer be used, use the **Unregister-SmisProvider** cmdlet.
Both cmdlets take a URI as input.

## EXAMPLES

### Example 1: Search for an SMI-S provider
```
PS C:\>Search-SmisProvider
```

This command searches for all SMI-S providers on the same subnet as the server.

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

### System.Uri[]
The URI represents the list of devices that the cmdlet discovered.

## NOTES

## RELATED LINKS

[Register-SmisProvider](./Register-SmisProvider.md)

[Unregister-SmisProvider](./Unregister-SmisProvider.md)

