---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BranchCacheOrchestrator.cdxml-help.xml
Module Name: BranchCache
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/branchcache/enable-bchostedclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-BCHostedClient
---

# Enable-BCHostedClient

## SYNOPSIS
Configures BranchCache to operate in hosted cache client mode.

## SYNTAX

### ServerNames (Default)
```
Enable-BCHostedClient [-Force] [-ServerNames] <String[]> [-UseVersion <HostedCacheVersion>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UseSCP
```
Enable-BCHostedClient [-Force] [-UseSCP] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-BCHostedClient** cmdlet configures BranchCache to operate in hosted cache client mode.

## EXAMPLES

### Example 1: Enable host cache client mode
```
PS C:\> Enable-BCHostedClient -ServerNames "HC.contoso.com" -UseVersion Windows7
```

This command enables hosted cache client mode using the HC.contos.com computer as a hosted cache server.
For HTTPS, use Windows® 7 mode (`Windows7`).

### Example 2: Enable host cache client mode for two servers
```
PS C:\> Enable-BCHostedClient -ServerNames "HC1.contoso.com","HC2.contoso.com" -UseVersion Windows8
```

This command enables hosted cache client mode with two hosted cache servers:  HC1.contoso.com and HC2.contoso.com.
For HTTP, use Windows 8 mode (`Windows8`).

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

### -ServerNames
Specifies the names of the hosted cache servers that the client computer can use to store content and obtain content.

```yaml
Type: String[]
Parameter Sets: ServerNames
Aliases:

Required: True
Position: 1
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

### -UseSCP
Indicates that the client should locate hosted cache servers by using service connection points (SCP).
A service connection point is an Active Directory object used to publish service specific data.
A hosted cache server may register a service connection point object associated with the active directory site in which it resides.
This is achieved with the *RegisterSCP* parameter on the **Enable-BCHostedServer** cmdlet.

If this parameter is specified, then this computer attempts to automatically discover a hosted cache server associated with the assigned active directory site by searching for an SCP.

```yaml
Type: SwitchParameter
Parameter Sets: UseSCP
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseVersion
Specifies the version of the offer protocol to use when contacting this hosted cache server.

This parameter controls which protocol the client should use when communicating with the hosted cache server.
The value `Windows8` specifies that the client uses HTTP.
The value `Windows7` specifies that the client uses HTTPS.
If this parameter is not specified, and a hosted cache server name is provided, then a value of `Windows8` is used.
If the *UseSCP* parameter is used, then a value of `Windows7` is used.

Hosted cache servers that are running Windows Server® 2012 do not need to enroll a certificate, and client computers can contact these servers to store or obtain content by using the HTTP protocol on the TCP port `80`.
However, Windows® 7-based hosted cache servers must have a certificate enrolled, and can only be contacted when client computers use the HTTPS protocol on the TCP port `443`.

Note: Windows® 7-based computers can only contact hosted cache servers by using the HTTPS protocol; because of this, a hosted cache server that is running Windows Server 2012 can be configured to accept requests over both HTTP and HTTPS so that the hosted cache server can operate with Windows® 7-based computers and with client computers that are running Windows® 8.

```yaml
Type: HostedCacheVersion
Parameter Sets: ServerNames
Aliases:
Accepted values: Windows7, Windows8

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

### None

## NOTES

## RELATED LINKS

[Enable-BCHostedServer](./Enable-BCHostedServer.md)

