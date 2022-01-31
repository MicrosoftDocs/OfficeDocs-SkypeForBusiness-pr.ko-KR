---
title: 커넥트 Microsoft Teams 기존 AAD 필수 요소(id)를 일정을 통해 기존 전자 메일 시스템에
author: adjoseph
ms.author: adjoseph
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Google Workspace와 같은 일정을 사용하여 Microsoft Teams(AAD Id)를 기존 전자 메일 시스템에 연결하는 방법에 대해 자세히 알아보기
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b05fb30b6e7e4a3f3725ca8e591cc5caf56fdde
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279246"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>커넥트 Microsoft Teams 기존 AAD 필수 요소(id)를 일정을 통해 기존 전자 메일 시스템에

이 가이드에서는 일정을 통해 기존 Microsoft Teams(AAD)를 기존 전자 메일 시스템에 연결하는 구성 단계를 제공합니다.

Microsoft Teams 필수 요소(AAD ID)는 모임, 채팅Teams 통화 및 공동 작업과 함께 최고의 기능을 제공합니다. Teams 필수 요소(AAD ID)는 기존 전자 메일 Teams 받은 편지함, 모든 일정 이벤트, 기존 전자 메일 주소로 Teams 로그인하는 Teams 같은 통합 환경을 제공할 수 있습니다.

연결되면 예약된 모임에 대한 응답과 사서함에서 공동 작업 및 초대에 대한 응답을 볼 수 Microsoft Teams. Google 작업 영역과 같은 타사 모임 소프트웨어를 사용하여 일정에서 들어오는 모임을 보고 상호 작용할 Teams 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

이 문서의 구성 단계에서는 해당 문서에서 항목을 자동으로 전달하는 프로세스가 Exchange Online. 기본적으로 스팸 방지 아웃바운드 정책에서 자동 전달을 사용하지 않도록 설정됩니다. 이 정책은 기존 사서함 및 일정 시스템에 Teams 필수 요소에 연결하려면 사용하도록 설정해야 합니다.

자동 전달을 사용하도록 설정하려면:

1. 에서 Microsoft 365 Defender 포털로 이동<https://security.microsoft.com/>
2. 왼쪽 탐색 메뉴에서 전자 메일 & **collaborationPolicies** >  >  & 정책 섹션에서 **정책** > **안티 스팸** 으로 이동
3. 스팸 방지 **정책 페이지에서** 목록에서 스팸 방지 아웃바운드 정책( **기본값)** 을 선택합니다.
4. 나타나는 정책 세부 정보 플라이아웃에서 보호 설정 편집을 **선택하여** 자동 적용 규칙을 수정합니다.
5. 전달 **규칙에서** 자동 전달 조건을 On으로 변경 - 전달이 **사용하도록 설정되어** 변경 내용을 저장합니다.

:::image type="content" source="media/essentials-antispam.png" alt-text="On을 사용하여 Microsoft Defender Portal 스팸 방지 아웃바운드 정책 플라이아웃을 보여주는 이미지는 전달 규칙에 따라 전달이 사용하도록 설정되어 있습니다." :::

아웃바운드 스팸 정책 구성에 대한 자세한 내용은 아웃바운드 스팸 [필터링 구성 - Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true).

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>커넥트 Teams 프레미스에서 Exchange Online Exchange 필수 요소

하이브리드 접근 방식을 사용하여 Teams(AAD)가 제공하는 모든 기능을 Microsoft Teams Exchange Online Exchange 수 있습니다.

프레미스 사서함에 대한 일정 액세스가 작동할 수 있도록 설정하기 위해 Teams 일정 액세스에 제공된 지침에 Exchange [-Microsoft Tech](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009) Community

Microsoft Teams 룸 하이브리드 환경에서 Exchange 배포를 Microsoft Teams 룸 Exchange [-Microsoft Teams | Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>커넥트 Teams 타사 전자 메일 시스템에 필수 요소 추가

조직의 사서함을 전자 메일로 전환하지 Microsoft 365 기존 타사 전자 메일 Teams 필수 요소에 연결할 수 있습니다. 이 연결을 사용하면 기존 Teams 모임 초대 및 일정 이벤트를 보는 동안 기존 전자 메일 시스템에서 알림을 받을 수 Microsoft Teams.

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>커넥트 Teams 도메인을 사용하여 타사 전자 메일에 필수 요소(Google 작업 영역 예제)

다음 섹션에서는 Google 작업 영역과 Microsoft Teams 기존 전자 메일 시스템에 연결하는 방법을 보여줍니다. 현재 전자 메일 시스템을 그대로 두고 모든 전자 메일을 일정 Exchange Online 제외한 모든 전자 메일을 필터링하여 이 연결을 수행할 수 있습니다. 이렇게 하면 일정 전자 메일이 미정으로 허용되는 Teams 일정에 자동으로 표시되고 일정이 아닌 전자 메일이 삭제됩니다.

사용자가 미리 알림 Microsoft 365 알림을 받을 수 있도록 모든 전자 메일이 Google 작업 영역으로 Teams 전송됩니다. 사용자의 기본 전자 메일과 같은 사용자 ID를 복제할 수 있습니다. Single Sign-On도 가능하지만 필수는 아닙니다. 사용자는 타사 일정 또는 Teams 모임에 참가할 Teams 있습니다. 다른 Teams 기능은 예상대로 작동합니다.

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="EXO와 Gmail 간의 메일 흐름 다이어그램을 그린 이미지":::

이러한 예제는 커넥트 [PowerShell V2](/powershell/exchange/exchange-online-powershell-v2&preserve-view=true) 모듈의 일부인 Exchange Online [ExchangeOnline](/powershell/module/exchange/connect-exchangeonline?view=exchange-ps&preserve-view=true) PowerShell 명령렛을 사용합니다. 커넥트-ExchangeOnline을 실행하는 경우 [EXO V2](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps&preserve-view=true) 모듈 설치를 사용하여 모듈을 설치하기 위한 권장 지침을 따르는지 확인하세요. 자격 Connect-ExchangeOnline 프롬프트를 표시하는 경우 테넌트 관리자 계정을 사용해야 합니다.

**1단계: 새 테넌트 Microsoft 365 설정**

1. 의 관리 센터로 이동하세요 <https://admin.microsoft.com>.

2. **UpDomains** **설정** > 으로 이동하고 도메인  추가를 선택하여 기존 도메인을 추가합니다. 도메인을 추가하지 않는 경우 조직의 사용자가 전자 메일 주소에 onmicrosoft.com 도메인을 사용합니다. 사용자를 추가하기 전에 도메인을 추가해야 하여 두 번 설정할 수 없습니다.

3. TXT 레코드를 사용하여 확인의 단계를 수행하여 [TXT 레코드를 사용하여 도메인을 확인합니다](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true).

4. 메시지가 표시되면 DNS 구성 **을 허용하지 Microsoft 365 선택합니다**.

5. 메시지가 표시될 때 기존 MX 레코드를 변경하지 않고 그대로 떠날 수 있습니다.

6. 기존 SPF TXT 레코드를 업데이트하여 Microsoft 365.

7. DKIM을 수동으로 설정하려면 다음 Microsoft 365 DKIM에 대해 도메인키 식별 메일([DKIM)을 구성합니다](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true).

8. DKIM을 <https://admin.microsoft.com/AdminPortal/> 사용하도록 Microsoft 365 관리 센터 에 다시 로그인

9. 왼쪽의 탐색 패널에서 **SetupDomains**  >  를 선택합니다.

10. 확인란을 사용하여 현재 도메인 목록에서 기존 비 Microsoft 도메인(예: TomislavK@thephone-company.com)을 선택합니다.

11. 세로 **점이 있는** 단추를 선택하여 메뉴를 니다.

12. 메뉴에서 기본값 **으로 설정을 선택합니다.**

13. **기존 도메인을** 기본값으로 설정하는 것으로 나타나는 창에서 기본값으로 집합을 확인합니다.
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="도메인을 기본값으로 설정하기 위한 확인 대화 상자 이미지":::

    도메인을 추가하는 방법에 대한 자세한 Microsoft 365 도메인 추가에 설명[된](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US) 단계를 Microsoft 365.

**2단계: 사용자 추가 및 Teams 필수 라이선스 할당**

1. 관리 센터로 이동하여 <https://admin.microsoft.com> 개별 사용자를 추가합니다.

2. **UserActive** >  **사용자로 이동** 하고 사용자 **추가를 선택합니다.**

3. 기본 설정 **창** 에서 기본 사용자 정보를 입력한 다음 다음을 **선택합니다**.
    - **이름:** 이름과 성, 표시 이름 및 사용자 이름을 입력합니다.
    - **도메인:** 사용자의 계정에 대한 도메인을 선택하세요. 예를 들어 사용자의 사용자 이름이 Jakob이고 도메인이 contoso.com 경우 사용자 이름을 사용하여 로그인 jakob@contoso.com.
    - **암호 설정:** 자동 생성 암호를 사용하거나 사용자에 대한 강력한 암호를 만들지 선택하세요.  사용자가 추가될 때 전자 메일에서 암호를 보낼지 여부를 결정합니다.

4. 제품 라이선스 **할당 창** 에서 사용자에 대한 위치 및 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없는 경우 사용자를 추가하고 더 많은 라이선스를 구입할 수 있습니다. 다음을 선택합니다.

5. 선택적 **설정 창에서** 이 사용자를 관리자  로 설정하려면 역할을 확장합니다. 프로필 **정보를 확장** 하여 사용자에 대한 추가 정보를 추가합니다.

6. 다음 **을** 선택하고 새 사용자의 설정을 검토하고, 필요한 경우 다른 변경을 한 다음 추가 **완료를 선택한** 다음 닫습니다.

동시에 여러 사용자를 추가하려면 사용자 추가의 권장 단계를 수행하고 라이선스 [할당 - Microsoft 365 관리자 | Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

**3단계: Google 작업 영역 구성**

***전자 메일 이중 배달을 Microsoft 365 및 스트립 첨부 파일을 구성합니다.***

1. 이중 배달을 설정하는 Google의 단계를 따릅니다. <https://support.google.com/a/answer/9228551?hl=en>

2. 경로 추가 Office 365

    - )에서 Google 관리 콘솔로 이동 <https://admin.google.com>
    - Gmail > Google 작업 영역 > Gmail > 로 이동하세요.
    - 경로 이름을 입력합니다. (예: Microsoft 365)
    - 'Single host'를 선택하고 도메인에 대해 지정된 MX 레코드를 Microsoft 365(예: ContosoLandscaping2-m365master-com.mail.protection.outlook.com)

    **메일이 프레미스/Exchange 보낼 때 ATTR35 응답 코드를 해결하는 스마트 호스트 Exchange Online.**
    - 'Single host'를 선택하고 스마트 호스트로 테넌트의 초기 도메인에 대한 MX 레코드를 입력합니다. 초기 도메인은 형식에 GUID.onmicrosoft.com. GUID는 서비스 등록의 일부로 모든 조직에 제공되는 고유한 값입니다. GUID는 고유 식별자가 필요한 모든 컴퓨터 및 네트워크에서 사용할 수 있는 128비트 정수(16 바이트)입니다.
    - 명령줄: nslookup -type MX GUID.onmicrosoft.com MX 레코드를 확인(예: contosolandscaping2.mail.protection.outlook.com)
    - 포트 **선택:25**
    - 권장 옵션 진행

3. 경로 구성을 Office 365

    - 에서 **Google 관리 콘솔 열** 기 <https://admin.google.com>

    - **AppsGoogle** >  **작업 영역** > **GmailRouting** > **으로 이동**

    - 라우팅 **탭에서** 구성 **을 선택합니다.**

    - 규칙 **의 이름을** 입력합니다. (예: Gmail에서 Office 365)

    - 전자 **메일 메시지에 영향을** 줄 수 있는 경우 **인** 바운드 및 내부 수신을  **모두 선택합니다.**

    - 위의 **메시지 형식** 의 경우 메시지 수정 **을 선택합니다.**

    - 또한 **배달에서** 받는 사람 **추가를 선택한** 다음 추가를 선택하여 보조 메일 **경로를 추가합니다.**

    - 받는 **사람 아래** 에서 아래쪽 화살표 ""를 선택하고 고급을 **선택합니다.**

    - 경로 **변경을 선택합니다.**

    - 목록에서 앞에서 만든 보조 메일 경로를 선택합니다.

    - 첨부 **파일에서** 메시지에서 **첨부 파일 제거를 선택합니다.**

    - 아래로 스크롤하고 저장을 **선택합니다**.

***Google 작업 영역의 하위 Microsoft 365.***

  다음으로 사서함을 하위 Microsoft 365 전달 규칙을 만들 것입니다. Google Workspace에서 사용할 하위 Microsoft 365(예: g.contosolandscaping2.m365master.com)

1. **Google 관리 콘솔** 에서 시작(admin.google.com)

2. **AccountDomainsManage** >  >  **도메인으로 이동**

3. 도메인 **추가 선택**

4. 선택한 도메인 이름 입력

5. 사용자 **별칭 도메인 선택**

6. 도메인 **추가 & 확인을 선택합니다.**

7. 확인이 완료될 때까지 기다렸다가 페이지를 새로 고침합니다.

8. Gmail **활성화 선택**

9. **MX 레코드 설정 건너뛰기를 선택한** 다음 **다음을 선택합니다.**

10. 다른 **서버 대화** 상자로 메일 라우팅 대화 상자에서(예: aspmx.l.google.com) 다른 메일 서버를 사용하는 서버를 선택합니다 **.**

***스팸 필터를 Microsoft 365 전자 메일 허용***

1. Google 작업 Microsoft 365 사용자에게 전자 메일을 보내서 테넌트에서 적절한 헤더를 찾을 수 있습니다.

2. 메시지를 열고 원본 **표시를 선택합니다.**

3. 사용자 테넌트에서 오는 메일을 고유하게 식별하는 전자 메일 Microsoft 365 선택하세요. (예를 들어 X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. 에서 **Google 관리 콘솔로** 이동 <https://admin.google.com>

5. **AppsGoogle** >  **작업 영역** > **GmailCompliance** > **로 이동**

6. 콘텐츠 준수 **로 이동** 하고 구성 **을 선택합니다.**

7. 설정을 이름을 지정합니다. 예를 들어 허용 목록 Microsoft 365 수 있습니다.

8. 체크 **인바운드에 영향을** 주는 전자 메일 메시지 아래

9. 각 **메시지에서** 검색할 콘텐츠를 설명하는 식 추가에서 다음 중 어느 것이 메시지와 일치하는지 **선택합니다.**

10. 식 **에서** xi **추가를** 선택합니다. 추가 **설정에서** 고급 콘텐츠 **일치를 선택하세요.**

11. 위치 **아래** 에서 **전체 헤더 선택**

12. 일치 **유형 아래** 에서 전체 **텍스트를 선택**

13. 콘텐츠 Microsoft 365 아래에서 사용자 테넌트에서 오는 전자 메일을 고유하게 식별하는 전자 메일 헤더를 입력합니다(예: X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

14. 저장 **선택**

15. 위의 **식** 이 일치하는 경우 다음 필드를 > 수정하고 스팸 아래에서 이 **메시지에 대한** 무시 스팸  필터를 **검사합니다**.

16. 저장 **선택**

**4단계: Microsoft 365 설정 구성**

*전자 메일에서 Gmail로 Microsoft 365 커넥터를 구성합니다.*

1. **Microsoft 관리 센터로** 이동<https://admin.microsoft.com/AdminPortal>

2. 왼쪽 **탐색 메뉴** 에서 모두 표시를 선택합니다.

3. 관리 **센터에서** 새 **Exchange** 관리 센터를 Exchange 관리 센터를 를 선택합니다.

4. 관리 **Exchange** 왼쪽 탐색 메뉴에서 **Mail flowConnectors** > 를 **선택하고** 오버플로 메뉴(...)를 열고 커넥터 추가를 선택합니다.

5. 새 **커넥터 창** 의 연결 아래에서 Office 365 

6. 연결 **에서** 조직의 전자 메일 서버를 선택한 다음을 **선택합니다.**

7. 새 커넥터 **의** 이름(예: Gmail)을 입력하고 다음을 **계속합니다**.

8. 커넥터 **사용 섹션** 에서 메시지를 이 커넥터로  리디렉션하는 전송 규칙이 설정된 경우만 선택하고 다음을 **선택합니다**.

9. 라우팅 섹션에서 적절한 스마트 메일 호스트(예: aspmx.l.google.com)를 입력하고 , 를 선택한 **+** 다음 다음을 **계속합니다**.

10. 보안 제한 **섹션** 에서 다음을 선택하여 기본 설정을 수 **락합니다.**

11. 유효성 **검사 전자 메일 섹션에서** Gmail 시스템의 유효한 전자 메일 주소(예: johannal@g.contosolandscaping2.m365master.com)를 입력하고 더하기 기호( **+**)를 선택한 다음 유효성 검사(유효성 검사)를 **선택합니다.**

12. 유효성 검사가 완료될 때까지 기다렸다가 성공한 경우 다음을 누르기

13. 커넥터 **검토에서** 구성이 올바른지 확인하고 커넥터 만들기를 누르기

14. 커넥터가 만든 알림이 표시되면 완료를 **누를 수 있습니다.**

*사서함에서 gmail로 Microsoft 365 메일 전달*

1. Microsoft 365 관리 **센터** 를 사용하여 각 사서함을 업데이트하거나 **PowerShell** 스크립트(예: 다음)를 사용할 수 있습니다.

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    
    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    } 
    ```

    **문제 해결 커넥트-ExchangeOnline:**

    커넥트-ExchangeOnline을 실행하는 경우 오류가 발생하나요? 조직의 자동 전자 메일 전달 규칙의 결과일 수 있습니다. 기본적으로 자동 전달을 사용할 수 없습니다. Google 작업 Teams 필수 요소에 연결하려면 규칙을 사용하도록 설정해야 합니다.  

    다음 스크립트를 입력합니다.

   ```powershell
    Set-ExecutionPolicy Unrestricted 
     ```

    그 후 다음 명령을 실행합니다.

    ```powershell
    Enable-OrganizationCustomization 
    Get-HostOutboundSpamFilterPolicy | set-HostedOutboundSpamFilterPolicy -AutoForwardingMode On
    ```

*일정 Exchange Online 직접 구성*

1. 이 설정을 구성하면 사용자가 일정에서 초대와 상호 작용할 Teams 일정에 표시될 수 있도록 일정 초대를 자동으로 Outlook Web App.

2. 다음 스크립트를 사용하여 전송 규칙을 만들 수 있습니다.

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems
    
    ```

*사서함에 웹용 Outlook 사용 안 함*

1. 사서함에 대한 웹용 Outlook [](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app) 사용 또는 Exchange Online 웹용 Outlook 지침을 따릅니다.

2. 관리 센터 또는 powerShell 웹용 Outlook 사용하여 Exchange  **비활성화할 수 있습니다**. 다음 PowerShell 예제를 사용하여 모든 사서함에 대한 웹용 Outlook 사용할 수 있습니다.

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

**5단계: Exchange Online 도메인 구성**

이 단계에서는 최종 해결을 위해 타사 시스템에 전자 메일이 전송되도록 합니다.

1. **Microsoft 관리 센터로** 이동<https://admin.microsoft.com/AdminPortal>

2. 왼쪽 탐색에서 모두 **표시를 선택합니다.**

3. 관리 **센터에서** 새 **탭에서** Exchange Exchange 관리 센터를 을 선택합니다.

4. Exchange 관리 **센터** 에서 왼쪽 탐색 메뉴에서  메일 흐름을 선택한 다음 수락된 도메인 **을 선택합니다.**

5. 타사 시스템에서 구성된 도메인 이름을 탭합니다(예: contosoLandscaping2.m365master.com)

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="메일 흐름에 Exchange 관리 센터 설정을 보여주는 이미지입니다.":::

6. 내부 **릴레이를** 선택한 다음 저장 **을 클릭합니다.**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="내부 릴레이 설정을 저장하는 행위를 보여주는 이미지입니다.":::

**6단계: 일정을 제외한 모든 인바운드 메일을 Exchange Online 규칙 만들기**

1. 관리 센터 또는 **PowerShell에서 Exchange 구성할 수 있습니다**. 다음 **PowerShell** 예제를 사용하여 규칙을 만들 수 있습니다.

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true 
    
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>커넥트 Teams 도메인을 사용하지 않는 타사 전자 메일에 필수 요소(Gmail 예제)

G Suite Add On에 대한 기본 Teams 기본 Teams Gmail 계정을 연결하여 Google 작업 영역에서 직접 모임을 예약하고 Teams [수 있습니다](https://support.microsoft.com/en-us/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60). 이렇게 하면 화면 공유, 모임 채팅, 디지털 화이트보드 등 비디오 및 오디오 회의를 예약할 수 있습니다.

Gmail에서 전자 메일을 끌어오도록 Exchange Online 메일이 Gmail에 Microsoft 365 Teams 수 있도록 구성합니다. 이 연결을 수행하려면 보안 기본값을 사용하지 않도록 설정해야 할 수 있습니다. 따라서 강력한 고유 암호를 반드시 사용할 수 있습니다. 이 시나리오에는 사용자 지정 도메인이 필요하지 않지만 Gmail에서 사용하기 위해 Microsoft 365 구성할 수 있습니다.

:::image type="content" source="media/essentials-gmail.png" alt-text="필수 요소와 Gmail 간에 메일 흐름을 Teams 이미지":::

**Gmail 계정이 설정되어 있는지 확인**

기존 계정이 이미 있는 경우 다음 단계를 진행할 수 있습니다. 그렇지 않은 경우 새 [Google](https://accounts.google.com/SignUp?hl=en) 계정 만들기를 방문하여 새 Gmail 계정을 설정하세요.

**2. 테넌트 Microsoft 365 설정**

*사용자 Teams AAD 구성*

1. Add 사용자[에](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) 대한 지침을 따르고 라이선스를 할당하여 여러 사용자를 추가합니다.

*ID 보호 구성*

1. 활성 상태인 경우 보안 기본값을 사용하지 않도록 설정합니다.

2. 사용자에 대한 다단계 인증 구성

3. 조건부 액세스를 사용하는 경우 사서함에 대한 POP 액세스에 대한 예외를 만들어야 합니다.

*Microsoft 365 관리 센터에 도메인 추가(선택 사항)*

1. 탐색에서 도메인 설정 > 선택한 다음 도메인 추가를 선택합니다.

2. 적절한 필드에 도메인 이름을 입력합니다.

3. TXT 레코드를 사용하여 도메인을 확인하려면 화면의 지침에 따라

4. 메시지가 표시되면 Microsoft에서 DNS를 구성하도록 허용

5. MX 레코드 경로 확인을 위해 지침을 Microsoft 365

6. SPF TXT 레코드를 포함하도록 Microsoft 365

7. DKIM TXT 레코드를 구성하기 위한 지침을 Microsoft 365

8. 관리 센터에 로그아웃하고 다시 로그인하여 DKIM이 사용하도록 설정되어 있는지 확인합니다.

**3. Gmail 구성**

1. Gmail을 구성하여 메일 Exchange Online 시스템으로 끌어오기

2. 일정 Teams 추가 기능 구성

3. Gmail에서 비즈니스 도메인 사용(선택 사항)
