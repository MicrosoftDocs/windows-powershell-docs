---
external help file: WmsCmdlets.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/06/2017
online version: https://docs.microsoft.com/powershell/module/multipoint/show-wmssystem?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Show-WmsSystem
---

# Show-WmsSystem

## SYNOPSIS
Notifies that the specified remote server is back online.

## SYNTAX

```
Show-WmsSystem -RemoteServer <String> [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Show-WmsSystem cmdlet notifies that the specified remote server is back online.

## EXAMPLES

### Example
```
PS C:\> show-wmssystem -RemoteServer RemoteManagedServer
No output.
```

The Show-WmsSystem cmdlet should be called by a remote server that is managed by the local server when it is ready to accept inbound connections. 
The remote server should specify its system name to the -RemoteServer parameter.

### 1:
```
PS C:\>
```

## PARAMETERS

### -RemoteServer
The name of the remote server that is back online.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutInSecond
The timeout value in seconds before the operation is aborted.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

