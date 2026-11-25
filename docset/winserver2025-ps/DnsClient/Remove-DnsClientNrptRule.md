---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsClientNRPTRule_v1.0.0.cdxml-help.xml
Module Name: DnsClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsclient/remove-dnsclientnrptrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DnsClientNrptRule
---

# Remove-DnsClientNrptRule

## SYNOPSIS
Removes the specified DNS client NRPT rule.

## SYNTAX

```
Remove-DnsClientNrptRule [-GpoName <String>] [-Name] <String> [-PassThru] [-Server <String>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DnsClientNrptRule** cmdlet removes the specified DNS client Name Resolution Policy Table (NRPT) rule.

## EXAMPLES

### Example 1: Remove an NRPT rule from a specified server
```
PS C:\> Remove-DnsClientNrptRule -GpoName "TestGPO" -Name "{1326d9d0-4fb5-4fed-9f67-f53637b85010}" -PassThru -Server "host1.com" -Force
```

This example removes the NRPT rule named {1326d9d0-4fb5-4fed-9f67-f53637b85010} on the server named host1.com.

### Example 2: Remove an NRPT rule
```
PS C:\> Remove-DnsClientNrptRule -Name "DA-{274D94E4-E38B-4997-BA9F-84700712C09E}" -PassThru

Confirm
Removing NRPT rule for the namespace nls.corp.contoso.com with
 DAEnable: Enable,
 DnsSecValidationRequired: Disabled,
 NameEncoding: Disable
 NameServers: No
 Do you want to continue?
 [Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y

Name                             : DA-{274D94E4-E38B-4997-BA9F-84700712C09E}
Version                          : 1
Namespace                        : {nls.corp.contoso.com}
IPsecCARestriction               :
DirectAccessDnsServers           :
DirectAccessEnabled              : True
DirectAccessProxyType            : UseDefault
DirectAccessProxyName            :
DirectAccessQueryIPsecEncryption :
DirectAccessQueryIPsecRequired   : False
NameServers                      :
DnsSecEnabled                    : False
DnsSecQueryIPsecEncryption       :
DnsSecQueryIPsecRequired         :
DnsSecValidationRequired         :
NameEncoding                     : Disable
DisplayName                      :
Comment                          :

This version of the cmdlet performs the task without user confirmation.
PS C:\> Remove-DnsClientNrptRule -Name "DA-{274D94E4-E38B-4997-BA9F-84700712C09E}" -PassThru -Force

Name                             : DA-{274D94E4-E38B-4997-BA9F-84700712C09E}
Version                          : 1
Namespace                        : {nls.corp.contoso.com}
IPsecCARestriction               :
DirectAccessDnsServers           :
DirectAccessEnabled              : True
DirectAccessProxyType            : UseDefault
DirectAccessProxyName            :
DirectAccessQueryIPsecEncryption :
DirectAccessQueryIPsecRequired   : False
NameServers                      :
DnsSecEnabled                    : False
DnsSecQueryIPsecEncryption       :
DnsSecQueryIPsecRequired         :
DnsSecValidationRequired         :
NameEncoding                     : Disable
DisplayName                      :
Comment                          :
```

This example removes the NRPT rule named {1326d9d0-4fb5-4fed-9f67-f53637b85010}.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -GpoName
Specifies the name of the Group Policy Object (GPO).

- If this parameter and the *Server* parameter are specified, then the NRPT rule is added in the GPO of domain.
The *Server* parameter specifies the domain controller (DC).
- If neither this parameter nor the *Server* parameter is specified, then the NRPT rule is added for local client computer.
- If this parameter is specified and the *Server* parameter is not specified, then the DC of the domain specified by this parameter value is found and NRPT rule is added to the GPO.
- If this parameter is not specified and the *Server* parameter is specified, then an error is displayed.

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

### -Name
Specifies the name which uniquely identifies a rule.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### -Server
Specifies the name of the server containing the GPO.
This parameter is only applicable with the *GpoName* parameter.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DnsClientNrptRule
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DNS/DnsClientNrptRule
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.


The **DnsClientNrptRule** object contains all of the properties of the DNS client NRPT rule.

## NOTES

## RELATED LINKS

[Add-DnsClientNrptRule](./Add-DnsClientNrptRule.md)

[Get-DnsClientNrptGlobal](./Get-DnsClientNrptGlobal.md)

[Get-DnsClientNrptPolicy](./Get-DnsClientNrptPolicy.md)

[Get-DnsClientNrptRule](./Get-DnsClientNrptRule.md)

[Set-DnsClientNrptGlobal](./Set-DnsClientNrptGlobal.md)

[Set-DnsClientNrptRule](./Set-DnsClientNrptRule.md)

