$reg = test-path -Path 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\WindowsFeatures\WindowsMediaVersion'
### Check if Media Pack is installed ###
if ($reg -eq 'True') {
Write-Host 'Installed'
# Do nothing
} else {
### Specify domain name if installing from (e.g.) netlogon
wusa.exe "\\#########\netlogon\Windows_MediaFeaturePack_x64_1809Oct.msu" /quiet /norestart 
Write-Host 'Installing...'
get-process *wusa*
}
