---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdvirtualdesktopcollectionjobstatus?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDVirtualDesktopCollectionJobStatus
---

# Get-RDVirtualDesktopCollectionJobStatus

## SYNOPSIS
Gets the status of a job on a virtual desktop collection.

## SYNTAX

```
Get-RDVirtualDesktopCollectionJobStatus [-CollectionName] <String> [-ConnectionBroker <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDVirtualDesktopCollectionJobStatus** gets status information for the most recent job that the server ran on a virtual desktop collection.
You can use the **Stop-RDVirtualDesktopCollectionJob** cmdlet to forcibly end a job that is in an unknown state.

## EXAMPLES

### Example 1: Get the status of a job on a virtual desktop collection
```
PS C:\> Get-RDVirtualDesktopCollectionJobStatus -ConnectionBroker "rdcb.contoso.com" -CollectionName "Virtual Desktop Collection"
```

This command gets the status information of the job that the server most recently ran on the virtual desktop collection named Virtual Desktop Pool.

## PARAMETERS

### -CollectionName
Specifies the name of a virtual desktop collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Stop-RDVirtualDesktopCollectionJob](./Stop-RDVirtualDesktopCollectionJob.md)

[Get-RDVirtualDesktopCollection](./Get-RDVirtualDesktopCollection.md)

