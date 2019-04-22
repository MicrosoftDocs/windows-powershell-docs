---
external help file: PS_DAEntryPoint_v1.0.0.cdxml-help.xml
online version: 
schema: 2.0.0
title: Set-DAEntryPoint
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 8ACC3C62-9C15-4433-A5D0-41C338CDB4FB
ms.author: kenwith
ms.reviewer: brianlic
---

# Set-DAEntryPoint

## SYNOPSIS
Configures settings for the entry point.

## SYNTAX

```
Set-DAEntryPoint [-ComputerName <String>] [-Name <String>] [-GslbIP <IPAddress>] [-PassThru]
 [-NewName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DAEntryPoint** cmdlet configures entry point settings, including the name of the server in the entry point, the name of the entry point, and the IP address used for global load balancing on the specified entry point.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DAEntryPoint -Name "Entry Point 1" -NewName "New Entry Point 1" -Force

EntryPointName GslbIp Servers 
-------------- ------ ------- 
New Entry Point 1 0.0.0.0 {da2.domain1.corp.contoso.com}
```

This example renames the entry point named Entry Point 1 to New Entry Point 1.

### EXAMPLE 2
```
PS C:\>Set-DAEntryPoint -Name "Entry Point 1" -GslbIP "10.1.2.44" -Force

EntryPointName GslbIp Servers 
-------------- ------ ------- 
Entry Point 1 10.1.2.44 {da2.domain1.corp.contoso.com}
```

This example sets the IP address 10.1.2.44 used for global load balancing on the entry point named Entry Point 1.

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
Specifies the IPv4 orIPv6 address, or host name, of a server included in the entry point.

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

### -GslbIP
Specifies the IPv4 or IPv6 address used for global load balancing for the entry point.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the entry point.

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

### -NewName
Specifies the new name of the entry point.
This parameter value replaces the value specified in the **Name** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: NewEntryPointName

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DAEntryPoint
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The DAEntryPoint object contains the following properties: 

 -- Entry point name. 

 -- IPv4 or IPv6 address used for global load balancing. 

 -- List of servers in the entry point.

## NOTES

## RELATED LINKS

[Add-DAEntryPoint](./Add-DAEntryPoint.md)

[Get-DAEntryPoint](./Get-DAEntryPoint.md)

[Get-DAEntryPointDC](./Get-DAEntryPointDC.md)

[Remove-DAEntryPoint](./Remove-DAEntryPoint.md)

[Set-DAEntryPointDC](./Set-DAEntryPointDC.md)

