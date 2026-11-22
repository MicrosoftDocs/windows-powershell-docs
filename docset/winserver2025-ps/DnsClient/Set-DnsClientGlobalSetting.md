---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DnsClientGlobalSetting.cdxml-help.xml
Module Name: DnsClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsclient/set-dnsclientglobalsetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsClientGlobalSetting
---

# Set-DnsClientGlobalSetting

## SYNOPSIS
Sets the DNS client global, non-interface specific, settings.

## SYNTAX

### ByName (Default)
```
Set-DnsClientGlobalSetting [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-DnsClientGlobalSetting [-InputObject <CimInstance[]>] [-SuffixSearchList <String[]>]
 [-UseDevolution <Boolean>] [-DevolutionLevel <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsClientGlobalSettings** cmdlet sets the global DNS client settings that are global, that are not associated with a specific interface.
These settings affect the behavior of the DNS client across all interfaces.

## EXAMPLES

### Example 1: Set the DNS suffix search list
```
PS C:\> Set-DnsClientGlobalSetting -SuffixSearchList @("corp.contoso.com", "na.corp.contoso.com")
```

This example sets the DNS suffix search list on the computer.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

```yaml
Type: SwitchParameter
Parameter Sets: InputObject (cdxml)
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
Parameter Sets: InputObject (cdxml)
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

### -DevolutionLevel
Specifies the number of labels up to which devolution should occur.
If this parameter is not specified, then the FRD algorithm is used.
If this parameter is configured, then devolution occurs until the specified level.
This parameter value cannot be set if the devolution level setting is already deployed through Group Policy.

```yaml
Type: UInt32
Parameter Sets: InputObject (cdxml)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: InputObject (cdxml)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SuffixSearchList
Specifies a list of global suffixes that can be used in the specified order by the DNS client for resolving the IP address of the computer name.
These suffixes are appended in the specified order to resolve the computer name that is specified.
This parameter value cannot be set if the suffix search list setting is already deployed through Group Policy.

```yaml
Type: String[]
Parameter Sets: InputObject (cdxml)
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
Parameter Sets: InputObject (cdxml)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDevolution
Indicates whether devolution is activated.
With devolution, the DNS resolver creates new FQDNs by appending the single-label, unqualified domain name with the parent suffix of the primary DNS suffix name, and the parent of that suffix, and so on, stopping if the name is successfully resolved or at a level specified in the *DevolutionLevel* parameter.
Devolution works by removing the left-most label and continuing to get to the parent suffix.
The default value is $True.
This parameter value cannot be set if the devolution level setting is already deployed through Group Policy.

```yaml
Type: Boolean
Parameter Sets: InputObject (cdxml)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_DNSClientGlobalSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_DNSClientGlobalSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_DNSClientGlobalSetting class has the various global settings for the DNS client.
Global settings include non-interface specific settings.

## NOTES

## RELATED LINKS

[Get-DnsClientGlobalSetting](./Get-DnsClientGlobalSetting.md)

