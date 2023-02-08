Import-Module .\NanoServerImageGenerator.psm1 -Verbose

$pass = Read-Host "depo724gidra" -AsSecureString

New-NanoServerImage -MediaPath J:\ -BasePath .\Base -TargetPath .\NANO1.vhdx -ComputerName NANO1 -DeploymentType Guest -Edition Standard  -InterfaceNameOrIndex Ethernet -Ipv4Address 192.168.2.22 -Ipv4SubnetMask 255.255.252.0 -Ipv4Gateway 192.168.0.2 -Ipv4Dns 192.168.0.20 -AdministratorPassword $pass

New-VM -name "NANO1" -generation 2 -memorystartupbytes 4GB -vhdpath "C:\Nano1\NANO1.vhdx"

https://software-static.download.prss.microsoft.com/pr/download/17763.737.190906-2324.rs5_release_svc_refresh_SERVERHYPERCORE_OEM_x64FRE_en-us_1.iso

https://software-static.download.prss.microsoft.com/pr/download/Windows_Server_2016_Datacenter_EVAL_en-us_14393_refresh.ISO
