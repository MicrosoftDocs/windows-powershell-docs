---
external help file: PS_DnsClientNRPTGlobal_v1.0.0.cdxml-help.xml
ms.assetid: 3B2243A2-20A8-4A89-BAF8-DE972758EB54
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
online version: 
schema: 2.0.0
---

# Set-DnsClientNrptGlobal

## SYNOPSIS
Modifies the global Name Resolution Policy Table (NRPT) settings.

## SYNTAX

```
Set-DnsClientNrptGlobal [-EnableDAForAllNetworks <String>] [-GpoName <String>]
 [-SecureNameQueryFallback <String>] [-QueryPolicy <String>] [-Server <String>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsClientNrptGlobal** cmdlet modifies the following global Name Resolution Policy Table (NRPT) settings: 

 -- DNS client enable Direct Access (DA) for all networks setting. 

 -- DNS client query policy. 

 -- DNS client secure name query fallback setting.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DnsClientNrptGlobal -EnableDAForAllNetworks disable -PassThru
EnableDAForAllNetworks                  QueryPolicy                             SecureNameQueryFallback 
----------------------                  -----------                             ----------------------- 
Disable                                 Disable                                 Disable
```

This example modifies the EnableDAForAllNetworks settings in the NPRT globally.

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

### -EnableDAForAllNetworks
Specifies DirectAccess (DA) settings. 
The acceptable values for this parameter are: EnableOnNetworkID, EnableAlways, Disable, or DisableDA.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: EnableOnNetworkID, EnableAlways, Disable, DisableDA

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GpoName
Specifies the name of the Group Policy Object (GPO).
If this parameter is not specified, then the local NRPT settings are retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -QueryPolicy
Specifies the DNS client query policy. 
The acceptable values for this parameter are: Disable, QueryIPv6Only, or QueryBoth.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Disable, QueryIPv6Only, QueryBoth

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecureNameQueryFallback
Specifies the DNS client name resolution fallback policy. 
The acceptable values for this parameter are: Disable, FallbackSecure, FallbackUnsecure, or FallbackPrivate.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Disable, FallbackSecure, FallbackUnsecure, FallbackPrivate

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the server hosting the GPO.
This parameter is only applicable with the **GpoName** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DnsClientNrptGlobal
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DnsClientNrptGlobal object contains all of the properties of the DNS client NRPT global settings.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DnsClientNrptGlobal
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DnsClientNrptGlobal object contains all of the properties of the DNS client NRPT global settings.

## NOTES

## RELATED LINKS

[Add-DnsClientNrptRule](./Add-DnsClientNrptRule.md)

[Get-DnsClientNrptGlobal](./Get-DnsClientNrptGlobal.md)

[Get-DnsClientNrptPolicy](./Get-DnsClientNrptPolicy.md)

[Get-DnsClientNrptRule](./Get-DnsClientNrptRule.md)

[Remove-DnsClientNrptRule](./Remove-DnsClientNrptRule.md)

[Set-DnsClientNrptRule](./Set-DnsClientNrptRule.md)

