
# QCM

### do - until
Scripting (40 pts)

What will be the output of the following code? 

```powershell
$value = 10
do
{
    Write-host $value
    $value++
}
until ($value -gt 5)
```

- There will be no output
- 5  
    6  
    7  
    8  
    9  
    10
- 11
- 10

### do - while
Scripting (40 pts)

What will be the output of the following code? 

```powershell
$value = 10
do
{
   $value++
   Write-host $value 
}
while ($value -le 11)
```

- There will be no output
- 10
- 11
- 11  
    12
- 10  
    11
- 10  
    11  
    12

### Hash tables
Scripting (40 pts)

Which statements are correct regarding the following command?

```powershell
$car = @{Brand = "Fiat"; Color = "Red"; Model = "Uno"; Amount = 1}
```

- Running `$car` will output the values in the same order as in the definition
- The following commands will output the same value:  `$car.Amount`, `$car["Amount"]`, `$car[-1]`
- `$car` is an array
- `$car` is a hash table

### Execution policies
Configuration management (20 pts)

You run the following command to check your server execution policies:

```powershell
Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       AllSigned
   UserPolicy       AllSigned
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine    RemoteSigned
```

What can be said about your current execution policies? 

- The `MachinePolicy` policy is controlled via GPO
- You can only execute scripts signed by a valid certificate
- Only the local adminstrators group can change the execution policy associated to the `LocalMachine` scope
- You can change the `UserPolicy` policy with following command:

```powershell
Set-ExecutionPolicy -Scope UserPolicy `
-ExecutionPolicy RemoteSigned​
```

### PowerShell Remoting - using Enter-PSSession
Remoting (20 pts)

You have successfully executed the following command as `user1`:

```powershell
Enter-PSSession -ComputerName Server1
```

What can be said about the effects of this command? 

- Your prompt has changed to:  

```powershell
[server1]: PS C:\Users\user1\Documents>​
```

- You connected to Server1 using the RDP protocol
- You connected to Server1 using the RPC protocol
- You can work remotely on Server1 in the interactive console
- Your prompt has changed to:

```powershell
[server1]: PS C:\Users\remote\Documen
```

### Module instalation
Configuration management (20 pts)

You have the `pspki` module installed on your PC and you want to use it on another PC. What can you do?

- Execute `Find-Module pspki`
- Copy the module directory located in the `$env:PSModule` path on your PC to the other PC
- Browse `www.powershellgallery.com` and use the "Deploy to Azure Automation" button
- Execute `Install-Module pspki` on the other PC

### Module verification
Configuration management (20 pts)

How would you check that the `PSPki` module is installed on your machine?

- 
```powershell
get-module -ListAvailable pspki
```

- 
```powershell
gmo pspki
```

- 
```powershell
Find-Module pspki
```

- 
```powershell
Import-Module pspki
```

### PSProviders and cd HKLM:
Configuration management (20 pts)

In your PowerShell console, you want to browse through the registry using `PSProviders`.

What command would you use to achieve that?

- `cd HKLM:`
- `HKLM:`
- `reg.exe`
- `Get-ChildItem reg:`

### Using ISE - Integrated Scripting Environment
Configuration management (20 pts)

You have logged in to a freshly installed Windows 2012 R2 machine and you want to edit some script using an editor.

What would be the fastest option?

- Install Visual Studio Code
- Install an editor using the following command:
    
```powershell
add-windowsfeature RSAT-AD-AdminCenter​
```

- Open ISE - Integrated Scripting Environment
- Install ISE using the following command

```powershell
install-windowsfeature PoweShell-ISE​
```

### Common parameters
Cmdlet (20 pts)

PowerShell provides a set of "common parameters", which are cmdlet parameters available in any cmdlet.

Select the common parameters provided by PowerShell. 

- `outvariable`
- `invariable`
- `errorvariable`
- `infoaction`

# Text

# Code
