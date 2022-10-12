
각 Microsoft Teams 룸 디바이스에는 자체 리소스 계정이 필요합니다. 리소스 계정은 Teams 룸 디바이스가 로그인하는 계정이며 조직의 사용자가 Teams 룸을 예약하기 위해 초대하는 계정입니다.

리소스 사서함을 만들 때 되풀이 모임을 허용할지, 회의실에서 초대를 자동으로 수락할지 여부, 초대를 수락할 날짜(일)를 지정할 수 있습니다.

> [!TIP]
> 리소스 계정의 이름을 지정할 때는 전자 메일 주소의 시작 부분에 표준 명명 규칙을 사용하는 것이 좋습니다. 이렇게 하면 Azure Active Directory에서 쉽게 관리할 수 있는 동적 그룹을 만드는 데 도움이 됩니다. 예를 들어 Microsoft Teams 룸 연결할 모든 리소스 계정에 "mtr-"을 사용할 수 있습니다.

> [!TIP]
> Exchange Online 및 Azure Active Directory를 사용하여 모든 리소스 계정을 만드는 것이 좋습니다.

다음 탭 중 하나에서 메서드를 사용하여 리소스 계정을 만듭니다.

#### <a name="in-microsoft-365-admin-center"></a>[**Microsoft 365 관리 센터**](#tab/m365-admin-center)

1. Microsoft 365 관리 센터에 로그인합니다.

2. Microsoft 365 테넌트에 대한 관리자 자격 증명을 제공합니다.

3. 왼쪽 패널의 **리소스** 로 이동한 다음, **룸 & 장비를** 선택합니다. 왼쪽 패널에서 이러한 옵션을 사용할 수 없는 경우 **먼저 모두 표시** 를 선택해야 할 수 있습니다.

4. **리소스 추가** 를 선택하여 새 리소스 계정을 만듭니다. 계정의 표시 이름 및 전자 메일 주소를 입력한 다음 **저장** 을 선택합니다.

5. 기본적으로 리소스 계정은 다음 설정으로 구성됩니다.

    - 반복 모임 허용
    - 다음 제한을 벗어나는 모임 자동 거부
      - 예약 기간(일): 180
      - 최대 기간(시간): 24
    - 모임 요청 자동 수락

    변경하려면 **닫기를** 선택하기 전에 **예약 옵션 편집** 을 선택합니다. 나중에 변경하려면 **리소스** > **룸 & 장비** 로 이동하여 리소스 계정을 선택합니다. 그런 다음 **예약 옵션** 에서 **편집** 을 선택합니다.

6. **사용자** > **활성 사용자** 로 이동하고 만든 회의실을 선택하여 속성 패널을 엽니다.

7. 다음으로, 리소스 계정에 암호를 할당합니다. 패널에서 **암호 재설정** 을 선택합니다.

8. 사용자가 공유 디바이스에서 암호를 변경하도록 요구하면 로그인 문제가 발생합니다. **이 사용자가 처음 로그인할 때 암호를 변경하도록 요구하고 암호** **재설정** 을 선택 취소합니다.

또한 이 계정에 대역폭 정책 또는 모임 정책을 적용해야 할 수도 있습니다. 이후 단계에서 사서함 정책을 설정할 수 있습니다.

#### <a name="with-exchange-online"></a>[**Exchange Online**](#tab/exchange-online)

1. [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)에 연결합니다.

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. 기본적으로 회의실 사서함에는 연결된 계정이 없습니다. Microsoft Teams에서 인증할 수 있도록 회의실 사서함을 만들 때 계정을 추가합니다.

    새 리소스 사서함을 만드는 경우:

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```

    이 예제에서는 다음 설정을 사용하여 새 회의실 사서함을 만듭니다.

    - 계정: ConferenceRoom01@contoso.com

    - 이름: ConferenceRoom01

    - 별칭: ConferenceRoom01

    - 계정 암호: P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Exchange 하이브리드 구성을 사용하는 경우 온-프레미스 도메인 계정의 이메일 주소를 추가해야 합니다. 자세한 내용은 [온-프레미스 동기화 및 Office 365 사용자 계정 디렉터리를 참조하세요](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

#### <a name="with-exchange-server"></a>[**Exchange Server**](#tab/exchange-server)

  1. Exchange 관리 셸에 연결합니다. [Exchange 관리 셸을 열](/powershell/exchange/exchange-server/open-the-exchange-management-shell) 거나 [원격 PowerShell을 사용하여 Exchange 서버에 연결합니다](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

  2. 새 회의실 사서함을 만들려면 다음을 수행합니다.

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```

      이 예제에서는 다음 설정을 사용하여 새 회의실 사서함을 만듭니다.

      - 계정: ConferenceRoom01@contoso.com

      - 이름: ConferenceRoom01

      - 별칭: ConferenceRoom01

      - 계정 암호: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**기존 Exchange Room 사서함 수정**](#tab/existing-account)

리소스 계정이 되도록 기존 회의실 사서함을 수정하려면 다음 구문을 사용합니다.

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

다음은 별칭 값이 ConferenceRoom02인 기존 회의실 사서함의 계정을 사용하도록 설정하고 암호를 9898P@$$W 0rd로 설정하는 예제입니다.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Exchange 하이브리드 구성을 사용하는 경우 온-프레미스 도메인 계정의 전자 메일 주소도 추가해야 합니다. 자세한 내용은 [온-프레미스 동기화 및 Office 365 사용자 계정 디렉터리를 참조하세요](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

자세한 구문 및 매개 변수 정보는 [새 사서함 및 Set-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 를 참조 [하세요](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Surface Hub의 Teams 룸에 대해 이 계정을 만드는 경우 이 계정에서도 ActiveSync를 사용하도록 설정해야 합니다. 이렇게 하면 Surface Hub에서 직접 전자 메일을 보낼 수 있으며, 화이트보드와 같은 기능에 사용할 수 있습니다. 자세한 내용은 [디바이스 계정에 ActiveSync 정책 적용(Surface Hub)](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) 을 참조하세요.

---

> [!IMPORTANT]
> 이 리소스 계정만 사용하여 공간을 예약하고 초대를 자동으로 수락하거나 거절하는 경우 설정을 완료했습니다. PSTN 통화에 이 리소스 계정을 사용하는 경우 [Microsoft Teams 추가 기능 라이선스를](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 참조하여 필요한 라이선스를 확인하세요.
