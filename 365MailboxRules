# Open up a session to 365 Exchange
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

# Import the session to the current powershell session
Import-PSSession $Session -DisableNameChecking

# Put together a list of all the mailboxes
$getUser = Get-Mailbox * -ResultSize Unlimited
# Put together a list of all the tenant users
$getID = $getUser.WindowsEmailAddress

# Loop over all the users. Initially print out the rules one by one. Uncommenting the final line in the foreach loop will remove each rule.
foreach ($recip in $getID) { 
$rule = Get-InboxRule -Mailbox $recip
$ruleid = $rule.ruleidentity
echo $rule
#Remove-InboxRule -Mailbox $recip $ruleid
}
