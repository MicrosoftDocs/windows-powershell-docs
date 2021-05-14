---
external help file: MSFT_NCSIPolicyConfiguration.cdxml-help.xml
Module Name: NetworkConnectivityStatus
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/networkconnectivitystatus/set-ncsipolicyconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NCSIPolicyConfiguration
---

# Set-NCSIPolicyConfiguration

## SYNOPSIS
Specifies the policy store from which the cmdlet should pull configuration information.

## SYNTAX

### ByName (Default)
```
Set-NCSIPolicyConfiguration [-PolicyStore <String>] [-GPOSession <String>]
 [[-CorporateDNSProbeHostAddress] <String>] [[-CorporateDNSProbeHostName] <String>]
 [[-CorporateSitePrefixList] <String[]>] [[-CorporateWebsiteProbeURL] <String>]
 [[-DomainLocationDeterminationURL] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NCSIPolicyConfiguration -InputObject <CimInstance[]> [[-CorporateDNSProbeHostAddress] <String>]
 [[-CorporateDNSProbeHostName] <String>] [[-CorporateSitePrefixList] <String[]>]
 [[-CorporateWebsiteProbeURL] <String>] [[-DomainLocationDeterminationURL] <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-NCSIPolicyConfiguration** cmdlet allows a user to configure NCSI configuration options on a Group Policy Object.

This cmdlet supports getting information from a Group Policy Object, in the form Domain\GPOName.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-NCSIPolicyConfiguration -PolicyStore "contoso\User1" -CorporateWebsiteProbe http://contoso.com
```

This example modifies the corporate website probe of the specified GPO.

### EXAMPLE 2
```
PS C:\> Get-NCSIPolicyConfiguration -PolicyStore "contoso\User1" | Set-NCSIPolicyConfiguration -CorporateWebsiteProbe http://contoso.com
```

This example performs the same operation as EXAMPLE 1 using pipelining.

### EXAMPLE 3
```
PS C:\> $Object = Get-NCSIPolicyConfiguration -PolicyStore "contoso\User1"
PS C:\> $Object.CorporateWebsiteProbe = http://ncsi.corp.microsoft.com
PS C:\> Set-NCSIPolicyConfiguration -InputObject $Object
```

This example performs an identical operation using dot notation.

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
Specifies the value to be configured. 
                         
This is the expected address of the host name used as for DNS probe.
Successful resolution of the host name to this address indicates corporate connectivity, such as `2001::32`

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CorporateDNSProbeHostName
Specifies the value to be configured. 
                         
This is the host name of a PC known to be on the corporate network.
Successful resolution of this host name to the expected address indicates corporate connectivity, such as `http://contoso.com`

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CorporateSitePrefixList
Specifies the value to be configured. 
                         
This is the list of IPv6 corporate site prefixes that should be monitored for corporate connectivity.
Reachability of addresses with any of these prefixes indicates corporate connectivity, such as `fe90::/9`, `fe81::/8`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CorporateWebsiteProbeURL
Specifies the value to be configured. 
                         
This is the URL of the corporate website that will be used to perform an active probe against, such as `http://contoso.com`

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainLocationDeterminationURL
Specifies the value to be configured. 
                         
This is the HTTPS URL of the corporate website that will be used to determine the current domain location, such as inside or outside the corporate domain.
Reachability of the URL indicates that the location is inside corporate else it is outside, such as `https://contoso.com`

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GPOSession
Specifies the Group Policy session for which the cmdlet should pull configuration information from.
This parameter can be used in conjunction with the NetGPO cmdlet family to aggregate multiple operations that are performed on a Group Policy Object. 
                         
This parameter cannot be used in conjunction with the **PolicyStore** parameter. 
                         
Using this parameter allows multiple cmdlets to be aggregated to run against a local GPO cache. 
                         
This is a common parameter across networking with very little difference between them.

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
Specifies the policy store for which the cmdlet should pull configuration information from.
This cmdlet supports getting information from a Group Policy Object, in the form `Domain\GPOName`. 
                         
The types of PolicyStore supported by this cmdlet: 
                         
 - `Domain\GPOName`
                         
 - `GPO: ComputerName`
                         
This is a common parameter across networking with very little difference between them.

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

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_NCSIConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-DAConnectionStatus](./Get-DAConnectionStatus.md)

[Get-NCSIPolicyConfiguration](./Get-NCSIPolicyConfiguration.md)

[Reset-NCSIPolicyConfiguration](./Reset-NCSIPolicyConfiguration.md)

