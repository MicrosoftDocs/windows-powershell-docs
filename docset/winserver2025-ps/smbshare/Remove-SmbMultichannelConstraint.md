---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbMultichannelConstraint.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/remove-smbmultichannelconstraint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-SmbMultichannelConstraint
---

# Remove-SmbMultichannelConstraint

## SYNOPSIS
Removes SMB multi-channel constraints.

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
The **Remove-SmbMultichannelConstraint** cmdlet removes one or more specified Server Message Block (SMB) multi-channel constraints, which determine the network interfaces to use for connections to specific servers.

## EXAMPLES

### Example 1: Remove SMB multi-channel constraints
```
PS C:\>Remove-SmbMultichannelConstraint -ServerName "Contoso-SO"
Confirm
Are you sure you want to perform this action?
Performing operation 'Remove-SmbMultiChannelConstraint' on Target 'Contoso-SO,{597b0a73-2b66-4be0-9e6d-f42eae8a35d6}'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N

Confirm
Are you sure you want to perform this action?
Performing operation 'Remove-SmbMultiChannelConstraint' on Target 'Contoso-SO,{bd3c4a04-64cf-4205-88f5-38c4c35dfc38}'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
```

This command removes one or more SMB multi-channel constraints.
These constraints determine the network interfaces to be used when connecting to specific servers.

### Example 2: Remove SMB multi-channel constraints without confirmation
```
PS C:\>Remove-SmbMultichannelConstraint -ServerName "Contoso-SO" -InterfaceIndex 12 -Force
```

This command removes one or more SMB multi-channel constraints without user confirmation.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies the input object that is used in a pipeline command.

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
Specifies an array of interface aliases of the network interfaces that are no longer used by SMB to connect to the server.

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
Specifies an array of interface indexes of the network interfaces that are no longer used by SMB to connect to the server.

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
Specifies an array of servers from which to remove one or more constraints

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-SmbMultichannelConstraint](./Get-SmbMultichannelConstraint.md)

[New-SmbMultichannelConstraint](./New-SmbMultichannelConstraint.md)

