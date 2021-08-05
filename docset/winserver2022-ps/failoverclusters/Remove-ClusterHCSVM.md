---
external help file: ClusterHCSVM.cdxml-help.xml
Module Name: FailoverClusters
online version:
schema: 2.0.0
---

# Remove-ClusterHCSVM

## SYNOPSIS
Removes an instance of an HCS VM resource.

## SYNTAX

### Query (cdxml) (Default)
```
Remove-ClusterHCSVM [[-Name] <String[]>] [-Force <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-ClusterHCSVM -InputObject <CimInstance[]> [-Force <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This is how we can remove an HCS VM resource from the cluster. You may also use Remove-ClusterGroup -Name "Your_Name" -RemoveResources

## EXAMPLES

### Example 1
```powershell
PS C:\> Remove-ClusterResource -name "HCS Virtual Machine hcsres"
```

No output is shown by default. That being said there can be output using the **PassThru** parameter

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -Force
This parameter is only needed in one instance. If you have a HCS VM resource that is currently running and try to remove it, you'll get the error **ERROR_INVALID_STATE** meaning that the state of the VM (in this case **online**) is preventing it from being removed. If you pass in the values **1** or **$true**, the VM will shut down and then remove itself. 
 
 The **default** value is 0 
 >-Force 1
 >-Force $true

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
You can use this to remove an HCS VM object. You could have something like this

```
$hcsvm = Get-ClusterHCSVM -Name "HCS Virtual Machine hcsvm"
Remove-ClusterHCSVM -InputObject $hcsvm
```

This will remove the HCS VM resource by object

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Here **Name** is used to find the actual resource. This parameter is **required**. Remember, when trying to get an HCS VM resource, always call it by its updated name.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
This will allow you to see the object that has been removed. It will return the same information that was shown with New-ClusterHCSVM

```
Name           : HCS Virtual Machine hcsres
SwitchName     : TestSwitch
MemorySizeInMb : 4096
CpuCount       : 1
VhdPath        : c:\vhd.vhdx
OfflineAction  : 0
VmName         : hcsres
```

You could parse this information into blocks and use them as necessary


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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/MSCLUSTER/MSCluster_HCSVM

## NOTES

## RELATED LINKS
