Source: https://o365reports.com/2019/05/09/export-office-365-users-mfa-status-csv/

How can I filter the Output?
Export Office 365 users’ MFA enabled status to CSV file

As an Office 365 admin, often you ask ‘How to check if mfa is enabled in office 365’? Solution is here. You can use –EnabledOnly param in this script. Using this param, you can export Office 365 users’ MFA enabled status to CSV file. 
./GetMFAStatus.ps1 -EnabledOnly
1
    
./GetMFAStatus.ps1 -EnabledOnly

 
Export Office 365 users’ MFA enforced status to CSV file

      Some users may enabled MFA status but not enforced (registration process not completed) for MFA. You can get list of MFA enforced users using -EnforcedOnly param. 
./GetMFAStatus.ps1 -EnforcedOnly
1
    
./GetMFAStatus.ps1 -EnforcedOnly

 
Export Office 365 users’ MFA disabled status to CSV file

        -DisabledOnly param used to filter output that only displays MFA disabled users. i.e,Users without MFA.
./GetMFAStatus.ps1 -DisabledOnly
1
    
./GetMFAStatus.ps1 -DisabledOnly

 
Export Office 365 admins without MFA report to CSV file

         As admin accounts has more privileges, it requires special attention. Using  –AdminOnly param, you can export admin accounts(users) that not protected with MFA.
./GetMFAStatus.ps1 -AdminOnly -DisabledOnly
1
    
./GetMFAStatus.ps1 -AdminOnly -DisabledOnly

 
Export Licensed users’ MFA status report 

          You can use –LicensedUserOnly param to get licensed users’ MFA status   
  ./GetMFAStatus.ps1 -LicensedUserOnly
1
    
  ./GetMFAStatus.ps1 -LicensedUserOnly

 
Export Users’ MFA Status based on SignIn status

         You can use –SignInAllowed param, to filter the result based on SignIn status,

    To list signin allowed users alone, 

./GetMFAStatus.ps1 -SignInAllowed $True
1
    
./GetMFAStatus.ps1 -SignInAllowed $True

    To list signin denied users alone, 

./GetMFAStatus.ps1 -SignInAllowed $False
1
    
./GetMFAStatus.ps1 -SignInAllowed $False

 

Note: 

You can use multiple filters together, to get a more granular result. For example, 

    You can get list of MFA status enabled users whose sign-in status is denied.

  ./GetMFAStatus.ps1 -EnabledOnly –SignInAllowed $False
1
    
  ./GetMFAStatus.ps1 -EnabledOnly –SignInAllowed $False

    You can get list of disabled admin users whose sign-in status is allowed. 

  ./GetMFAStatus.ps1 -DisabledOnly –AdminOnly –SignInAllowed $True
1
    
  ./GetMFAStatus.ps1 -DisabledOnly –AdminOnly –SignInAllowed $True