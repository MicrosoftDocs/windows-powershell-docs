---
external help file: PS_DhcpServerV4MulticastScope_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
online version: 
schema: 2.0.0
title: Remove-DhcpServerv4MulticastScope
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 6C01EE7C-C077-40C1-9203-9A85355B9478
---

# Remove-DhcpServerv4MulticastScope

## SYNOPSIS
Removes multicast scopes.

## SYNTAX

```
Remove-DhcpServerv4MulticastScope [-ComputerName <String>] -Name <String[]> [-Force] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DhcpServerv4MulticastScope** cmdlet removes the specified multicast scopes from the Dynamic Host Configuration Protocol (DHCP) server.
When you remove a multicast scope, the DHCP server cannot assign the range of IP addresses to DHCP clients.

## EXAMPLES

### Example 1: Remove a multicast scope by using a name
```
PS C:\>Remove-DhcpServerv4MulticastScope -Name "Multicast_VideoConference" -ComputerName "DhcpServer01.Contoso.com"
```

This command removes the multicast scope named Multicast_VideoConference from the DHCP server named DhcpServer01.Contoso.com.

### Example 2: Remove a multicast scope without a confirmation
```
PS C:\>Remove-DhcpServerv4MulticastScope -Name "Multicast_AudioConference" -ComputerName "DhcpServer01.Contoso.com" -Force
```

This command removes the multicast scope named Multicast_AudioConference from the DHCP server named DhcpServer01.Contoso.com.
The cmdlet does not prompt the user for confirmation, regardless if the scopes are active or contain active client leases.

### Example 3: Remove inactive multicast scopes
```
PS C:\>Get-DhcpServerv4MulticastScope | Where-Object -FilterScript { $_.State -Eq "Inactive" } | Remove-DhcpServerv4MulticastScope -Force -PassThru
```

This command removes all of the disabled multicast scopes on the DHCP Server service.
The Get-DhcpServerv4MulticastScope cmdlet returns the multicast scope objects and passes the objects to the **Where-Object** cmdlet by using the pipeline operator.
For more information, type `Get-Help Where-Object`.

The **Where-Object** cmdlet filters the multicast scope objects for inactive multicast scopes, and passes the objects to the Remove-DhcpServerv4MulticastScope cmdlet by using the pipeline operator.
The Remove-DhcpServerv4MulticastScope cmdlet removes the inactive scopes.

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
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the DNS name or IP address of the target computer that runs the DHCP Server service.

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

### -Force
Forces the command to run without asking for user confirmation.

If you specify this parameter, the cmdlet removes the scope regardless if there are active leases in the scope.

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

### -Name
Specifies an array of names of multicast scopes.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DhcpServerv4MulticastScope[]

## NOTES

## RELATED LINKS

[Get-DhcpServerv4MulticastScope](./Get-DhcpServerv4MulticastScope.md)

[Set-DhcpServerv4MulticastScope](./Set-DhcpServerv4MulticastScope.md)

[Add-DhcpServerv4MulticastScope](./Add-DhcpServerv4MulticastScope.md)

[Get-DhcpServerv4MulticastScopeStatistics](./Get-DhcpServerv4MulticastScopeStatistics.md)

