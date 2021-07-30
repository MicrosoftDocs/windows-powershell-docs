---
external help file: SMTasks_Cmdlets.xml
Module Name: ServerManagerTasks
online version: https://docs.microsoft.com/powershell/module/servermanagertasks/get-smserverfeature?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-SMServerFeature

## SYNOPSIS
Gets the server features on a target server.

## SYNTAX

```
Get-SMServerFeature [-AsJob] [-BatchSize <UInt32>] [-CimSession <CimSession[]>]
 [-FilterFlag <FeatureFilterFlag>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-SMServerFeature** cmdlet gets the list of features, role services, and roles installed on a target server.

## EXAMPLES

### Example 1:
```
PS C:\>Get-SMServerFeature
```

This command gets the server features on the local server.

## PARAMETERS

### -AsJob
Indicates that the command runs as a background job.

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

### -BatchSize
Specifies the batch size that the command uses to stream results.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterFlag
Specifies a list of features to include in the results.

The filter flag values and names are: 

    --Value=1 Name="Available"

    --Value=2 Name="Installed" 

    --Value=4 Name="Uninstall Pending" 

    --Value=8 Name="Install Pending" 

    --Value=16 Name="Not Present" 

    --Value=32 Name="Removed" 

    --Value=64 Name="Unknown"

```yaml
Type: FeatureFilterFlag
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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ServerFeature[]

## NOTES

## RELATED LINKS



