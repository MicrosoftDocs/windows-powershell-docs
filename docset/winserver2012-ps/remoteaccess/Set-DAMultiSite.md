---
external help file: UnifiedRA_Cmdlets.xml
Module Name: RemoteAccess
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-damultisite?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DAMultiSite

## SYNOPSIS
Configures global settings for all entry points in a multi-site deployment.

## SYNTAX

```
Set-DAMultiSite [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-GslbFqdn <String>]
 [-ManualEntryPointSelectionAllowed <String>] [-Name <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-DAMultiSite** cmdlet configures global multi-site settings that are applied to all entry points, including: 

 -- The name of an entry point server included in the multi-site deployment. 

 -- The global load balancing fully qualified domain name (FQDN), if required. 

 -- Support for remote clients to manually select the entry point to which the clients connect. 

 -- The name of the multi-site deployment.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DAMultiSite -ManualEntryPointSelection enabled -PassTrue

EnterpriseName                   : Company Enterprise 
GslbFqdn                         : 
ManualEntryPointSelectionAllowed : Enabled 
DAEntryPoints                    : Entry Point 1
```

This example enables users to manually select entry points when using the Windows Server 2012 Network connectivity assistant.

### EXAMPLE 2
```
PS C:\>Set-DAMultiSite -GslbFqdn "directaccessGlobalSite.contoso.com" -PassTrue

EnterpriseName                   : Company Enterprise 
GslbFqdn                         : directaccessglobalsite.contoso.com 
ManualEntryPointSelectionAllowed : Enabled 
DAEntryPoints                    : Entry Point 1
```

This example sets the FQDN of a third-party load balancer named directaccessglobalsite.contoso.com.

### EXAMPLE 3
```
PS C:\>Set-DAMultiSite -ManualSiteSelection enabled -GslbFqdn "" -PassThru

EnterpriseName                   : Company Enterprise 
GslbFqdn                         : 
ManualEntryPointSelectionAllowed : Enabled 
DAEntryPoints                    : Entry Point 1
```

This example erases the previously defined FQDN of a third-party load balancer.

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
Specifies the IPv4 orIPv6 address, or host name, of one of the entry point servers included in the multi-site deployment for which parameters should be set.

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

### -GslbFqdn
Specifies the FQDN of a third-party global load balancer, if deployed.
A global load balancer is used to direct clients to the closest entry point.

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

### -ManualEntryPointSelectionAllowed
Sets the enabled state that allows clients running firstref_client_7 or Windows Server® 2012 to manually select the entry point to which each client connects.

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
Specifies the name used to identify the multi-site deployment.

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

### Microsoft.Management.Infrastructure.CimInstance#DAMultiSite
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAMultiSite object contains the following properties: 

 -- Multi-site deployment name. 

 -- Multi-site deployment entry points with a list of servers associated with each entry point. 

 -- Global load balancing FQDN, if required. 

 -- Support for remote clients to manually select the entry point to which the clients connect.

## NOTES

## RELATED LINKS

[Disable-DAMultiSite](./Disable-DAMultiSite.md)

[Enable-DAMultiSite](./Enable-DAMultiSite.md)

[Get-DAMultiSite](./Get-DAMultiSite.md)

