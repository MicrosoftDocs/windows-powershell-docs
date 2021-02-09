---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Remove-HpcTest
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-HpcTest

## SYNOPSIS
Removes the diagnostic test with the specified alias from the HPC cluster.

## SYNTAX

### TestName (Default)
```
Remove-HpcTest [-Alias] <String> [-Company <String>] [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TestObject
```
Remove-HpcTest -Test <HpcTestCase> [-Scheduler <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcTest** cmdlet removes the diagnostic test with the specified alias from the HPC cluster.
You can use an alias or an **HPCTestCase** object to specify the diagnostic test to remove.
Use the Get-HpcTest cmdlet to view the aliases of diagnostic tests on the HPC cluster or to get the **HPCTestCase** object for a specific test.

## EXAMPLES

### Example 1: Remove a test by name
```
PS C:\>Remove-HpcTest -Alias "diskspace"
```

This command removes the diagnostic test with an alias of diskspace from the HPC cluster.

### Example 2: Remove a test with no confirmation
```
PS C:\>Remove-HpcTest -Alias "culturetest" -Company "Costoso, Ltd" -Confirm:$False
```

This command removes the diagnostic test with an alias of culturetest from the company Contoso, Ltd.
from the HPC cluster without prompting for confirmation.

### Example 3: Get a test and remove it
```
PS C:\>Get-HpcTest -Alias "exceltest" | Remove-HpcTest
```

This command gets the **HpcTestCase** object for the diagnostic test with an alias of exceltest, and then removes that diagnostic test from the HPC cluster by redirecting the **HpcTestCase** object to the input of the **Remove-HpcTest** cmdlet.

## PARAMETERS

### -Alias
Specifies the alias of the diagnostic test that you want to remove from the HPC cluster.
You cannot specify both the *Alias* and *Test* parameters.
To view a list of the diagnostic tests available on the HPC cluster, use the Get-HpcTest cmdlet.

```yaml
Type: String
Parameter Sets: TestName
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Company
Specifies the company that created the diagnostic test that you want to remove from the HPC cluster.
If you specify the *Company* parameter, you must also specify the *Alias* parameter.
Specify the company if your HPC cluster includes two diagnostic tests with the same alias from different companies, and you only want information for one of the tests.
You cannot specify both the *Company* and *Test* parameters.

```yaml
Type: String
Parameter Sets: TestName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the HPC cluster for which you want to remove the diagnostic test.
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
Specifies the **HPCTestCase** object for the diagnostic test that you want to remove from the HPC cluster.
Use the Get-HpcTest cmdlet to get an **HPCTestCase** object for a diagnostic test.
You cannot specify the *Test* parameter if you also specify the *Alias* or *Company* parameters.

```yaml
Type: HpcTestCase
Parameter Sets: TestObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### HpcTestCase

## OUTPUTS

### None

## NOTES
* You cannot remove the system tests that Microsoft HPC Pack provides. These system tests have System as the company name.
* If you remove a diagnostic test for the cluster, HPC Pack does not remove the information about the results of the test runs for that diagnostic test. You can still view the results of those test runs with the Get-HpcTestResult and Get-HpcTestResultDetail cmdlets.
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Add-HpcTest](./Add-HpcTest.md)

[Get-HpcTest](./Get-HpcTest.md)

[Invoke-HpcTest](./Invoke-HpcTest.md)
