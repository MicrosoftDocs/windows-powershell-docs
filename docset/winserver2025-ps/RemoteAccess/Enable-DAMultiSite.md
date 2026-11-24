---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAMultiSite_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/enable-damultisite?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-DAMultiSite
---

# Enable-DAMultiSite

## SYNOPSIS
Enables and configures a multi-site deployment, and adds the first entry point.

## SYNTAX

```
Enable-DAMultiSite [-ComputerName <String>] [-EntryPointName] <String> [-GslbFqdn <String>]
 [-ManualEntryPointSelectionAllowed <String>] [-Name <String>] [-GslbIP <IPAddress>] [-Force] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-DAMultiSite** cmdlet enables and configures a multi-site deployment.
This cmdlet configures both global multi-site settings and entry point-specific settings.

Global settings include:

 -- Multi-site deployment name.

 -- A fully qualified domain name (FQDN) for global load balancing.
This setting is optional.

 -- Support for remote clients to manually select the entry point to which they connect.

Entry point-specific settings include:

 -- Entry point name.

 -- A global load balancing IP address for the entry point.
This setting is optional.

A prerequisite check is performed for multi-site deployment requirements.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Enable-DAMultiSite -EntryPointName "Entry Point 1" -PassThru -Force

EnterpriseName                   : Enterprise
GslbFqdn                         :
ManualEntryPointSelectionAllowed : Enabled
DAEntryPoints                    : Entry Point 1
```

This example enables DirectAccess (DA) Multi-site on the local DA server while using default parameters and naming the first entry point Entry Point 1.
As can be seen from the output, the cmdlet chose a default EnterpriseName Enterprise and enabled the Manual Entry Point Selection by the Windows Server® 2012 user.

### EXAMPLE 2
```
PS C:\>Enable-DAMultiSite -EntryPointName "Entry Point 1" -ComputerName "da1" -PassThru

EnterpriseName                   : Enterprise
GslbFqdn                         :
ManualEntryPointSelectionAllowed : Enabled
DAEntryPoints                    : Entry Point 1
```

This example enables DA Multi-site on the remote DA server 'DA1' while using default parameters and naming the first entry point Entry Point 1.
As can be seen from the output, the cmdlet chose a default EnterpriseName Enterprise and enabled Manual Entry Point Selection by the Windows Server 2012 user.

### EXAMPLE 3
```
PS C:\>Enable-DAMultiSite "Entry Point 1" -GslbFqdn "directaccessGlobalSite.contoso.com" -EnterpriseName "Company Enterprise" -GslbIP "137.2.0.1" -PassThru -Force

EnterpriseName                   : Company Enterprise
GslbFqdn                         : directaccessGlobalSite.company.com
ManualEntryPointSelectionAllowed : Enabled
DAEntryPoints                    : Entry Point 1
```

This example enables DA Multi-site on the local computer while naming the Multi-site deployment Company Enterprise and determining the FQDN of a third-party load balancer directaccessGlobalSite.contoso.com.
Using load balancer will also require entering the GslbIP for the first entry point 137.2.0.1.

As can be seen from the output, the cmdlet enabled Manual Entry Point Selection by the Windows Server 2012 user.

### EXAMPLE 4
```
PS C:\>Enable-DAMultiSite -EntryPointName "Entry Point 1" -ManualSiteSelectionAllowed Disabled -Name "Company Enterprise" -PassThru -Force

EnterpriseName                   : Company Enterprise
GslbFqdn                         :
ManualEntryPointSelectionAllowed : Disabled
DAEntryPoints                    : Entry Point 1
```

This example enables DA Multi-site on the local computer while naming the Multi-site deployment Company Enterprise and disabled the user from manually select entry points when using the Windows Server 2012 network connectivity assistant.

## PARAMETERS

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

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of a server or server cluster in the multi-site deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

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

### -EntryPointName
Specifies the name of the first entry point in the multi-site deployment.

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

### -GslbFqdn
Specifies the FQDN of a third-party global load balancer.
Global load balancing is used to direct Remote Access clients to the nearest entry point.

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

### -GslbIP
Specifies the IPv4 or IPv6 dedicated IP address (DIP) of the server, or the virtual IP address (VIP) of the server cluster, to be used for global load balancing.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManualEntryPointSelectionAllowed
Allow clients running firstref_client_7 or Windows® 8 to manually select the entry point to which they connect.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

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
Aliases: EnterpriseName

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

### System.String

### System.Net.IPAddress

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAMultiSite

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAMultisite object contains the entire multi-site deployment configuration as follows:

 -- Multi-site deployment name.

 -- Multi-site entry points, where each entry point has a list of associated servers.

 -- Global load balancing FQDN, if defined.

 -- Support for remote clients to manually select the entry point to which they connect.

## NOTES

## RELATED LINKS

[Add-DAEntryPoint](./Add-DAEntryPoint.md)

[Disable-DAMultiSite](./Disable-DAMultiSite.md)

[Get-DAMultiSite](./Get-DAMultiSite.md)

[Set-DAMultiSite](./Set-DAMultiSite.md)

