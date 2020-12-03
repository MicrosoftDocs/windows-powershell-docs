---
external help file: ClusterAware_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: F0EEF063-A47F-4D06-8BC4-332540CB3877
manager: dansimp
---

# Unregister-CauPlugin

## SYNOPSIS
Removes a software updating plug-in from the list of plug-ins that are used by Cluster-Aware Updating (CAU).

## SYNTAX

```
Unregister-CauPlugin [-Name] <String>
```

## DESCRIPTION
The **Unregister-CauPlugin** cmdlet removes a software updating plug-in from the list of plug-ins that are used by Cluster-Aware Updating (CAU).
The plug-in can be removed, but afterwards, it cannot be used for Updating Runs.
The Microsoft.WindowsUpdatePlugin and Microsoft.HotfixPlugin plug-ins, which are installed with CAU, cannot be unregistered.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Unregister-CauPlugin -Name Plugin01
```

This example removes the plug-in named Plugin01 from the list of plug-ins that are used by Cluster-Aware Updating (CAU).

## PARAMETERS

### -Name
Specifies the name of the plug-in to unregister.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauPlugin

## NOTES

## RELATED LINKS

[Get-CauPlugin](./Get-CauPlugin.md)

[Register-CauPlugin](./Register-CauPlugin.md)

