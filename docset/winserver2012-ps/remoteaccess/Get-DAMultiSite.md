---
external help file: UnifiedRA_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 36B7594B-0FB5-43D6-B1A4-FD0A492622D1
manager: dansimp
---

# Get-DAMultiSite

## SYNOPSIS
Retrieves global settings applied to all entry points in a multi-site deployment.

## SYNTAX

```
Get-DAMultiSite [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DAMultiSite** cmdlet retrieves global multi-site settings that are applied to all entry points, including the following: 

 -- The name of the multi-site deployment. 

 -- A list of the entry points included in the deployment, and the servers contained in each entry point. 

 -- The global load balancing fully qualified domain name (FQDN), if applicable. 

 -- Support for remote clients to manually select the entry point to which they connect.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DAMultiSite
EnterpriseName                   : Company Enterprise 
GslbFqdn                         : directaccessglobalsite.contoso.com 
ManualEntryPointSelectionAllowed : Enabled 
DAEntryPoints                    : Entry Point 1
```

This example retrieves all the multisite related information.

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
Specifies the IPv4 or IPv6 address, or host name, of a server or server cluster in the multi-site deployment for which global settings should be retrieved.

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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DAMultiSite
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAMultiSite object contains the following: 

 -- Multi-site deployment name. 

 -- List of entry points in the deployment, and the servers contained in each entry point. 

 -- Global load balancing FQDN, if defined. 

 -- Support for remote clients to manually select the entry point to which they connect.

## NOTES

## RELATED LINKS

[Disable-DAMultiSite](./Disable-DAMultiSite.md)

[Enable-DAMultiSite](./Enable-DAMultiSite.md)

[Set-DAMultiSite](./Set-DAMultiSite.md)

