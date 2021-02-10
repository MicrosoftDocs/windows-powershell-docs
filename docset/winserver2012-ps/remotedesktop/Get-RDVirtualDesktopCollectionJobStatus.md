---
external help file: 
ms.assetid: EA5EDA09-8096-4751-9E37-5C848703B4FC
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
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

This command gets the status information of the job that the server most recently ran on the virtual desktop collection named "Virtual Desktop Pool".

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Stop-RDVirtualDesktopCollectionJob](./Stop-RDVirtualDesktopCollectionJob.md)

[Get-RDVirtualDesktopCollection](./Get-RDVirtualDesktopCollection.md)

