---
external help file: WmsCmdlets.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/06/2017
online version: https://learn.microsoft.com/powershell/module/multipoint/get-wmsapp?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmsApp
---

# Get-WmsApp

## SYNOPSIS
Returns the currently running application in the specified session.

## SYNTAX

```
Get-WmsApp [-SerializeString] -SessionId <UInt32> [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-WmsApp cmdlet returns the currently running application in the specified session.
It also returns the process ID and window ID of the application.

## EXAMPLES

### Example
```
PS C:\> get-wmsapp -sessionid 3
Name                                                                                         ProcId                                              hWnd                                        CreateTime

----                                                                                         ------                                              ----                                        ----------

Calculator                                                                                     4228                                            197108                                129937600254314944
```

The output is a list of the applications that are running in the session.

### 1:
```
PS C:\>
```

## PARAMETERS

### -SerializeString
Returns data in XML format.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionId
Specifies a Remote Desktop Session (RDS) using SessionID.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Describes what would happen if you executed the command without actually executing the command.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

###  
Returns WmsRunningApp collection as PSObject collection.

## NOTES

## RELATED LINKS

