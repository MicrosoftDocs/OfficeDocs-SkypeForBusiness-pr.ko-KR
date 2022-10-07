
다른 Microsoft 365 계정과 마찬가지로 새로 만든 리소스 계정의 암호는 일정 기간 후에 자동으로 만료되도록 설정됩니다. 그러나 리소스 계정 암호가 만료되면 로그인한 Teams 룸 디바이스는 만료 날짜에 다시 로그인할 수 없습니다. 

리소스 계정의 암호를 재설정한 다음 각 Teams 룸 디바이스에 다시 로그인하지 않도록 하려면 계정에 대한 암호 만료를 해제할 수 있습니다.
  
> [!NOTE]
> **암호가 만료되지 않도록** 설정하는 것은 공유 Microsoft Teams 디바이스에 대한 요구 사항입니다. 도메인 규칙이 만료되지 않는 암호를 금지하는 경우 각 Teams 디바이스 리소스 계정에 대한 예외를 만들어야 합니다.

다음 탭 중 하나의 단계에 따라 암호 만료를 해제합니다.

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

먼저 Active Directory PowerShell에 연결합니다.

```PowerShell
   Connect-AzureAD
```

그런 다음 [암호가 만료되지 않도록 설정을](/microsoft-365/admin/add-users/set-password-to-never-expire#set-a-password-to-never-expire) 참조하세요.

다음은 계정 ConferenceRoom01@contoso.com 암호가 만료되지 않도록 설정하는 예제입니다.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. MSOnline PowerShell에 연결:

       ```PowerShell
       Connect-MsolService
       ```

       Active Directory에 대한 자세한 내용은 [Azure Active Directory(MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true)를 참조하세요.

2. 다음 구문을 사용하여 암호가 만료되지 않도록 설정합니다.

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    다음은 계정 ConferenceRoom01@contoso.com 암호가 만료되지 않도록 설정하는 예제입니다.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory(온-프레미스)**](#tab/active-directory1-password/)

1. Active Directory PowerShell에 연결:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Active Directory PowerShell에 대한 자세한 내용은 [ActiveDirectory](/powershell/module/activedirectory)를 참조하세요.

2. 다음 구문을 사용하여 암호가 만료되지 않도록 설정합니다.

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    다음은 계정 ConferenceRoom01@contoso.com 암호가 만료되지 않도록 설정하는 예제입니다.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---