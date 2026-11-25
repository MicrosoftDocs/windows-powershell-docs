---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAEntryPoint_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-daentrypoint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DAEntryPoint
---

# Get-DAEntryPoint

## SYNOPSIS
Displays the settings for an entry point.

## SYNTAX

```
Get-DAEntryPoint [-ComputerName <String>] [-Name <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DAEntrypoint** cmdlet displays the settings for an entry point, including the entry point name, the global load balancing IP address, and a list of entry point servers.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DAEntrypoint -Name "Entry Point 2"
EntryPointName                 GslbIp                         Servers
--------------                 ------                         -------
Entry Point 2                  0.0.0.0                        {da2.domain1.corp.contoso.com}
```

This example gets a specific entry point configuration named Entry Point 2.

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
Specifies the IPv4 or IPv6 address, or host name, of a server or server cluster for which the entry point information should be retrieved.

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

### -Name
Specifies the name of the entry point for which information should be retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: EntryPointName

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#DAEntryPoint

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAEntryPoint object contains the following:

 -- Entry point name.

 -- Global load balancing server IP address.

 -- List of servers in the entry point.

## NOTES

## RELATED LINKS

[Add-DAEntryPoint](./Add-DAEntryPoint.md)

[Get-DAEntryPoint](./Get-DAEntryPoint.md)

[Get-DAEntryPointDC](./Get-DAEntryPointDC.md)

[Remove-DAEntryPoint](./Remove-DAEntryPoint.md)

[Set-DAEntryPoint](./Set-DAEntryPoint.md)

[Set-DAEntryPointDC](./Set-DAEntryPointDC.md)

