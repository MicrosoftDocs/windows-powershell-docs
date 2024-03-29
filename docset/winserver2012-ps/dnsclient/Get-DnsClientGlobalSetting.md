---
external help file: MSFT_DnsClientGlobalSetting.cdxml-help.xml
Module Name: DnsClient
online version: https://learn.microsoft.com/powershell/module/dnsclient/get-dnsclientglobalsetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DnsClientGlobalSetting

## SYNOPSIS
Retrieves global DNS client settings like the suffix search list.

## SYNTAX

```
Get-DnsClientGlobalSetting [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DnsClientGlobalSetting** cmdlet retrieves DNS client settings that are global, that are not associated with a specific interface.
The settings affect the behavior of the DNS client across all of the interfaces.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DnsClientGlobalSetting
UseSuffixSearchList : True 
SuffixSearchList    : {corp.contoso.com, na.corp.contoso.com} 
UseDevolution       : True 
DevolutionLevel     : 0
```

This example gets all of the global DNS client settings.

### EXAMPLE 2
```
PS C:\>$dnsCGSetting = Get-DnsClientGlobalSetting



PS C:\>$dnsCGSetting.SuffixSearchList
corp.contoso.com 
na.corp.contoso.com
```

This example gets the connection-specific suffixes.
The first item in the list is the primary DNS suffix, if configured.

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_DNSClientGlobalSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Set-DnsClientGlobalSetting](./Set-DnsClientGlobalSetting.md)

