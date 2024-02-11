---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetIPsecDospSetting.cmdletDefinition.cdxml-help.xml
Module Name: NetSecurity
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/netsecurity/get-netipsecdospsetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetIPsecDospSetting
---

# Get-NetIPsecDospSetting

## SYNOPSIS
Retrieves IPsec DoS protection settings from the target computer.

## SYNTAX

### GetAll (Default)
```
Get-NetIPsecDospSetting [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByName
```
Get-NetIPsecDospSetting [-Name] <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetIPsecDospSetting** cmdlet returns the instances of existing IPsec DoS protection settings.

If the *Name* parameter is not specified, then all of the Dosp settings configured on the computer are returned.
Querying by object requires the use of the [Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423) cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetIPsecDospSetting
```

This example gets all of the Dosp setting configured on the computer.

### EXAMPLE 2
```
PS C:\>Get-NetIPsecDospSetting -Name CorpNet-PubNet
```

This example gets the Dosp setting with the specified name.

### EXAMPLE 3
```
PS C:\>$netIPSDospSetting = Get-NetIPsecDospSetting



PS C:\>Where-Object -FilterScript { $_.PublicInterfaceAliases -Eq "PubNet" } -InputObject $netIPSDospSetting


This cmdlet can be run using only the pipeline.
PS C:\>Get-NetIPsecDospSetting | Where-Object -FilterScript { $_.PublicInterfaceAliases -Eq "PubNet" }
```

This example gets all of the Dosp settings configured to the specified internal interface.

### EXAMPLE 4
```
PS C:\>$nIPSDospSetting = Get-NetIPsecDospSetting



PS C:\>$nIPSDospSettingPubNet = Where-Object -FilterScript { $_.PublicInterfaceAliases -Eq "PubNet" } -InputObject $nIPSDospSetting



PS C:\>Set-NetIPsecDospSetting -PublicInterfaceAliases PubNet2 -InputObject $nIPSDospSettingPubNet


This cmdlet can be run using only the pipeline.
PS C:\>Get-NetIPsecDospSetting | Where-Object -FilterScript { $_.PublicInterfaceAliases -Eq "PubNet" } | Set-NetIPsecDospSetting -PublicInterfaceAliases PubNet2
```

This example modifies the internal interface of the previously acquired IPsec Dosp settings.

## PARAMETERS

### -All
Indicates that all of the Dosp settings within the specified policy store are retrieved.

```yaml
Type: SwitchParameter
Parameter Sets: GetAll
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -Name
Specifies that only the matching IPsec rules of the indicated name are retrieved.
Wildcard characters are accepted.
This parameter acts just like a file name, in that only one rule with a given name may exist in a policy store at a time.
During group policy processing and policy merge, rules that have the same name but come from multiple stores being merged, will overwrite one another so that only one exists.
This overwriting behavior is desirable if the rules serve the same purpose.
For instance, all of the firewall rules have specific names, so if an administrator can copy these rules to a GPO, and the rules will override the local versions on a local computer.
GPOs can have precedence.
So if an administrator has a different or more specific rule with the same name in a higher-precedence GPO, then it overrides other rules that exist.
The default value is a randomly assigned value.
When the defaults for main mode encryption need to overridden, specify the customized parameters and set this parameter value, making this parameter the new default setting for encryption.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: 0
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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\NetIPsecDospSetting[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkId=113423)

[New-NetIPsecDospSetting](./New-NetIPsecDospSetting.md)

[Remove-NetIPsecDospSetting](./Remove-NetIPsecDospSetting.md)

[Set-NetIPsecDospSetting](./Set-NetIPsecDospSetting.md)

