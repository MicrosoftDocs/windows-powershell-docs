---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/initialize-wssdisk?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Initialize-WssDisk
---

# Initialize-WssDisk

## SYNOPSIS
Initializes a disk for sbs_sbs8_2 storage.

## SYNTAX

```
Initialize-WssDisk [-Force] [-Disk] <Disk> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Initialize-WssDisk** cmdlet initializes a disk that you can use for the sbs_sbs8_1 storage system.
The cmdlet formats and creates volumes for sbs_sbs8_2 on the disk that you specify.

## EXAMPLES

### Example 1: Initialize a disk for Windows Server 2012 Essentials storage
```
PS C:\>$Disks = Get-WssDisk -ID "26a21bda-a627-11d7-9931-806e6f6e6963"
PS C:\> Initialize-WssDisk -Disk $Disks
```

The first command gets the Disk object that has the ID 26a21bda-a627-11d7-9931-806e6f6e6963, and stores it in the **$Disks** variable.

The second command initializes the disk stored in the **$Disks** variable.

## PARAMETERS

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

### -Disk
Specifies a Disk object.
To obtain a Disk object, use the Get-WssDisk cmdlet.

```yaml
Type: Disk
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

## OUTPUTS

### Microsoft.WindowsServerSolutions.Storage.Disk
This cmdlet generates the disk for use in the Windows Server Essentials storage system to format and create volumes.

## NOTES

## RELATED LINKS

[Get-WssDisk](./Get-WssDisk.md)

[Add-WssDisksToSpacesPool](./Add-WssDisksToSpacesPool.md)

