---
external help file: SmbMultichannelConstraint.cdxml-help.xml
Module Name: SmbShare
online version: 
schema: 2.0.0
title: Remove-SmbMultichannelConstraint
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 382A020C-5DD3-49CE-BBC4-7095E8EF7B48
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-SmbMultichannelConstraint

## SYNOPSIS
Removes one or more specified Server Message Block (SMB) multi-channel constraints, which determine the network interfaces to be used when connecting to specific servers.

## SYNTAX

### ByInterfaceIndex (Default)
```
Remove-SmbMultichannelConstraint [-ServerName] <String[]> [[-InterfaceIndex] <UInt32[]>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByInterfaceAlias
```
Remove-SmbMultichannelConstraint [-ServerName] <String[]> [[-InterfaceAlias] <String[]>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-SmbMultichannelConstraint -InputObject <CimInstance[]> [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SmbMultichannelConstraint** cmdlet removes one or more specified Server Message Block (SMB) multi-channel constraints, which determine the network interfaces to be used when connecting to specific servers.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-SmbMultichannelConstraint -ServerName Contoso-SO
Confirm 
Are you sure you want to perform this action? 
Performing operation 'Remove-SmbMultiChannelConstraint' on Target 'Contoso-SO,{597b0a73-2b66-4be0-9e6d-f42eae8a35d6}'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N 
 
Confirm 
Are you sure you want to perform this action? 
Performing operation 'Remove-SmbMultiChannelConstraint' on Target 'Contoso-SO,{bd3c4a04-64cf-4205-88f5-38c4c35dfc38}'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
```

This example removes one or more specified SMB multi-channel constraints, which determine the network interfaces to be used when connecting to specific servers.

### EXAMPLE 2
```
PS C:\>Remove-SmbMultichannelConstraint -ServerName Contoso-SO -InterfaceIndex 12 -Force
```

This example removes one or more specified SMB multi-channel constraints, which determine the network interfaces to be used when connecting to specific servers without user confirmation.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InterfaceAlias
Specifies one or more interface aliases of the network interfaces that are no longer used by SMB to connect to the server.

```yaml
Type: String[]
Parameter Sets: ByInterfaceAlias
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies one or more interface indexes of the network interfaces that are no longer used by SMB to connect to the server.

```yaml
Type: UInt32[]
Parameter Sets: ByInterfaceIndex
Aliases: 

Required: False
Position: 2
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

### -ServerName
Specifies the server from which to remove one or more constraints

```yaml
Type: String[]
Parameter Sets: ByInterfaceIndex, ByInterfaceAlias
Aliases: 

Required: True
Position: 1
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

### None

## NOTES

## RELATED LINKS

[Get-SmbMultichannelConstraint](./Get-SmbMultichannelConstraint.md)

[New-SmbMultichannelConstraint](./New-SmbMultichannelConstraint.md)

