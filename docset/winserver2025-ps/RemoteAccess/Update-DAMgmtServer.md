---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAMgmtServer_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/update-damgmtserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-DAMgmtServer
---

# Update-DAMgmtServer

## SYNOPSIS
Updates the list of Management servers of the DirectAccess (DA) deployment.

## SYNTAX

```
Update-DAMgmtServer [-PassThru] [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-DAMgmtServer** cmdlet updates the list of Management servers of the DirectAccess (DA) deployment.
A management server is any server that needs to be accessed in a DA managed-out deployment or during the first tunnel in a DA full deployment, such as update servers, domain controllers and other servers.

Domain controllers and Microsoft Endpoint Configuration Manager servers are discovered automatically.
Manually entered management server names are resolved to IP addresses.

Management server configuration is applicable globally to the entire DA deployment and therefore is not impacted by multi-site deployments.

When the cmdlet runs, the list of automatically discovered domain controllers and Configuration Manager servers is updated.
Discovered servers are added to the list, and servers that cannot be discovered are removed.
IP addresses in the list are updated in accordance with server name resolution.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$x = Update-DAMgmtServer -PassThru



PS C:\>$x.Summary
ChangesDetected


PS C:\>$x.Servers | Format-Table -AutoSize
Change: Added
Host                         Change Type   IPAddresses
----                         ------ ----   -----------
DC3.domain1.corp.company.com Added  {DC}   {fdfe:5c64:53e1:7777::1e00:6302}
SC1.domain1.corp.company.com Added  {SCCM} {fdfe:5c64:53e1:7777::1e00:845A}
Change: Removed

Host                         Change  Type IPAddresses
----                         ------  ---- -----------
DC4.domain1.corp.company.com Removed {DC} {fdfe:5c64:53e1:7777::1e00:6301, 3000:0:30::99:1}
Change: Unchanged
Host                         Change    Type     IPAddresses
----                         ------    ----     -----------
MGT.domain1.corp.company.com Unchanged {Manual} {fdfe:5c64:53e1:7777::1e00:6301, 3000:0:30::99:1}
DC2.domain2.corp.company.com Unchanged {DC}     {fdfe:5c64:53e1:7777::3200:1, 3000:0:50::1}
DC1.domain1.corp.company.com Unchanged {DC}     {fdfe:5c64:53e1:7777::1e00:1, 3000:0:30::1}
Change: AddressChanged
Host Change         Type     IPAddresses
---- ------         ----     -----------
mm1  AddressChanged {Manual} {fdfe:5c64:53e1:7777::1e00:431a}
```

This example updates the list of management servers accessible via the infrastructure tunnel and outputs the details of the changes.
As seen in the output, the cmdlet performed the following:

 -- Discovered and added one domain controller and one Configuration Manager server.

 -- Removed one DC from the list since it could no longer find it listed as a DC in the domain.

 -- Left the listing for two previously discovered DCs and an existing manually added server unchanged.

 -- Changed the IP address of an existing manually entered server according, after resolving the associated fully qualified domain name (FQDN) and finding that the returned IP is different from the one that was currently listed.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access (RA) server computer specific tasks should be run.

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAMgmtServer

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAMgmtServer object contains the following properties:

 -- The list of added domain controllers.

 -- The list of removed domain controllers.

 -- The list of unchanged domain controllers.

 -- The list of added Configuration Manager servers.

 -- The list of removed Configuration Manager servers.

 -- The list of unchanged Configuration Manager servers.

 -- The list of manually entered servers that have been resolved to new IP addresses.

 -- The list of unchanged manually entered servers.

## NOTES

## RELATED LINKS

[Format-Table](https://go.microsoft.com/fwlink/p/?LinkId=113303)

[Add-DAMgmtServer](./Add-DAMgmtServer.md)

[Get-DAMgmtServer](./Get-DAMgmtServer.md)

[Get-RemoteAccess](./Get-RemoteAccess.md)

[Remove-DAMgmtServer](./Remove-DAMgmtServer.md)

