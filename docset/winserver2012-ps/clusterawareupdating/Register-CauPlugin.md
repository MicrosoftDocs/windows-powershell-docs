---
external help file: ClusterAware_Cmdlets.xml
Module Name: ClusterAwareUpdating
online version: https://docs.microsoft.com/powershell/module/clusterawareupdating/register-cauplugin?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Register-CauPlugin

## SYNOPSIS
Registers a Cluster-Aware Updating (CAU) software updating plug-in on the local computer.

## SYNTAX

```
Register-CauPlugin [-Path] <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Register-CauPlugin** cmdlet registers a Cluster-Aware Updating (CAU) software updating plug-in on the local computer. 

CAU always uses a plug-in when performing updates, although you do not need to register a plug-in because CAU uses the Microsoft.WindowsUpdatePlugin plug-in by default.
This plug-in communicates with the Windows Update Agent software resident on each node, the same software that is used when updates are downloaded from Windows Update or Microsoft Update, or from a Windows Server Update Services (WSUS) server.
For more information about how plug-ins work in CAU, see the content about Cluster-Aware Updating plug-inshttp://go.microsoft.com/fwlink/p/?LinkId=235333.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Register-CauPlugin -Path c:\PluginDevelopment\Plugin01.dll -Force
```

The example registers a plug-in called Plugin01.dll located in the C:\PluginDevelopment folder.
The cmdlet runs without displaying confirmation prompts.

## PARAMETERS

### -Path
Specifies the path to the binary that implements the plug-in.
Classes that implement the plug-in interface and are decorated with the plug-in attribute, are discovered through reflection and registered.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauPlugin

## NOTES

## RELATED LINKS

[Get-CauPlugin](./Get-CauPlugin.md)

[Unregister-CauPlugin](./Unregister-CauPlugin.md)

