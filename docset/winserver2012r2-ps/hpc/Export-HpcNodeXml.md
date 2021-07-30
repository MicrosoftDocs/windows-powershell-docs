---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/export-hpcnodexml?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-HpcNodeXml
---

# Export-HpcNodeXml

## SYNOPSIS
Exports information about  compute nodes to an XML file.

## SYNTAX

### AllNode (Default)
```
Export-HpcNodeXml -Path <String> [-Force] [-Scheduler <String[]>]
 [<CommonParameters>]
```

### Name
```
Export-HpcNodeXml -Path <String> [-Force] [-Name] <String[]> [-Scheduler <String[]>] [<CommonParameters>]
```

### Node
```
Export-HpcNodeXml -Path <String> [-Force] -Node <HpcNode[]> [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-HpcNodeXml** cmdlet exports information about the specified compute nodes to an XML file.
You can specify the compute nodes by name or by using **HpcNode** objects that you get with the Get-HpcNode cmdlet.

## EXAMPLES

### Example 1: Export a compute node
```
PS C:\>Export-HpcNodeXML -Name "ComputeNode01" -Path "C:\MyNodeXMLFiles\ComputeNode01.xml"
```

This command exports information about the compute node named ComputeNode01 to the XML file located at C:\MyNodeXMLFiles\ComputeNode01.xml.

### Example 2: Get multiple nodes and export them
```
PS C:\>Get-HpcNode -Group NodeGroupA | Export-HpcNodeXML -Path "C:\MyNodeXMLFiles\NodeGroupA.xml" -Force
```

This command gets the **HpcNode** objects for the nodes in the NodeGroupA node group, and then exports information about those nodes to the XML file located at C:\MyNodeXMLFiles\NodeGroupA.xml.
If this XML file already exists, the **Export-HpcNodeXML** cmdlet overwrites it without prompting.

## PARAMETERS

### -Force
Replaces the node XML file if it already exists, without prompting.

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

### -Name
Specifies an array of the names of compute nodes that you want to export.
You cannot specify both the *Name* and *Node* parameters.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
Specifies an array of **HpcNode** objects for the compute nodes that you want to export.
Use the Get-HpcNode cmdlet to get the **HpcNode** objects for the nodes.
You cannot specify both the *Node* and *Name* parameters.

```yaml
Type: HpcNode[]
Parameter Sets: Node
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies a name for the XML file to which you want to export the nodes, including the full or relative path to the file if the **Export-HpcNodeXML** cmdlet should not save the file in the current directory.

This cmdlet creates any directories that do not already exist in that path.
If the file already exists and you do not specify the *Force* parameter, the cmdlet prompts you to confirm whether or not you want to replace the file.

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

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the compute nodes.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcNode

## OUTPUTS

### None

## NOTES
* You cannot export a head node. You can import the node XML file later to add compute nodes to a cluster by using the Import-HpcNodeXml cmdlet. For example, if you export the information about the nodes to a node XML file with the **Export-HpcNodeXML** cmdlet, then remove those nodes from the cluster with the Remove-HpcNode cmdlet to upgrade them or perform maintenance on them, you can add the nodes back to the cluster by importing the node xml file.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcNode](./Get-HpcNode.md)

[Import-HpcNodeXml](./Import-HpcNodeXml.md)

[Remove-HpcNode](./Remove-HpcNode.md)
