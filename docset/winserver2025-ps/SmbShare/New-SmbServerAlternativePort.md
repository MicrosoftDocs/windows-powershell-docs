---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbServerAlternativePort.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/new-smbserveralternativeport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-SmbServerAlternativePort
---

# New-SmbServerAlternativePort

## SYNOPSIS
Creates a new alternative port for the Server Message Block (SMB) protocol on the local server.

## SYNTAX

```
New-SmbServerAlternativePort [-TransportType] <TransportType> [-Port] <UInt16>
 [-EnableInstances] <Instance> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `New-SmbServerAlternativePort` cmdlet creates a new alternative port for the Server Message
Block (SMB) protocol on the local server. This cmdlet can be used to add a new port to the list of
alternate ports that are available for SMB connections.

## EXAMPLES

### Example 1: Create a new SMB server alternative port

```powershell
New-SmbServerAlternativePort -TransportType QUIC -Port 1
```

This command creates a new SMB server alternative port that uses TCP transport on port number
**1**.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

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

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

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

### -EnableInstances

Enables alternative ports on SMB instances. Currently only the **Default** instance is allowed.
This setting is not used.

```yaml
Type: Instance
Parameter Sets: (All)
Aliases:
Accepted values: None, Default

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Port

Specifies the port number that the SMB connection should use.

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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

### -TransportType

Specifies the transport protocol to use for the SMB connection. The only accepted value for this
parameter is `QUIC`.

```yaml
Type: TransportType[]
Parameter Sets: (All)
Aliases:
Accepted values: QUIC

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SmbServerAlternativePort.TransportType

### System.UInt16

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SmbServerAlternativePort.Instance

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[Get-SmbServerAlternativePort](Get-SmbServerAlternativePort.md)

[Remove-SmbServerAlternativePort](Remove-SmbServerAlternativePort.md)

[Set-SmbServerAlternativePort](Set-SmbServerAlternativePort.md)
