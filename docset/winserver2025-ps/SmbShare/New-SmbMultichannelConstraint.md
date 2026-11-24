---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbMultichannelConstraint.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/new-smbmultichannelconstraint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-SmbMultichannelConstraint
---

# New-SmbMultichannelConstraint

## SYNOPSIS
Creates an SMB multi-channel constraint for the specified server.

## SYNTAX

### ByInterfaceIndex (Default)
```
New-SmbMultichannelConstraint [-ServerName] <String> [-InterfaceIndex] <UInt32[]> [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInterfaceAlias
```
New-SmbMultichannelConstraint [-ServerName] <String> [-Force] [-InterfaceAlias] <String[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SmbMultichannelConstraint** cmdlet creates a Server Message Block (SMB) multi-channel constraint for the specified server. This constraint applies to the Default instance of SMB used for normal sharing. It does not apply to SMB-using application instances like Storage Replica, Storage Spaces Direct SBL, or CSV.

## EXAMPLES

### Example 1: Create an SMB multi-channel constraint for an SMB server
```
PS C:\>New-SmbMultichannelConstraint -ServerName "Contoso-SO" -InterfaceAlias "RDMA1", "RDMA2"
Confirm
Are you sure you want to perform this action?
Performing operation 'New-SmbMultichannelConstraint' on Target 'Contoso-SO'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y

InterfaceAlias : RDMA1
InterfaceGuid  : {597b0a73-2b66-4be0-9e6d-f42eae8a35d6}
InterfaceIndex : 12
ServerName     : Contoso-SO
PSComputerName :

InterfaceAlias : RDMA2
InterfaceGuid  : {bd3c4a04-64cf-4205-88f5-38c4c35dfc38}
InterfaceIndex : 15
ServerName     : Contoso-SO
PSComputerName :
```

This command creates an SMB multi-channel constraint for the SMB server named Contoso-SO.

### Example 2: Create an SMB multi-channel constraint for an SMB server without confirmation
```
PS C:\>New-SmbMultichannelConstraint -ServerName "Contoso-SO" -InterfaceIndex 12, 15 -Force
InterfaceAlias : RDMA1
InterfaceGuid  : {597b0a73-2b66-4be0-9e6d-f42eae8a35d6}
InterfaceIndex : 12
ServerName     : Contoso-SO
PSComputerName :

InterfaceAlias : RDMA2
InterfaceGuid  : {bd3c4a04-64cf-4205-88f5-38c4c35dfc38}
InterfaceIndex : 15
ServerName     : Contoso-SO
PSComputerName :
```

This command creates an SMB multi-channel constraint for the SMB server named Contoso-SO without user confirmation.

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

### -InterfaceAlias
Specifies the interface aliases of the network interfaces that is used to connect to the server.

```yaml
Type: String[]
Parameter Sets: ByInterfaceAlias
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies the interface indexes of the network interfaces that are used to connect to the server.

```yaml
Type: UInt32[]
Parameter Sets: ByInterfaceIndex
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies, when the SMB client is connecting to this server, that the constraints determine which network interfaces are used.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbMultiChannelConnection
This cmdlet returns a **MSFT_SmbMultiChannelConnection** object that represents the SMB multi-channel constraints for the server against which one or more constraints are created.

## NOTES

## RELATED LINKS

[Get-SmbMultichannelConstraint](./Get-SmbMultichannelConstraint.md)

[Remove-SmbMultichannelConstraint](./Remove-SmbMultichannelConstraint.md)

