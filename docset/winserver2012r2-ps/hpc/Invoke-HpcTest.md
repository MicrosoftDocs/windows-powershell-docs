---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/invoke-hpctest?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-HpcTest
---

# Invoke-HpcTest

## SYNOPSIS
Runs the specified diagnostic tests on one or more specified nodes.

## SYNTAX

### TestNameNodeName (Default)
```
Invoke-HpcTest [-Alias] <String> -NodeName <String[]> [-Parameters <Hashtable>] [[-Company] <String>]
 [-RunTestAs <PSCredential>] [-Scheduler <String[]>] [<CommonParameters>]
```

### TestNameNodeObj
```
Invoke-HpcTest [-Alias] <String> -Node <HpcNode[]> [-Parameters <Hashtable>] [[-Company] <String>]
 [-RunTestAs <PSCredential>] [-Scheduler <String[]>] [<CommonParameters>]
```

### TestNameGroupName
```
Invoke-HpcTest [-Alias] <String> -GroupName <String> [-Parameters <Hashtable>] [[-Company] <String>]
 [-RunTestAs <PSCredential>] [-Scheduler <String[]>] [<CommonParameters>]
```

### TestObjNodeName
```
Invoke-HpcTest -Test <HpcTestCase> -NodeName <String[]> [-Parameters <Hashtable>] [-RunTestAs <PSCredential>] [-Scheduler <String[]>] [<CommonParameters>]
```

### TestObjNodeObj
```
Invoke-HpcTest -Test <HpcTestCase> -Node <HpcNode[]> [-Parameters <Hashtable>] [-RunTestAs <PSCredential>] [-Scheduler <String[]>] [<CommonParameters>]
```

### TestObjGroupName
```
Invoke-HpcTest -Test <HpcTestCase> -GroupName <String> [-Parameters <Hashtable>] [-RunTestAs <PSCredential>] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-HpcTest** cmdlet runs the specified diagnostic tests on one or more specified nodes.
You can specify the diagnostic test by using the alias or by specifying the **HpcTestCase** object for the test.
You can specify the nodes by using the names or by specifying the **HpcNode** objects for the nodes, or you can use the name of a node group that contains the nodes.

## EXAMPLES

### Example 1: Invoke a test by node name
```
PS C:\>Invoke-HpcTest -Alias "ping" -NodeName "ComputeNode1"
```

This command runs the Ping Test on the node named ComputeNode1.

### Example 2: Invoke a test by group name
```
PS C:\>Invoke-HpcTest -Alias "dnstest" -GroupName "MyNodeGroup"
```

This command runs the DNS Test on all of the nodes that belong to the node group named MyNodeGroup.

### Example 3: Get a node and invoke a test
```
PS C:\>Get-HpcNode -Name "MyComputeNode" | Invoke-HpcTest -Alias "ad"
```

This command gets the **HpcNode** object for the node named MyComputeNode, and then runs the Domain Connectivity Test on that node by redirecting that **HpcNode** object to the **Invoke-HpcTest** cmdlet.

### Example 4: Invoke a test and specify its parameters
```
PS C:\>Invoke-HpcTest -Alias "ping" -Parameters @{ Network="Private" ; count=5 } -RunTestAs CONTOSO\someone -NodeName "ComputeNode01"
```

This command runs the Ping Test with the *Network* parameter set to Private and the ping count parameter set to 5 on ComputeNode01, and uses the credentials of the user with the user name of CONTOSO\someone.
A dialog box is displayed to prompt you for the password for the CONTOSO\someone account.

### Example 5: Get a test case and invoke it on a node
```
PS C:\>Get-HpcTest -Alias "ad" | Invoke-HpcTest -NodeName "ComputeNode2"
```

This command gets the **HpcTestCase** object for the Domain Connectivity Test, and then runs that diagnostic test on the node named ComputeNode2 by redirecting that **HpcTestCase** object to the **Invoke-HpcTest** cmdlet.

## PARAMETERS

### -Alias
Specifies the alias for the diagnostic test that you want to run.
Use the Get-HpcTest cmdlet to view the diagnostic tests that are available on the HPC cluster.
You cannot specify both the *Alias* and *Test* parameters.

This parameter was introduced in HPC Pack 2008 R2.
It is not available in previous versions.
It replaced the *Name* parameter.

```yaml
Type: String
Parameter Sets: TestNameNodeName, TestNameNodeObj, TestNameGroupName
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Company
Specifies the company that created the diagnostic test that you want to run.
If you specify the *Company* parameter, you must also specify the *Alias* parameter.
Specify the company if your HPC cluster includes two diagnostic tests with the same alias from different companies.
You cannot specify both the *Company* and *Test* parameters.

This parameter was introduced in HPC Pack 2008 R2.
It is not available in previous versions.
It replaced the *Name* parameter.

```yaml
Type: String
Parameter Sets: TestNameNodeName, TestNameNodeObj, TestNameGroupName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupName
Specifies the name of the node group that contains the nodes on which you want to run the diagnostic tests.
You cannot specify both the *GroupName* parameter and either the *Node* or the *NodeName* parameter.

```yaml
Type: String
Parameter Sets: TestNameGroupName, TestObjGroupName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
Specifies an array of **HpcNode** objects for the nodes on which you want to run the diagnostic tests.
Use the Get-HpcNode cmdlet to get the **HpcNode** objects for the nodes.
You cannot specify both the *Node* parameter and either the *GroupName* or the *NodeName* parameter.

```yaml
Type: HpcNode[]
Parameter Sets: TestNameNodeObj, TestObjNodeObj
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NodeName
Specifies an array of names for the nodes on which you want to run the diagnostic tests.
Use the Get-HpcNode cmdlet to view the names of the nodes in the HPC cluster.
You cannot specify both the *NodeName* parameter and either the *GroupName* or the *Name* parameter.
This parameter is a filter parameter, so you do not receive an error for specifying a node the does not exist in the HPC cluster as long as you specify at least one node that does exist.

```yaml
Type: String[]
Parameter Sets: TestNameNodeName, TestObjNodeName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameters
Specifies the values to use for the parameters of the diagnostic test.
When you specify the hash table for the parameters and values, use the switch name for the parameter as the key name.
For example, the ping test has parameters with the switch names of Network and count, so you can specify the hash table as `@{ Network="Private" ; count=5 }` if you want to use the Private network and a ping count of 5.
Use the Get-HpcTestDetail cmdlet, or contact the company that created the test to determine the parameters available for the diagnostic test and their switch names.

This parameter was introduced in HPC Pack 2008 R2.
It is not available in previous versions.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunTestAs
Specifies the credentials under which you want the commands for the diagnostic test to run.
Use the Get-Credential cmdlet to create a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet displays a dialog box that prompts you to provide a password for the user.

This parameter was introduced in HPC Pack 2008 R2.
It is not available in previous versions.
It replaced the *Name* parameter.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the diagnostic tests and nodes.
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

### -Test
Specifies an **HpcTestCase** object for the diagnostic test that you want to run.
Use the Get-HpcTest cmdlet to get the **HpcTestCase** object for the diagnostic test.
You cannot specify both the *Test* and either *Alias* or *Company* parameters.

```yaml
Type: HpcTestCase
Parameter Sets: TestObjNodeName, TestObjNodeObj, TestObjGroupName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcTestCase, HpcNode[]

## OUTPUTS

### HpcTestResult

## NOTES
* To cancel a diagnostic test run, use the Stop-HpcTestResult cmdlet.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcGroup](./Get-HpcGroup.md)

[Get-HpcNode](./Get-HpcNode.md)

[Get-HpcTest](./Get-HpcTest.md)

[Get-HpcTestDetail](./Get-HpcTestDetail.md)

[Get-HpcTestResult](./Get-HpcTestResult.md)

[Stop-HpcTestResult](./Stop-HpcTestResult.md)
