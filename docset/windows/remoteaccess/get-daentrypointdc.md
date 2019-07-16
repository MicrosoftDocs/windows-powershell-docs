---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAEntryPointDC_v1.0.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-DAEntryPointDC
ms.reviewer:
ms.assetid: BBECAB94-B1EB-4BB4-A576-16707C60C3A4
---

# Get-DAEntryPointDC

## SYNOPSIS
Retrieves a list of entry points and the associated domain controllers (DCs).

## SYNTAX

```
Get-DAEntryPointDC [-ComputerName <String>] [-EntryPointName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DAEntryPointDC** cmdlet retrieves a list of entry point names and the associated domain controllers (DCs).

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DAEntryPointDC

EntryPointName       : Entry Point 1 
DomainControllerName : dc1.domain1.corp.contoso.com 
 
EntryPointName       : Entry Point 2 
DomainControllerName : dc2.domain2.corp.contoso.com
```

This example displays all of the entry points and the associated DCs.
The output shows that, Entry Point 1 is associated with dc1.domain1.corp.contoso.com and Entry Point 2 is associated with dc2.domain2.corp.contoso.com.

### EXAMPLE 2
```
PS C:\>Get-DAEntryPointDC -EntryPointName "Entry Point 1"
EntryPointName       : Entry Point 1 
DomainControllerName : dc1.domain1.corp.contoso.com
```

This example displays a single entry point and the associated DC.
The output shows that, Entry Point 1 is associated with dc1.domain1.corp.contoso.com.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies the IPv4 or IPv6 address, or host name, of a server or server cluster in the entry point.

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

### -EntryPointName
Specifies the name of the entry point for which DC information should be retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DADomainController[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The array of DADomainController objects contains the following: 

 -- Entry points. 

 -- Associated DCs.

## NOTES

## RELATED LINKS

[Add-DAEntryPoint](./Add-DAEntryPoint.md)

[Get-DAEntryPoint](./Get-DAEntryPoint.md)

[Remove-DAEntryPoint](./Remove-DAEntryPoint.md)

[Set-DAEntryPoint](./Set-DAEntryPoint.md)

[Set-DAEntryPointDC](./Set-DAEntryPointDC.md)

