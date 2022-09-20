---
external help file: SmbWitnessWmiClient.cdxml-help.xml
Module Name: SmbWitness
online version: https://learn.microsoft.com/powershell/module/smbwitness/move-smbwitnessclient?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Move-SmbWitnessClient

## SYNOPSIS
Requests a Server Message Block (SMB) client to move the associated SMB connection from the current cluster node to the specified cluster node.

## SYNTAX

```
Move-SmbWitnessClient [-ClientName] <String> [-DestinationNode] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Move-SmbWitnessClient** requests the specified Server Message Block (SMB) client to move the associated SMB connection from the current cluster node to the specified cluster node.
Only SMB connections to a Distributed Server Name can be moved.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Move-SmbWitnessClient -ClientName Server1 -DestinationNode FileServer1
```

This example requests that the SMB client named Server1 move the associated SMB connection from the current cluster node to the cluster node named FileServer1.
Note: This cmdlet does not return any output.
The Get-SmbOpenFile cmdlet can be used to validate the client that is moved.
Note: The specified SMB client must have an active connection with the cluster for this cmdlet to be effective.

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

[Get-SmbWitnessClient](./Get-SmbWitnessClient.md)

[Get-SmbOpenFile](../smbshare/Get-SmbOpenFile.md)

