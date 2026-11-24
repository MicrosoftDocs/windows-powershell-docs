---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Policy.cdxml-help.xml
Module Name: StorageQoS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storageqos/get-storageqospolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageQosPolicy
---

# Get-StorageQosPolicy

## SYNOPSIS
Retrieves a storage QoS policy from the policy manager.

## SYNTAX

### Name (Default)
```
Get-StorageQosPolicy [-Name <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### Id
```
Get-StorageQosPolicy [-PolicyId <Guid[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByParent
```
Get-StorageQosPolicy [-ParentPolicy <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByChild
```
Get-StorageQosPolicy [-ChildPolicy <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByFlow
```
Get-StorageQosPolicy [-Flow <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageQosPolicy** cmdlet retrieves a storage Quality of Service (QoS) policy from the storage QoS Windows Management Instrumentation (WMI) provider.

For more information about Storage QoS, see Storage Quality of Servicehttps://technet.microsoft.com/en-us/library/Mt126108  (https://technet.microsoft.com/en-us/library/Mt126108).

## EXAMPLES

### Example 1: Get a QoS policy by name
```
PS C:\>Get-StorageQosPolicy -Name "Policy01"

Name    MinimumIops MaximumIops Status

----    ----------- ----------- ------

Policy01 10          100         Ok
```

This command gets the QoS policy named Policy01.

### Example 2: Get a parent QoS policy
```
PS C:\>
Get-StorageQosPolicy -ChildPolicy (Get-StorageQosPolicy -Name "Policy02")

Name    MinimumIops MaximumIops Status

----    ----------- ----------- ------

Policy01 10          100         Ok
```

This command gets the parent policy of the policy named Policy02.
If there are hierarchical policies, the hierarchy can be traversed using -ChildPolicy and -ParentPolicy.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -ChildPolicy
Specifies a child policy, for which to retrieve a parent policy.
If the **ChildPolicy** parameter is specified, this cmdlet retrieves any parent policy associated with the input object.

```yaml
Type: CimInstance
Parameter Sets: ByChild
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Flow
Specifies a flow object.
If the **Flow** parameter is specified, this cmdlet retrieves the policy governing the flow input object, if any.

```yaml
Type: CimInstance
Parameter Sets: ByFlow
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the policy, or a wildcard pattern.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentPolicy
Specifies a parent policy for which to retrieve child policies.
If the *ParentPolicy* parameter is specified, this cmdlet retrieves all of the child policies associated with the input object.

```yaml
Type: CimInstance
Parameter Sets: ByParent
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PolicyId
Specifies the GUID of the policy.

```yaml
Type: Guid[]
Parameter Sets: Id
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_StorageQoSPolicy
This cmdlet outputs a Common Information Model (CIM) object of type MSFT_StorageQoSPolicyhttps://msdn.microsoft.com/en-us/library/mt164592(v=vs.85).aspx (https://msdn.microsoft.com/en-us/library/mt164592(v=vs.85).aspx).

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-StorageQoSFlow](./Get-StorageQoSFlow.md)

[Get-StorageQosVolume](./Get-StorageQosVolume.md)

[New-StorageQosPolicy](./New-StorageQosPolicy.md)

[Remove-StorageQosPolicy](./Remove-StorageQosPolicy.md)

[Set-StorageQosPolicy](./Set-StorageQosPolicy.md)

