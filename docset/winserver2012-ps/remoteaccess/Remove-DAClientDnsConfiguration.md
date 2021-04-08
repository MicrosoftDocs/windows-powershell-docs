---
author: Kateyanne
external help file: UnifiedRA_Cmdlets.xml
manager: dansimp
Module Name: RemoteAccess
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/remoteaccess/remove-daclientdnsconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-DAClientDnsConfiguration

## SYNOPSIS
Removes the Name Resolution Policy Table (NRPT) entry corresponding to the specified DNS suffix from the NRPT.

## SYNTAX

```
Remove-DAClientDnsConfiguration [-DnsSuffix] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-DAClientDnsConfiguration** cmdlet removes the Name Resolution Policy Table (NRPT) entry corresponding to the specified DNS suffix from the NRPT.

In a multi-domain scenario; when an NRPT entry is removed, the entry is correspondingly deleted from the all the client GPOs in various domains.
Note: In a Windows deployment with firstref_server_7 GPOs, removal of a suffix will removes it from both the nextref_server_7 GPOs and Windows Server® 2012 GPOs

The NRPT configuration is applicable globally to the entire DA deployment and therefore is not impacted by multi-site deployments.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Remove-DAClientDnsConfiguration -DnsSuffix 'contoso.com' -PassThru
Name                             : 
Version                          : 1 
Namespace                        : {hrnet.com} 
IPsecCARestriction               : 
DirectAccessDnsServers           : fdad:34fb:a649:7777::404:404 
DirectAccessEnabled              : True 
DirectAccessProxyType            : Direct 
DirectAccessProxyName            : 
DirectAccessQueryIPsecEncryption : None 
DirectAccessQueryIPsecRequired   : False 
NameServers                      : 
DnsSecEnabled                    : 
DnsSecQueryIPsecEncryption       : None 
DnsSecQueryIPsecRequired         : False 
DnsSecValidationRequired         : False 
NameEncoding                     : 
DisplayName                      : 
Comment                          :
```

This example removes the NRPT rules for contoso.com from DA configuration.
This change is propagated across all of the client GPOs.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsSuffix
Specifies a list of DNS suffixes.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsClientNRPTRule[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The array of DnsClientNRPTRule objects contains the following properties: 

 -- The NRPT object for the NRPT entry that was removed.

## NOTES

## RELATED LINKS

[Add-DAClientDnsConfiguration](./Add-DAClientDnsConfiguration.md)

[Get-DAClientDnsConfiguration](./Get-DAClientDnsConfiguration.md)

[Set-DAClientDnsConfiguration](./Set-DAClientDnsConfiguration.md)

