---
external help file: IpamDhcpConfigurationEvent.cdxml-help.xml
Module Name: IpamServer
online version: 
schema: 2.0.0
title: Remove-IpamDhcpConfigurationEvent
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 26B2D47A-5C46-4DE4-B757-717AA2ECF396
---

# Remove-IpamDhcpConfigurationEvent

## SYNOPSIS
Removes configuration events for DHCP servers from the IPAM database.

## SYNTAX

```
Remove-IpamDhcpConfigurationEvent -EndDate <DateTime> [-PassThru] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IpamDhcpConfigurationEvent** cmdlet removes configuration events for Dynamic Host Configuration Protocol (DHCP) servers from the IP Address Management (IPAM) database.
The cmdlet permanently deletes configuration events through the specified end date.
The end date uses the time zone of the IPAM server.

Use the Get-IpamDhcpConfigurationEvent cmdlet to view configuration events from the IPAM database.

Do not specify the current date as the end date.
The IPAM server collects the configuration events from DHCP servers as part of the next data gathering task, and, therefore, specifying the current date does not result in permanently deleting events from the current day.

The cmdlet does not delete the configuration events from the DHCP servers themselves.

## EXAMPLES

### Example 1: Remove events through the previous day
```
PS C:\> $Today = Get-DatePS C:\>Remove-IpamConfigurationEvent -EndDate $Today.AddDays(-1)
```

This example removes all configuration events through the previous day.

The first command creates a **DateTime** object by using the **Get-Date** cmdlet, and then stores it in the **$Today** variable.
By default, **Get-Date** creates the current date.
For more information about **Get-Date** and **DateTime** objects, type `Get-Help Get-Date`.

The second command removes configuration events from the IPAM database through the previous day.
The command subtracts one day from the **DateTime** object stored in the **$Today** variable, and then specifies that value for the **EndDate** parameter.

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

### -EndDate
Specifies the end date as a **DateTime** object.
The cmdlet removes events through this date from the IPAM database.
To obtain a **DateTime** object, use the **Get-Date** cmdlet.
For more information, type `Get-Help Get-Date`.

Do not specify the current date.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
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

### IpamDhcpConfigurationEvent
Represents a DHCP server configuration event in IPAM.

## NOTES

## RELATED LINKS

[Get-IpamDhcpConfigurationEvent](./Get-IpamDhcpConfigurationEvent.md)

