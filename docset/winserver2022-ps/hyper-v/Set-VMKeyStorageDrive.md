---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 08/27/2021
online version: https://docs.microsoft.com/powershell/module/hyper-v/set-vmkeystoragedrive?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMKeyStorageDrive
---

# Set-VMKeyStorageDrive

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### VMName (Default)
```
Set-VMKeyStorageDrive [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String> [[-ControllerNumber] <Int32>] [[-ControllerLocation] <Int32>] [-ToControllerNumber <Int32>]
 [-ToControllerLocation <Int32>] [-ResourcePoolName <String>] [-AllowUnverifiedPaths] [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Object
```
Set-VMKeyStorageDrive [-VMKeyStorageDrive] <KeyStorageDrive[]> [-ToControllerNumber <Int32>]
 [-ToControllerLocation <Int32>] [-ResourcePoolName <String>] [-AllowUnverifiedPaths] [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
{{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AllowUnverifiedPaths
{{ Fill AllowUnverifiedPaths Description }}

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
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-v hosts. NetBIOS names, IP addresses, and fully qualified domain names
are allowable. The default is the local computer. Use localhost or a dot (.) to specify the local
computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerLocation
Specifies the number of the location on the controller.
If not specified, the number of the first available location on the controller is used.

```yaml
Type: Int32
Parameter Sets: VMName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber
Specifies the number of the controller.

If not specified, this parameter assumes the value of the first available controller at the location specified in the **ControllerLocation** parameter.

```yaml
Type: Int32
Parameter Sets: VMName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the storage drive to be configured.

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

### -ResourcePoolName
Specifies the friendly name of a resource pool.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToControllerLocation
{{ Fill ToControllerLocation Description }}

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

### -ToControllerNumber
{{ Fill ToControllerNumber Description }}

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

### -VMKeyStorageDrive
{{ Fill VMKeyStorageDrive Description }}

```yaml
Type: KeyStorageDrive[]
Parameter Sets: Object
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
{{ Fill VMName Description }}

```yaml
Type: String
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.KeyStorageDrive[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.KeyStorageDrive

## NOTES

## RELATED LINKS
