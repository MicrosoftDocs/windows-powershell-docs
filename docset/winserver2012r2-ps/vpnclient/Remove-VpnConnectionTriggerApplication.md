---
external help file: PS_VpnConnectionTriggerApplication_v1.0.cdxml-help.xml
Module Name: VpnClient
online version: 
schema: 2.0.0
title: Remove-VpnConnectionTriggerApplication
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: C5D31872-B56B-4E13-8CAC-E1F83042F2CF
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-VpnConnectionTriggerApplication

## SYNOPSIS
Removes a trigger application from a VPN connection object.

## SYNTAX

```
Remove-VpnConnectionTriggerApplication [-ConnectionName] <String> [-ApplicationID] <String[]> [-PassThru]
 [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VpnConnectionTriggerApplication** cmdlet removes a trigger application from a VPN connection object.
After you remove an application from the VPN connection, when the client accesses that application, it no longer triggers the VPN connection.

## EXAMPLES

### Example 1: Remove a VPN connection trigger application
```
PS C:\> Remove-VpnConnectionTriggerApplication -ConnectionName "Contoso" -ApplicationID "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe","Microsoft.RemoteDesktop_Contoso0987" -PassThru -Force
ConnectionName : Contoso

ApplicationID  : {C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe, Microsoft.RemoteDesktop_Contoso0987}
```

This command uses the Remove-VpnConnectionTriggerApplication cmdlet to remove the trigger applications by using the **ApplicationID** parameter.
The command also specifies the **PassThru** and **Force** parameters.

## PARAMETERS

### -ApplicationID
Specifies an array of unique identifiers for an application.
For legacy desktop applications, the application identifier is the application path.
For modern applications, it is the Package Family Name of the application.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -ConnectionName
Specifies the name of a VPN connection profile.
To view existing VPN connection profiles, use the Get-VpnConnection cmdlet.

A VPN connection profile includes connection types, group policy settings, and names of authentication, authorization, and accounting servers.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Performs the action without a confirmation message.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.
If you specify this parameter, the cmdlet returns the **VpnConnectionTriggerApplication** object that contains the applications configured for VPN trigger.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnConnectionTriggerApplication

## NOTES

## RELATED LINKS

[Add-VpnConnectionTriggerApplication](./Add-VpnConnectionTriggerApplication.md)

