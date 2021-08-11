---
external help file: ClusterHCSVM.cdxml-help.xml
Module Name: FailoverClusters
online version:
schema: 2.0.0
---

# New-ClusterHCSVM

## SYNOPSIS
Creates a new instance of an HCS VM resource.

## SYNTAX

```
New-ClusterHCSVM [-Name] <String> [-SwitchName <String>] [-ExtendedVmConfiguration <String>]
 [-MemorySizeInMb <UInt32>] [-CpuCount <UInt32>] [-VhdPath <String>] [-VmName <String>]
 [-OfflineAction <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

Use this cmdlet to create a new instance of an HCS VM resource. When an HCS
VM resource is created, it renames the resource. For example, if you create an HCS VM resource
and name the resource **HcsRes** using the **Name** parameter, the resource name is translated to **HCS Virtual Machine HcsRes**.

You can verify using **Get-ClusterResource** which shows the list of resources on the cluster.

## EXAMPLES

### Example 1
```powershell
New-ClusterHCSVM -Name "hcstest" -VhdPath c:\vhd.vhdx -SwitchName TestSwitch -MemorySizeInMb 4096 -CpuCount 2
```
```Output
Name           : HCS Virtual Machine hcsres
SwitchName     : TestSwitch
MemorySizeInMb : 4096
CpuCount       : 2
VhdPath        : c:\vhd.vhdx
OfflineAction  : 0
VmName         : hcsres
```

After creating the HCS VM, a list of information is returned. The **Name** of the resource has been changed. However, the group name (**VmName**) remains the same.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](/powershell/module/microsoft.powershell.core/receive-job) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) or [Get-CimSession](/powershell/module/CimCmdlets/Get-CimSession) cmdlet.
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

### -CpuCount

Specifies how many CPU cores are used. This parameter has a **default** value of 1.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedVmConfiguration

Specify a VM configuration setting file. The configuration file format is JSON.

The following example show how to pass a configuration file via parameter:
> -ExtendedVmConfiguration (Get-Content 'C:\config.txt')

Ensure that you use **Get-Content** when passing the configuration file. A **default**
ExtendedVmConfiguration is used when the resource is started.

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

### -MemorySizeInMb

Specify the amount of memory you want to allocate for your VM. This parameter has a **default** value of 1024mb. This parameter also has a minimum amount that may be passed in. You cannot pass a value lower than **32mb**. Values lower than 32mb result in a minimum value of 32mb.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Name of resource you are creating. This value is used to create the full name of the HCS VM
resource.

For example, if you used the value **hcsres** the full name of the HCS VM resource is **HCS Virtual Machine hcsres**.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OfflineAction
Action taken when shutting the VM off. This parameter is **not required** and has a **default**
value of 0. You can set a value anywhere from 0-2.

- **Save (0) [Save state]**
- **Shutdown (1) [Graceful shutdown]**
- **Poweroff (2) [Ungraceful shutdown]**

To use **Shutdown (1) [Graceful shutdown]**, you must have GCS enabled. This can be passed in via
the ExtendedVmConfiguration parameter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SwitchName

Specifies the name of the switch used for network connectivity on the VM.

> [!IMPORTANT]
> Ensure **every host** on the cluster uses the exact same **SwitchName**.

This parameter is **not required**, but is **required** to start the VM. If you intend on creating a
resource and starting it, you **must** pass in a **SwitchName**.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell&reg; calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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

### -VhdPath

Specifies the path to your VHD. This parameter is **not required** but as with **SwitchName**, it is
required if you plan on starting the VM.

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

### -VmName

Allows you to name the group of the resource. If not used, the group is named the using the **Name**
parameter value.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/MSCluster/MSCluster_HCSVM

## NOTES

## RELATED LINKS
