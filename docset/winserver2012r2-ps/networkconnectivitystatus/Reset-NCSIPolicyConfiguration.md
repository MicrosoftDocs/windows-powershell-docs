---
external help file: MSFT_NCSIPolicyConfiguration.cdxml-help.xml
Module Name: NetworkConnectivityStatus
online version: 
schema: 2.0.0
title: Reset-NCSIPolicyConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: E8ADD910-FF91-4A2F-98CD-8F814F4A7DD6
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Reset-NCSIPolicyConfiguration

## SYNOPSIS
Resets a configuration for NCSI.

## SYNTAX

### ByName (Default)
```
Reset-NCSIPolicyConfiguration [-PolicyStore <String>] [-GPOSession <String>] [-CorporateDNSProbeHostAddress]
 [-CorporateDNSProbeHostName] [-CorporateSitePrefixList] [-CorporateWebsiteProbeURL]
 [-DomainLocationDeterminationURL] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Reset-NCSIPolicyConfiguration -InputObject <CimInstance[]> [-CorporateDNSProbeHostAddress]
 [-CorporateDNSProbeHostName] [-CorporateSitePrefixList] [-CorporateWebsiteProbeURL]
 [-DomainLocationDeterminationURL] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Reset-NCSIPolicyConfiguration** cmdlet resets a configuration for NCSI.
There is a GPO that configures NCSI.
Return that GPO to a not configured state.
To do that, use this cmdlet to reset the fields that no longer need to be configured.

## EXAMPLES

### EXAMPLE 1
```
This cmdlet resets the NCSI configuration of the specified GPO.
PS C:\>Reset-NCSIPolicyConfiguration -PolicyStore "contoso\User1"


This cmdlet performs an identical operation using pipelining.
PS C:\> Get-NCSIPolicyConfiguration -PolicyStore "contoso\User1" | Reset-NCSIPolicyConfiguration
```

This example resets the NCSI configuration of a specified CPO in two ways.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CorporateDNSProbeHostAddress
Specifies that the specified policy store will no longer configure the corporate DNS probe host address.

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

### -CorporateDNSProbeHostName
Specifies that the specified policy store will no longer configure the corporate DNS probe host name.

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

### -CorporateSitePrefixList
Specifies that the specified policy store will no longer configure the corporate site prefix list.

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

### -CorporateWebsiteProbeURL
Specifies that the specified policy store will no longer configure the corporate website probe URL.

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

### -DomainLocationDeterminationURL
Specifies that the specified policy store will no longer configure the domain location determination URL.

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

### -GPOSession
Specifies a GPO session as the store for this cmdlet. 
                         
Using this parameter will allow an aggregate of multiple cmdlets to run against a local GPO cache.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Sends items from the interactive window down the pipeline as input to other cmdlets.
By default, this cmdlet does not generate any output.
This parameter is equivalent to using the Multiple value of the **OutputMode** parameter. 
                         
To send items from the interactive window down the pipeline, click to select the items and then click OK.
Shift-click and Ctrl-click are supported.

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

### -PolicyStore
Used to specify the logical store for the management operation.
An example is the local persistent store or a Group Policy Object.
The acceptable values for this parameter are:
                         
 - `Domain\GPOName`
                         
 - `ComputerName`

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_NCSIPolicyConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-DAConnectionStatus](./Get-DAConnectionStatus.md)

[Get-NCSIPolicyConfiguration](./Get-NCSIPolicyConfiguration.md)

[Set-NCSIPolicyConfiguration](./Set-NCSIPolicyConfiguration.md)

