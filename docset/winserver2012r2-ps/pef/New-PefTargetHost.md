---
external help file: Microsoft.Protocols.Tools.PowerShell.dll-Help.xml
Module Name: PEF
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/pef/new-peftargethost?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-PefTargetHost
---

# New-PefTargetHost

## SYNOPSIS
Creates a target host object for a PEF Live Trace Session.

## SYNTAX

```
New-PefTargetHost [-ComputerName] <String> [[-Credential] <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **New-PefTargetHost** cmdlet creates a target host object that you specify as a target computer for remote tracing.
You can target and add multiple computers to a Protocol Engineering Framework (PEF) Live Trace Session that you create by using this cmdlet.
Use the object that this cmdlet creates as input to the Add-PefProviderConfig cmdlet.

This cmdlet uses the current user credentials by default.
Provide other credentials by specifying the **Credentials** parameter as described in Example 2.

Note that this cmdlet enables the Microsoft-Pef-WFP-MessageProver for remote tracing.
You can use this provider to capture remote traffic on a remote Windows 10 host only, and while running on a Windows 8.1, Windows Server 2012 R2, or Windows 10 computer only.

## EXAMPLES

### Example 1: Create a target host to use for a remote session
```
PS C:\> $TargetHost = New-PefTargetHost -ComputerName "Server21"
PS C:\> $Th1p1Config = $TargetHost | Add-PefProviderConfig -Provider "Microsoft-Windows-NDIS-PacketCapture"
PS C:\> $TraceSession01 = New-PefTraceSession -Force -Path "C:\Trace01" -SaveOnStop | Add-PefMessageSource -Source $TargetHost | Start-PefTraceSession
```

The first command creates a target host for the computer named Server21, by using the current cmdlet, and then stores that host in the **$TargetHost** variable.
Because this command does not specify credentials, the command uses the current credentials.

The second command passes the host stored in **$TargetHost** to the Add-PefProviderConfig cmdlet, by using the pipeline operator.
The command also adds a provider, and then stores the result in the **$Th1p1Config** variable.
The Microsoft-Windows-NDIS-PacketCapture provider captures traffic at the Link Layer and above.
Alternatively, you can use the Microsoft-PEF-WFP-MessageProvider provider to capture traffic above the IP/Network layer.

The final command creates a session, adds the target host as the session source, and then starts the remove Live Trace Session, by using the New-PefTraceSession, Add-PefMessageSource, and Start-PefTraceSession cmdlets.
The command stores the new session in the **$TraceSession01** variable.
This session encapsulates the configuration settings of the previous commands in this example.

### Example 2: Create a target host by using credentials
```
PS C:\> $Credential = Get-Credential
PS C:\> $TargetHost = New-PefTargetHost -ComputerName "Server21" -Credential $Credential
PS C:\> $Th1p1Config = $TargetHost | Add-PefProviderConfig -Provider "Microsoft-Windows-NDIS-PacketCapture"
PS C:\> $TraceSession01 = New-PefTraceSession -Force -Path "C:\Trace01" -SaveOnStop | Add-PefMessageSource -Source $TargetHost | Start-PefTraceSession
```

This example resembles the previous example, but it also includes credentials.

The first command creates a credential by using the Get-Credentialhttp://go.microsoft.com/fwlink/?LinkID=293936 cmdlet, and stores the resulting **PSCredential** object in the **$Credential** variable.
The **Get-Credential** cmdlet prompts you for user name and password.
For more information, type `Get-Help Get-Credential`.

The second command creates the target host as the computer named Server21 by using the current cmdlet, and then stores that host in the **$targetHost** variable.
This command also specifies **$Credential** for the **Credential** parameter.

The third and fourth commands are the same as the second and third commands of the previous example.

## PARAMETERS

### -ComputerName
Specifies the name of the target host computer on which to run a Live Trace Session.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Specifies credentials, as a **PSCredential** object, for the target computer specified by the **ComputerName** parameter.
To obtain a **PSCredential** object, use the Get-Credentialhttp://go.microsoft.com/fwlink/?LinkID=293936 cmdlet.
For more information, type `Get-Help Get-Credential`.

If you do not specify a value for this parameter, this cmdlet uses the current credentials.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

[Add-PefMessageSource](./Add-PefMessageSource.md)

[Add-PefProviderConfig](./Add-PefProviderConfig.md)

[New-PefTraceSession](./New-PefTraceSession.md)

[Start-PefTraceSession](./Start-PefTraceSession.md)

