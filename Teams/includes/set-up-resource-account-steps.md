Microsoft Teams에서는 각 자동 전화 교환 또는 통화 큐에 리소스 계정이 필요합니다. 리소스 계정에 전화 번호가 할당될 수도 있습니다. 자동 전화 교환 및 통화 큐에 전화 번호를 할당하여 Teams 외부의 발신자가 자동 전화 교환 또는 통화 큐에 연결할 수 있도록 하는 방법입니다.

이 문서에서는 리소스 계정을 만들고 자동 전화 교환 및 통화 큐에서 사용할 수 있도록 준비하는 방법을 설명합니다.

이 문서의 절차를 시작하기 전에 다음 단계를 완료했는지 확인합니다.

- [Microsoft Teams 전화 리소스 계정 라이선스 가져오기](#obtain-microsoft-teams-phone-resource-account-licenses)
- [전화 번호 가져오기](#obtain-phone-numbers)

> [!NOTE]
> 자동 전화 교환 및 통화 큐에 사용되는 리소스 계정은 로그인에 사용할 수 없으므로 그대로 유지해야 합니다. 이러한 계정에는 채팅 및 현재 상태를 사용할 수 없습니다.

### <a name="obtain-microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams 전화 리소스 계정 라이선스 가져오기

각 리소스 계정에는 자동 전화 교환 및 통화 큐(**Microsoft Teams 전화 Resource Account** 라이선스라고 함)를 사용하기 위해 라이선스가 필요합니다. Teams Phone이 있는 구독은 자동으로 **Microsoft Teams 전화 리소스 계정** 라이선스를 무료로 할당하며, 더 필요한 경우 추가 **Microsoft Teams 전화 리소스 계정** 라이선스를 구매할 수 있습니다. 이러한 라이선스를 가져오는 방법에 대한 자세한 내용은 [Microsoft Teams 전화 Resource Account 라이선스를 참조하세요](../teams-add-on-licensing/virtual-user.md).

[이 문서의 뒷부분에 있는 리소스 계정에 라이선스를 할당하는](#assign-a-license) 방법에 대해 설명합니다.

통화 플랜 번들 라이선스를 **사용하여 Teams 전화 표준 요금제** 또는 **Teams Phone** 을 구매한 경우 **Teams 전화 리소스 계정** 라이선스는 이미 계정에 있습니다.

**Teams 전화 리소스 계정** 라이선스가 이미 있는지 확인하려면 전역 관리자 권한이 있는 계정을 사용하여 [Microsoft 365 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339) 로그인합니다. 그런 다음 청구 [> 제품으로](https://admin.microsoft.com/Adminportal/Home#/subscriptions) 이동합니다. **Teams 전화 리소스 계정** 라이선스가 있는 경우 **Microsoft Teams 전화 리소스 계정** 으로 표시됩니다.

1. [Microsoft 365 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339) 열고 전역 관리자인 사용자로 로그인합니다. 일반적으로 Microsoft 365에 등록하는 데 사용한 계정입니다.
2. 왼쪽 탐색 창에서 [**청구** > **구매 서비스**](https://admin.microsoft.com/Adminportal/Home#/catalog)**추가 기능** >  > **모든 추가 기능 제품 보기로** 이동합니다.
3. 끝까지 스크롤하여 **Microsoft Teams 전화 Resource Account** 라이선스를 찾습니다. **세부 정보를** 선택한 다음 **구매** 를 선택합니다.
4. 라이선스 구매 페이지에서 원하는 라이선스 수를 선택합니다. 설정하려는 각 자동 전화 교환 및 통화 큐에 대해 하나의 라이선스가 필요합니다. 더 많은 라이선스를 바로 구매하지 않고도 나중에 더 많은 자동 전화 교환 및 통화 큐를 쉽게 설정할 수 있도록 5개 이상의 라이선스를 선택하는 것이 좋습니다.
5. **라이선스가 없는 모든 사용자에게 자동으로 할당을 선택 취소합니다**.
6. **지금 체크 아웃을** 선택합니다.
7. 주문을 확인하고 **다음** 을 선택한 다음 **주문합니다**.

비용은 없지만 라이선스를 획득하려면 다음 단계를 따라야 합니다.

### <a name="obtain-phone-numbers"></a>전화 번호 가져오기

전화 번호는 자동 전화 교환 및 통화 큐에 대한 선택 사항입니다. 전화 번호로 직접 연결할 수 있는 자동 전화 교환 또는 통화 큐의 경우 연결된 전화 번호가 있는 리소스 계정이 있어야 합니다.

리소스 계정은 수신자 또는 무료 전화 번호를 사용할 수 있습니다. 새 번호를 요청하거나 다른 운송업체에서 기존 번호를 포팅할 수 있습니다.

리소스 계정에 적용할 수 있는 허용 가능한 전화 번호는 다음과 같습니다.

- **통화 플랜 서비스 번호:** 통화 플랜을 사용하여 서비스 번호를 가져오려면 [서비스 전화 번호 가져오기를 참조하세요](../getting-service-phone-numbers.md).
- **직접 라우팅 번호:** 직접 라우팅 번호를 가져오려면 [직접 라우팅에 대한 사용자 사용을 참조하세요](/microsoftteams/direct-routing-enable-users#configure-the-phone-number-and-enable-enterprise-voice).
- **연산자 연결 번호:** Operator Connect 번호를 가져오려면 [Operator Connect 구성](/microsoftteams/operator-connect-configure#set-up-phone-numbers)을 참조하세요.

다른 이동 통신 사업자의 번호를 포트하려면 [Teams로 전화 번호 전송을 참조하세요](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>리소스 계정 만들기

Teams 관리 센터에서 리소스 계정을 만들 수 있습니다.

1. [Teams 관리 센터에 로그인합니다](https://go.microsoft.com/fwlink/p/?linkid=2066851). 
2. **음성** 을 확장한 다음 **, 리소스 계정을** 선택합니다.
3. **추가** 를 선택합니다.
4. **리소스 계정 추가** 창에서 **표시 이름**, **사용자** 이름 및 **리소스 계정 유형을 입력합니다**. 리소스 계정 유형은 이 리소스 계정을 사용하는 방법에 따라 **자동 전화 교환** 또는 **통화 큐** 일 수 있습니다.
5. **저장** 을 선택합니다.

## <a name="assign-a-license"></a>라이선스 할당

각 리소스 계정에 대해 **Microsoft Teams 전화 Resource Account** 라이선스를 할당해야 합니다.

1. [Microsoft 365 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339) 로그인합니다. 
2. **사용자를** 확장한 다음 **활성 사용자를** 선택합니다.
3. 라이선스를 할당할 리소스 계정을 선택합니다. 리소스 계정의 사용자 창이 표시됩니다.
4. **라이선스 및 앱** 탭의 **라이선스** 에서 **리소스 계정 Microsoft Teams 전화** 선택합니다.
5. **변경 내용 저장** 을 선택합니다.

## <a name="assign-a-phone-number"></a>전화 번호 할당

전화 번호가 필요한 자동 전화 교환 또는 통화 큐와 함께 리소스 계정을 사용하려는 경우 리소스 계정에 번호를 할당합니다.

1. [Teams 관리 센터에 로그인합니다](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. **음성** 을 확장한 다음 **리소스 계정** 페이지를 선택합니다.
3. 전화 번호를 할당할 리소스 계정을 선택한 다음 **할당/할당 취소** 를 선택합니다.
4. **전화 번호 유형** 드롭다운에서 사용할 번호 유형을 선택합니다.
5. **할당된 전화 번호** 상자에서 사용할 번호를 검색하고 **추가** 를 선택합니다. 국가 코드(예: +1 250 555 0012)를 포함해야 합니다.
6. **저장** 을 선택합니다.

리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당하려면 PowerShell을 사용해야 합니다.

```powershell
Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting
```
