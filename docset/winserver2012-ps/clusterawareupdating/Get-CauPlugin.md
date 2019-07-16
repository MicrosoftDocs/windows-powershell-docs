---
external help file: ClusterAware_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: F20C0ACB-0F7B-410E-9713-D939F41C7D29
manager: dansimp
---

# Get-CauPlugin

## SYNOPSIS
Retrieves information about one or more software updating plug-ins that are registered on the local computer.

## SYNTAX

```
Get-CauPlugin [[-Name] <String>]
```

## DESCRIPTION
The **Get-CauPlugin** cmdlet retrieves information about one or more software updating plug-ins that are registered on the local computer.
A plug-in can be specified or information can be retrieved about all registered plug-ins. 

CAU always uses a plug-in when performing updates.
The default is the Microsoft.WindowsUpdatePlugin plug-in.
This plug-in communicates with the Windows Update agent, the same software that is used when updates are downloaded from Windows Update or Microsoft Update, or from a Windows Server Update Services (WSUS) server.
For more information about how plug-ins work in CAU, see the content about Cluster-Aware Updating plug-inshttp://go.microsoft.com/fwlink/p/?LinkId=235333.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-CauPlugin | Format-List -Property *
Name       : Microsoft.WindowsUpdatePlugin
BinaryPath : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\ClusterAwareUpdating\ClusterAwareUpdating.dll
ClassName  : MS.Internal.ClusterAwareUpdating.WuaPlugin
Name       : Microsoft.HotfixPlugin
BinaryPath : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\ClusterAwareUpdating\ClusterAwareUpdating.dll
ClassName  : MS.Internal.ClusterAwareUpdating.HotfixPlugin
```

This example gets information about the software updating plug-ins that are registered in the local CAU tool.

## PARAMETERS

### -Name
Specifies the name of the plug-in whose information should be retrieved.
If not specified, then information for all of the registered plug-ins is returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauPlugin

## NOTES

## RELATED LINKS

[Format-List](http://go.microsoft.com/fwlink/?LinkID=113302)

[Register-CauPlugin](./Register-CauPlugin.md)

[Unregister-CauPlugin](./Unregister-CauPlugin.md)

