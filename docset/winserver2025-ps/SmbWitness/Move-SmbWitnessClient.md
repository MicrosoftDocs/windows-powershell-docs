---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbWitnessWmiClient.cdxml-help.xml
Module Name: SmbWitness
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbwitness/move-smbwitnessclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-SmbWitnessClient
---

# Move-SmbWitnessClient

## SYNOPSIS
Requests an SMB client to move the associated SMB connection to a specified cluster node.

## SYNTAX

```
Move-SmbWitnessClient [-ClientName] <String> [-DestinationNode] <String> [[-NetworkName] <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Move-SmbWitnessClient** cmdlet requests the specified Server Message Block (SMB) client to move the associated SMB connection from the current cluster node to the specified cluster node.
Only SMB connections to a Distributed Server Name can be moved.

## EXAMPLES

### Example 1: Move a client
```
PS C:\>Move-SmbWitnessClient -ClientName "Server01" -DestinationNode "FileServer22" -NetworkName "NetName07"
```

This example requests that the SMB client named Server01 move the associated SMB connection from the current cluster node to the cluster node named FileServer22.
This cmdlet does not return any output.
The Get-SmbOpenFile cmdlet can be used to validate the client that is moved.
The specified SMB client must have an active connection with the cluster for this cmdlet to be effective.

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

### -ClientName
Specifies the SMB client by name.

```yaml
Type: String
Parameter Sets: (All)
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationNode
Specifies the destination cluster node by name.

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

### -NetworkName
Specifies the network name of the file server to which the client connects.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-SmbWitnessClient](./Get-SmbWitnessClient.md)

