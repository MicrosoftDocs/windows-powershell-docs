---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_HgsKeyProtector_v1.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: HgsClient
ms.assetid: 3F1EB445-2B71-43EA-85FA-FB84CC2FA261
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: ConvertTo-HgsKeyProtector
ms.reviewer:
---

# ConvertTo-HgsKeyProtector

## SYNOPSIS
Converts a key protector into a Host Guardian Service key protector.

## SYNTAX

```
ConvertTo-HgsKeyProtector [-Bytes] <Byte[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **ConvertTo-HgsKeyProtector** cmdlet converts an existing key protector into a Host Guardian Service key protector object.
Specify the existing key protector as a byte array.
You might use this cmdlet to import a key protector from a virtual machine configuration file.

## EXAMPLES

### Example 1: Convert a key protector
```
PS C:\> $VirtualTPM = Get-VMTPM -Name "Shielded Virtual Machine 17" 
PS C:\> $VirtualMachineKeyProtector = $VirtualTPM.KeyProtector 
PS C:\> $KeyProtector = ConvertTo-HgsKeyProtector -Bytes $VirtualMachineKeyProtector
```

The first command gets the Trusted Platform Module (TPM) object for the virtual machine named Shielded Virtual Machine 17.
The command stores the object in the **$VirtualTPM** variable.

The second command stores the **KeyProtector** property of the object stored in **$VirtualTPM** in the **$VirtualMachineKeyProtector** variable.

The final command creates a Host Guardian Service key protector object from the byte array representation stored in **$VirtualMachineKeyProtector**.
The command stores the new key protector in the **$KeyProtector** variable.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](http://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](http://go.microsoft.com/fwlink/?LinkID=113251).


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

### -Bytes
Specifies the existing key protector as a byte array.
This cmdlet generates a key protector object from the existing key protector that this parameter specifies.

```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_HgsKeyProtector
This cmdlet returns a key protector.

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[New-HgsKeyProtector](./New-HgsKeyProtector.md)

