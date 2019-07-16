---
external help file: MsftSil_ComputerIdentity.cdxml-help.xml
Module Name: SoftwareInventoryLogging
online version: 
schema: 2.0.0
title: Get-SilComputerIdentity
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 6D009E40-457B-4C6A-8572-8A9CC691B411
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Get-SilComputerIdentity

## SYNOPSIS
Gets IDs that identify a Windows installation.
Windows Server 2012 R2 with KB3000850 applied.
For more information, see http://support.microsoft.com/kb/3000850.

## SYNTAX

```
Get-SilComputerIdentity [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SilComputerIdentity** cmdlet gets IDs that identify a Windows installation, or operating system environment.
This cmdlet gets information for both physical and virtual servers.

## EXAMPLES

### Example 1: Get IDs for a virtual machine
```
PS C:\> Get-SilComputerIdentity
ID                 : 961FF8A1-8549-4BEC-8DF6-3B3E32C26FFA
UUID               : B49ACB4C-7D9C-4806-9917-AE750BB3DA84
VMGUID             : E84CCCBD-0D0F-486B-A424-9780C7CF92E4
Name               : Server08Guest.TSQA.Contoso.com
HypervisorHostName : Server08.TSQA.Contoso.com
```

This command gets the IDs for a virtual machine that runs on Hyper-V.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/InventoryLogging/MsftSil_ComputerIdentity

## NOTES

## RELATED LINKS

[Get-SilComputer](./Get-SilComputer.md)

