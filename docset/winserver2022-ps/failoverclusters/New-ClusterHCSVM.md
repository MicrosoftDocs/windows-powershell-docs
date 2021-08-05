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
Use this cmdlet to create a new instance of an HCS VM resource. It should be noted that when an HCS VM resource is created, it will rename the resource. For example, when you create an HCS VM resource and under the **Name** parameter you name the resource **HcsRes**, this will be translated to **HCS Virtual Machine HcsRes**. 

> HcsRes -> HCS Virtual Machine HcsRes

You'll see this change when you check the resource using **Get-ClusterResource**, which will show the list of resources on the cluster. You should see your HCS VM resource and its new name!

## EXAMPLES

### Example 1
```powershell
PS C:\> New-ClusterHCSVM -Name "hcstest" -VhdPath c:\vhd.vhdx -SwitchName TestSwitch -MemorySizeInMb 4096 -CpuCount 2 

Name           : HCS Virtual Machine hcsres
SwitchName     : TestSwitch
MemorySizeInMb : 4096
CpuCount       : 2
VhdPath        : c:\vhd.vhdx
OfflineAction  : 0
VmName         : hcsres
```



{{ Add example description here }}

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

### -CpuCount
This parameter specifies how many CPU cores are used. This parameter has a **default** value of 1

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
This is where you can pass in extra settings that you'd like to pass into the VM. You can pass them in via JSON. This would be an example of how you would want to pass it in via parameter

> -ExtendedVmConfiguration (Get-Content 'C:\config.txt') 

Ensure that you use **Get-Content**. A **default** ExtendedVmConfiguration will be passed in when the resource is started

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
This is where you can allocate how much memory you want your VM to use. This parameter has a **default** value of 1024mb.  This parameter also has a min amount that may be passed in. You cannot pass a value lower than **32mb**. Any lower and it will be defaulted to 32mb.

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
This is the name of resource you are creating. This param will be used to create the full name of the HCS VM resource

> Your_Name -> HCS Virtual Machine Your_name

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
This will be the action taken when shutting the VM off. This parameter is **not required** and has a **default** value of 0. You can set a value anywhere from 0-2

- **Save (0) [Save state]**
- **Shutdown (1) [Graceful shutdown]**
- **Poweroff (2) [Ungraceful shutdown]**

It should be noted that to use **Shutdown (1) [Graceful shutdown]**, you must have GCS enabled. This can be passed in via the ExtendedVmConfiguration

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
This is the name of Switch that you'll be passing in to allow network connectivity on the VM. There are a few important things to note about passing in a Switch to a HCS VM. This should go for all resources that use a switch, but you **want to ensure that _every host_ on the cluster has the exact same SwitchName**. 

This parameter is **not required**, but as stated above, will be **required** to actually start the VM. So if you intend on creating this resource and starting it, you **must** pass in a SwitchName.

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

### -VhdPath
This will be the path to your Vhd. This parameter is **not required** but as with SwitchName, it will be required if you plan on starting the VM.

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
This will allow you to name the group of the resource something different. If this param is not passed in, the default name of the group will just be what was passed in under the **Name** parameter

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
