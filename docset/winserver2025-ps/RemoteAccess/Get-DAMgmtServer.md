---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAMgmtServer_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-damgmtserver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DAMgmtServer
---

# Get-DAMgmtServer

## SYNOPSIS
Displays the configured management servers.
Management server here refers to update servers, Domain Controllers and other servers.

## SYNTAX

```
Get-DAMgmtServer [-ComputerName <String>] [-Type <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DAMgmtServer** cmdlet displays the configured management servers.
Management server here refers to update servers, Domain Controllers, and other servers.

The server addresses are displayed in the same format in which the addresses were originally added (IPv4 or IPv6 address, or host name).

Management server configuration is applicable globally, to the entire DirectAccess (DA) deployment and hence is not impacted by multi-site deployments.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DAMgmtServer -Type DC
DC1.corp.contoso.com
```

This example retrieves a list of all domain controllers which were configured automatically by DA and does not include the servers configured manually.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the remote access server computer specific tasks should be run.

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

### -Type
Specifies the type of management server to be listed.
The acceptable values for this parameter are: DC, SCCM, Manual, or All.
If not specified, then manual and Configuration Manager servers will be output.
Anything that is not a Domain Controllers is listed.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Manual, Sccm, DC, All

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

### System.String[]
The array of strings consists of the following properties:

 -- The list of management servers configured.

## NOTES

## RELATED LINKS

[Add-DAMgmtServer](./Add-DAMgmtServer.md)

[Remove-DAMgmtServer](./Remove-DAMgmtServer.md)

[Update-DAMgmtServer](./Update-DAMgmtServer.md)

