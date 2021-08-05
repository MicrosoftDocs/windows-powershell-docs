---
external help file: ClusterHCSVM.cdxml-help.xml
Module Name: FailoverClusters
online version:
schema: 2.0.0
---

# Set-ClusterHCSVM

## SYNOPSIS
Sets certain settings for the HCS VM 

## SYNTAX

### Query (cdxml) (Default)
```
Set-ClusterHCSVM [[-Name] <String[]>] [-NewName <String>] [-ExtendedVmConfiguration <String>]
 [-OfflineAction <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-ClusterHCSVM -InputObject <CimInstance[]> [-NewName <String>] [-ExtendedVmConfiguration <String>]
 [-OfflineAction <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
With this cmdlet you can set a variaty of settings on the HCS VM

## EXAMPLES

### Example 1
```powershell
PS C:\> Set-ClusterHCSVM -Name "HCS Virtual Machine hcsres" -NewName "newName" -ExtendedVmConfiguration "info" -OfflineAction 0
```

Though you can change certian settings, it is not recommended that you change the name of the resource

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

### -ExtendedVmConfiguration
This are where you can pass in extra settings that you'd like to pass into the VM. You can pass them in via JSON. This would be an example of you'd want to pass it in via parameter

> -ExtendedVmConfiguration (Get-Content 'C:\config.txt') 

Ensure that you use **Get-Content**. This parameter is **not required**, and a **default** ExtendedVmConfiguration will be passed in when the resource is started

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

### -InputObject
This allows you to change settings via powershell object rather than name

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
This fetches the HCS VM via name. Remember to use the updated name **"HCS Virtual Machine YourName"**

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

### -NewName
This will change the name of the HCS VM resource, this is not recommended

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

### -OfflineAction
***
This will be the action taken when shutting the VM off. This parameter is **not required** and has a **default** value of 0. You can set a value anywhere from 0-2

- **Save (0) [Save state]**
- **Shutdown (1) [Graceful shutdown]**
- **Poweroff (2) [Ungraceful shutdown]**

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

### -PassThru
This will output the object that has been changed 

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
