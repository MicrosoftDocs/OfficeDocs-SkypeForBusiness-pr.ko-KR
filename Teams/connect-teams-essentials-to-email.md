---
title: 일정이 있는 기존 전자 메일 시스템에 대한 커넥트 Microsoft Teams Essentials(AAD ID)
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
description: Google Workspace와 같은 일정을 사용하여 기존 전자 메일 시스템에 Microsoft Teams Essentials(AAD ID)를 연결하는 방법을 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dcea261be727c01382d55c4a2861541291fcb343
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823589"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>일정이 있는 기존 전자 메일 시스템에 대한 커넥트 Microsoft Teams Essentials(AAD ID)

이 가이드에서는 일정이 있는 기존 전자 메일 시스템에 Microsoft Teams Essentials(AAD ID)를 연결하기 위한 구성 단계를 제공합니다.

Microsoft Teams Essentials(AAD ID)는 모임, 채팅, 통화 및 공동 작업과 함께 최고의 Teams 제공합니다. AAD ID(Teams Essentials)는 기존 전자 메일 시스템에 연결하여 기존 전자 메일 받은 편지함에 모든 Teams 알림, Teams 모든 일정 이벤트 및 기존 전자 메일 주소로 Teams 로그인하는 기능과 같은 통합된 환경을 제공할 수 있습니다.

연결되면 사서함 및 Microsoft Teams 공동 작업을 위해 예약된 모임 및 초대에 대한 응답을 볼 수 있습니다. Google Workspace와 같은 Teams 및 타사 모임 소프트웨어를 사용하여 일정에서 들어오는 모임을 보고 상호 작용할 수도 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

이 문서의 구성 단계에는 Exchange Online 항목을 자동으로 전달하는 프로세스가 포함됩니다. 기본적으로 자동 전달은 스팸 방지 아웃바운드 정책에 의해 비활성화됩니다. Teams Essentials를 기존 사서함 및 일정 시스템에 연결하려면 이 정책을 사용하도록 설정해야 합니다.

자동 전달을 사용하도록 설정하려면 다음을 수행합니다.

1. 에서 Microsoft 365 Defender 포털로 이동합니다.<https://security.microsoft.com/>
2. 왼쪽 탐색 메뉴에서 **정책 섹션에서 메일 & 협업** > **정책 & 규칙** > **위협 정책** > **스팸 방지** 로 이동합니다.
3. **스팸 방지 정책** 페이지의 목록에서 **스팸 방지 아웃바운드 정책(기본값)** 을 선택합니다.
4. 표시되는 정책 세부 정보 플라이아웃에서 **보호 설정 편집** 을 선택하여 자동 전달 규칙을 수정합니다.
5. **전달 규칙에** 따라 자동 전달 조건을 **켜기 - 전달이 사용하도록 설정됨으로** 변경하고 변경 내용을 저장합니다.

:::image type="content" source="media/essentials-antispam.png" alt-text="Microsoft Defender Portal 스팸 방지 아웃바운드 정책 플라이아웃을 켜고 전달 규칙에 따라 전달이 사용하도록 설정된 상태를 보여 주는 이미지입니다." :::

아웃바운드 스팸 정책을 구성하는 방법에 대한 자세한 내용은 [아웃바운드 스팸 필터링 구성 - Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true).

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>Exchange 온-프레미스로 Exchange Online 커넥트 Teams Essentials

하이브리드 접근 방식을 사용하여 Exchange 온-프레미스와 Microsoft Teams Exchange Online 간의 연결을 구성함으로써 AAD(Teams Essentials)가 제공하는 모든 것을 즐길 수 있습니다.

온-프레미스 사서함에 대해 일정 액세스가 작동하도록 하려면 Exchange[온-프레미스 사서함에 대한 Teams 일정 액세스 구성에 제공된 지침을 따릅니다. Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)

Exchange 온-프레미스를 사용하여 하이브리드 환경에서 Microsoft Teams 룸 배포하려면 온[-프레미스에서 Exchange Microsoft Teams 룸 배포 - Microsoft Teams | Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>일정을 사용하여 타사 전자 메일 시스템에 Essentials 커넥트 Teams

조직의 사서함을 Microsoft 365 전환하지 않으려는 경우 Teams Essentials를 기존 타사 전자 메일 및 일정 시스템에 연결할 수 있습니다. 이 연결을 사용하면 Microsoft Teams 기존 모임 초대 및 일정 이벤트를 보면서 기존 전자 메일 시스템에서 Teams 알림을 받을 수 있습니다.

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>베니티 도메인을 사용하여 타사 전자 메일에 Essentials 커넥트 Teams(Google Workspace 예제)

다음 섹션에서는 Google Workspace와 같은 일정을 사용하여 기존 전자 메일 시스템에 Microsoft Teams 연결하는 방법을 보여줍니다. 현재 전자 메일 시스템을 그대로 유지하고, 모든 전자 메일을 Exchange Online 전달하고, 일정 유형의 전자 메일을 제외한 모든 전자 메일을 필터링하여 이 연결을 수행합니다. 이렇게 하면 일정 전자 메일이 임시 및 비 일정 형식 전자 메일로 허용되는 Teams 일정에 자동으로 표시됩니다.

사용자가 Teams 미리 알림 및 알림을 받을 수 있도록 Microsoft 365 생성된 모든 전자 메일이 Google 작업 영역으로 전달됩니다. 사용자의 기본 전자 메일과 같은 사용자 ID를 복제할 수 있습니다. Single Sign-On도 가능하지만 필수는 아닙니다. 사용자는 타사 일정 또는 Teams 일정에서 Teams 모임에 참가할 수 있어야 합니다. 또 다른 Teams 기능은 예상대로 작동합니다.

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="EXO와 Gmail 간의 메일 흐름 다이어그램을 보여 주는 이미지":::

이러한 예제는 [Exchange Online](/powershell/module/exchange/connect-exchangeonline) [PowerShell V2 모듈의 일부인 커넥트-ExchangeOnline PowerShell](/powershell/exchange/exchange-online-powershell-v2?preserve-view=true&view=exchange-ps) commandlet을 사용합니다. 커넥트-ExchangeOnline을 실행할 때 오류가 발생하는 경우 [EXO V2 모듈 설치](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-EXO-v2-module)를 사용하여 모듈을 설치하기 위한 권장 지침을 따랐는지 확인합니다. Connect-ExchangeOnline 자격 증명을 묻는 메시지가 표시되면 테넌트 관리자 계정을 사용해야 합니다.

#### <a name="step-one-set-up-a-new-microsoft-365-tenant-domain"></a>1단계: 새 Microsoft 365 테넌트 도메인 설정

1. 에서 관리 센터로 <https://admin.microsoft.com>이동합니다.

2. **도메인** **설정** > 으로 이동하고 **도메인 추가** 를 선택하여 기존 도메인을 추가합니다. 도메인을 추가하지 않으면 조직의 사용자는 사용자가 할 때까지 전자 메일 주소에 onmicrosoft.com 도메인을 사용합니다. 사용자를 추가하기 전에 도메인을 추가해야 하므로 두 번 설정할 필요가 없습니다.

3. TXT 레코드로 확인의 단계에 따라 [TXT 레코드가 있는 도메인을 확인](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true)합니다.

4. 메시지가 표시되면 **Microsoft 365 DNS 구성 허용 안 함을** 선택합니다.

5. 메시지가 표시되면 기존 MX 레코드를 변경하지 않고 그대로 둡니다.

6. Microsoft 365 포함하도록 기존 SPF TXT 레코드를 업데이트합니다.

7. DKIM을 수동으로 설정하려면 다음 단계에 따라 Microsoft 365 DomainKeys 식별 메일([DKIM](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true))을 구성합니다.

8. DKIM을 사용하도록 설정하려면 Microsoft 365 관리 센터 <https://admin.microsoft.com/AdminPortal/> 다시 로그인합니다.

9. 왼쪽의 탐색 패널에서 **도메인 설정** >  선택

10. 확인란을 사용하여 현재 도메인 목록에서 기존 비 Microsoft 도메인(예: TomislavK@thephone-company.com)을 선택합니다.

11. 세로 점이 **세** 개 있는 단추를 선택하여 메뉴를 엽니다.

12. 메뉴에서 **기본값으로 설정** 선택

13. 기존 도메인을 **기본값으로 설정하는** 것으로 표시되는 창에서 기본값으로 설정 확인합니다.
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="도메인을 기본값으로 설정하기 위한 확인 대화 상자 이미지":::

    Microsoft 365 도메인을 추가하는 방법에 대한 자세한 지침은 Microsoft 365 [도메인 추가](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)에 설명된 단계를 따르세요.

#### <a name="step-two-add-users-and-assign-teams-essentials-licenses"></a>2단계: 사용자 추가 및 Teams Essentials 라이선스 할당

1. 관리 센터로 <https://admin.microsoft.com> 이동하여 개별 사용자 추가

2. **사용자** > **활성 사용자** 로 이동하고 **사용자 추가를** 선택합니다.

3. **기본 설정** 창에서 기본 사용자 정보를 입력한 다음 다음 **을 선택합니다.**
    - **이름:** 이름과 성, 표시 이름 및 사용자 이름을 입력합니다.
    - **도메인:** 사용자 계정에 대한 도메인을 선택합니다. 예를 들어 사용자의 사용자 이름이 Jakob이고 도메인이 contoso.com 경우 jakob@contoso.com 사용하여 로그인합니다.
    - **암호 설정:** 자동 생성된 암호를 사용하거나 사용자에 대한 강력한 암호를 만들도록 선택합니다.  사용자가 추가되면 전자 메일에 암호를 보낼지 여부를 결정합니다.

4. **제품 라이선스 할당** 창에서 사용자의 위치와 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없는 경우에도 사용자를 추가하고 더 많은 라이선스를 구입할 수 있습니다. 다음을 선택합니다.

5. 이 사용자를 관리자로 만들려면 **선택적 설정** 창에서 **역할을** 확장합니다. **프로필 정보를** 확장하여 사용자에 대한 추가 정보를 추가합니다.

6. **다음** 을 선택하고, 새 사용자의 설정을 검토하고, 필요한 경우 다른 변경 내용을 적용한 다음, **추가 완료** 를 선택한 다음, 닫습니다.

동시에 여러 사용자를 추가하려면 [사용자 추가 및 라이선스 할당의 권장 단계를 수행합니다. Microsoft 365 관리자 | Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

#### <a name="step-three-configure-google-workspace"></a>3단계: Google 작업 영역 구성

***Microsoft 365 및 제거 첨부 파일에 대한 전자 메일 이중 배달을 구성합니다.***

1. 이중 배달을 설정하기 위한 Google의 단계를 따릅니다. <https://support.google.com/a/answer/9228551?hl=en>

2. Office 365 대한 경로 추가

    - 에서 Google 관리 콘솔<https://admin.google.com>로 이동
    - Google Workspace > Gmail > 호스트를 > 앱으로 이동합니다.
    - 경로 이름을 입력합니다. (예: Microsoft 365)
    - '단일 호스트'를 선택하고 Microsoft 365 도메인에 지정된 MX 레코드를 입력합니다(예: ContosoLandscaping2-m365master-com.mail.protection.outlook.com).

    **온-프레미스/Exchange Online Exchange 메일을 보낼 때 ATTR35 응답 코드를 확인하는 스마트 호스트 방법:**
    - '단일 호스트'를 선택하고 테넌트의 초기 도메인에 대한 MX 레코드를 스마트 호스트로 입력합니다. 초기 도메인은 GUID.onmicrosoft.com 형식입니다. GUID는 서비스 등록의 일부로 모든 조직에 제공되는 고유한 값입니다. GUID는 고유 식별자가 필요한 모든 컴퓨터 및 네트워크에서 사용할 수 있는 128비트 정수(16바이트)입니다.
    - 명령줄: nslookup -type MX GUID.onmicrosoft.com 사용하여 MX 레코드를 확인할 수 있습니다(예: contosolandscaping2.mail.protection.outlook.com).
    - **포트 선택:25**
    - 권장 옵션 진행

3. Office 365 경로 구성

    - 에서 **Google 관리 콘솔** 열기<https://admin.google.com>

    - **앱** > **Google Workspace** > **Gmail** > **라우팅** 으로 이동

    - **라우팅** 탭에서 **구성** 을 선택합니다.

    - 규칙 **의 이름을** 입력합니다. (예: Gmail to Office 365)

    - **전자 메일 메시지가 영향을 주려면** **인바운드** 및 **내부 수신을** 모두 선택합니다.

    - **위의 메시지 유형에서 메시지** **수정** 을 선택합니다.

    - **배달** 대상에서 **받는 사람 추가를** 선택한 다음 **추가를 선택하여 보조 메일 경로를 추가합니다.**

    - **받는 사람** 아래에서 아래쪽 화살표 ""를 선택하고 고급을 선택합니다 **.**

    - **경로 변경을 선택합니다.**

    - 목록에서 이전에 만든 보조 메일 경로를 선택합니다.

    - **첨부 파일** 아래에서 **메시지에서 첨부 파일 제거** 를 선택합니다.

    - 아래로 스크롤하여 **저장** 을 선택합니다.

***Google 작업 영역에 하위 도메인을 추가하여 Microsoft 365 전자 메일을 받습니다.***

  다음으로 Microsoft 365 사서함에 대한 전달 규칙을 하위 도메인에 만듭니다. Google Workspace에서 Microsoft 365 전자 메일을 받는 데 사용할 하위 도메인 선택(예: g.contosolandscaping2.m365master.com)

1. **Google 관리 콘솔** 에서 시작(admin.google.com)

2. **계정** > **도메인 관리** > **도메인으로** 이동

3. **도메인 추가** 선택

4. 선택한 도메인 이름을 입력합니다.

5. **사용자 별칭 도메인** 선택

6. **도메인 추가 & 확인 시작** 선택

7. 확인이 완료되기를 기다렸다가 페이지를 새로 고칩니다.

8. **Gmail 활성화** 선택

9. **MX 레코드 설정 건너뛰기** 선택 및 **다음** 선택

10. **다른 서버로 메일 라우팅** 대화 상자에서 메일을 라우팅할 서버(예: aspmx.l.google.com)를 적어 두고 **다른 메일 서버를 사용하도록** 선택합니다.

***Microsoft 365 이메일이 스팸 필터를 무시하도록 허용***

1. Google 작업 영역의 사용자에게 전자 메일을 보내 Microsoft 365 테넌트에서 적절한 헤더를 찾습니다.

2. 메시지를 열고 **원본 표시** 를 선택합니다.

3. Microsoft 365 테넌트에서 들어오는 메일을 고유하게 식별하는 전자 메일 헤더를 선택합니다. (예: X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. **에서 Google 관리 콘솔** 로 이동<https://admin.google.com>

5. **앱** > **Google Workspace** > **Gmail** > **준수** 로 이동

6. **콘텐츠 준수** 로 이동하고 **구성** 을 선택합니다.

7. 설정에 이름을 지정합니다. 예를 들어 허용 목록은 전자 메일을 Microsoft 365.

8. 인바운드 확인 **에 영향을 줄 전자 메일 메시지**

9. **각 메시지에서 검색할 콘텐츠를 설명하는 식 추가 아래에서** **다음 중 하나라도 메시지와 일치하는지** 선택합니다.

10. **식** 에서 xi **추가** 를 선택합니다. **추가 설정** 에서 **고급 콘텐츠 일치** 를 선택합니다.

11. **위치** 아래에서 **전체 머리글** 선택

12. **일치 유형** 에서 **전체 텍스트** 선택

13. 콘텐츠 아래에 Microsoft 365 테넌트에서 들어오는 전자 메일을 고유하게 식별하는 전자 메일 헤더를 입력합니다(예: X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

14. **저장** 선택

15. **위의 식이 일치하는 경우 메시지** **수정** > 다음 필드를 수행하고 **스팸** 아래에서 **이 메시지에 대한 스팸 필터 무시를** 확인합니다.

16. **저장** 선택

#### <a name="step-four-configure-microsoft-365-settings-for-the-integration"></a>4단계: 통합에 대한 Microsoft 365 설정 구성

*Microsoft 365 Gmail로 메일을 라우팅하도록 커넥터를 구성합니다.*

1. **에서 Microsoft 관리 센터로** 이동합니다.<https://admin.microsoft.com/AdminPortal>

2. 왼쪽 탐색 메뉴에서 **모두 표시** 를 선택합니다.

3. **관리 센터에서 Exchange** 선택하여 새 탭에서  Exchange 관리 센터를 엽니다.

4. **Exchange 관리 센터의** 왼쪽 탐색 메뉴에서 **메일 흐름** > **커넥터** 를 선택하고 오버플로 메뉴(...)를 열고 커넥터 추가를 선택합니다.

5. 새 커넥터 창의 **연결에서** **Office 365**

6. **연결** 에서 조직의 전자 메일 서버를 선택한 다음 **, 다음** 을 선택합니다.

7. 새 커넥터의 **이름**(예: Gmail로)을 입력하고 **다음** 을 계속합니다.

8. **커넥터 사용** 섹션에서 **메시지를 이 커넥터로 리디렉션하는 전송 규칙이 설정된 경우에만** 선택하고 **다음** 을 선택합니다.

9. 라우팅 섹션에서 적절한 스마트 메일 호스트(예: aspmx.l.google.com)를 입력하고, 선택하고 **+**, 다음을 계속 **합니다**.

10. **보안 제한** 섹션에서 **다음** 을 선택하여 기본 설정을 적용합니다.

11. **유효성 검사 전자 메일 섹션에서** Gmail 시스템의 유효한 전자 메일 주소(예: johannal@g.contosolandscaping2.m365master.com)를 입력하고 **더하기 기호(+)** 를 선택한 다음 **유효성 검사를** 선택합니다.

12. 유효성 검사가 완료되고 성공하면 다음 키를 누릅니다.

13. **검토 커넥터** 에서 구성이 올바른지 확인하고 커넥터 만들기를 누릅니다.

14. 커넥터에서 만든 알림이 표시되면 완료 키를 누릅니다 **.**

*Microsoft 365 사서함에서 Gmail로 메일 전달:*

1. **Microsoft 365 관리 센터를** 사용하여 각 사서함을 업데이트하거나 다음과 같은 **PowerShell** 스크립트를 사용할 수 있습니다.

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {

    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    }
    ```

    **커넥트-ExchangeOnline 문제 해결:**

    커넥트-ExchangeOnline을 실행할 때 오류가 발생합니까? 조직의 자동 전자 메일 전달 규칙의 결과일 수 있습니다. 기본적으로 자동 전달은 사용하지 않도록 설정됩니다. Teams Essentials를 Google Workspace에 연결하려면 규칙을 사용하도록 설정해야 합니다.

    다음 스크립트를 입력합니다.

   ```powershell
    Set-ExecutionPolicy Unrestricted
     ```

    그런 다음 다음 명령을 실행합니다.

    ```powershell
    Enable-OrganizationCustomization
    Get-HostOutboundSpamFilterPolicy | set-HostedOutboundSpamFilterPolicy -AutoForwardingMode On
    ```

*일정 전송 규칙으로 직접 Exchange Online 구성:*

1. 이 설정을 구성하면 사용자가 Outlook Web App 초대와 상호 작용할 필요 없이 일정 초대가 Teams 일정에 표시되도록 자동으로 수락됩니다.

2. 다음 스크립트를 사용하여 전송 규칙을 만들 수 있습니다.

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems

    ```

*사서함에 대한 웹용 Outlook 사용하지 않도록 설정합니다.*

1. [Exchange Online 사서함에 대한 웹용 Outlook 사용 또는 사용 안 함](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)의 지침에 따라 사서함에 대한 웹용 Outlook 사용하지 않도록 설정합니다.

2. Exchange 관리 Center 또는 **PowerShell** 을 사용하여 **웹용 Outlook** 사용하지 않도록 설정할 수 있습니다. 다음 PowerShell 예제를 사용하여 모든 사서함에 웹용 Outlook 사용하지 않도록 설정할 수 있습니다.

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

#### <a name="step-five-configure-exchange-online-domain-for-internal-relay"></a>5단계: 내부 릴레이에 대한 Exchange Online 도메인 구성

이 단계에서는 최종 해결을 위해 전자 메일을 타사 시스템으로 보냅니다.

1. **에서 Microsoft 관리 센터로** 이동합니다.<https://admin.microsoft.com/AdminPortal>

2. 왼쪽 탐색에서 **모두 표시** 를 선택합니다.

3. **관리 센터에서** **Exchange** 선택하여 새 탭에서 Exchange 관리 센터를 엽니다.

4. **Exchange 관리 센터의** 왼쪽 탐색 메뉴에서 **메일 흐름을** 선택한 다음, **허용 도메인을 선택합니다.**

5. 타사 시스템에 구성된 도메인 이름을 탭합니다(예: contosoLandscaping2.m365master.com).

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="메일 흐름에 대한 Exchange 관리 센터 설정을 보여 주는 이미지입니다.":::

6. **내부 릴레이** 를 선택한 다음 **저장** 을 클릭합니다.

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="내부 릴레이 설정을 저장하는 동작을 보여 주는 이미지입니다.":::

#### <a name="step-six-create-a-rule-to-delete-all-inbound-mail-to-exchange-online-except-for-calendaring"></a>6단계: 일정 지정을 제외한 Exchange Online 모든 인바운드 메일을 삭제하는 규칙 만들기

1. **Exchange 관리 Center** 또는 **PowerShell** 에서 이 규칙을 구성할 수 있습니다. 다음 **PowerShell** 예제를 사용하여 규칙을 만들 수 있습니다.

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>베니티 도메인을 사용하지 않는 타사 전자 메일에 Essentials 커넥트 Teams(Gmail 예제)

소비자 Gmail 계정을 Teams Essentials에 연결하여 Teams [G Suite 추가](https://support.microsoft.com/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60) 기능에 대한 기본 의존도를 사용하여 Google Workspace에서 직접 Teams 모임을 예약하고 참가할 수 있습니다. 이렇게 하면 화면 공유, 모임 채팅, 디지털 화이트보드 등을 사용하여 비디오 및 오디오 회의를 예약할 수 있습니다.

Microsoft 365 생성된 메일이 Gmail에 성공적으로 도착할 Teams 있도록 Exchange Online 전자 메일을 가져오도록 Gmail을 구성합니다. 이 연결을 수행하려면 보안 기본값을 사용하지 않도록 설정해야 할 수 있으므로 강력한 고유 암호를 사용해야 합니다. 이 시나리오에서는 사용자 지정 도메인이 필요하지 않지만 Gmail에서 사용할 수 있도록 Microsoft 365 구성할 수 있습니다.

:::image type="content" source="media/essentials-gmail.png" alt-text="Teams Essentials와 Gmail 간의 메일 흐름을 구분하는 이미지":::

#### <a name="1-ensure-that-you-have-a-gmail-account-set-up"></a>1. Gmail 계정이 설정되어 있는지 확인

기존 계정이 이미 있는 경우 다음 단계로 진행할 수 있습니다. 그렇지 않은 경우 [새 Google 계정 만들기](https://accounts.google.com/SignUp?hl=en) 를 방문하여 새 Gmail 계정을 설정합니다.

#### <a name="2-set-up-your-microsoft-365-tenant"></a>2. Microsoft 365 테넌트 설정

*Teams AAD 사용자 구성:*

1. 사용자 추가의 지침에 따라[라이선스를 할당](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) 하여 여러 사용자 추가

*ID 보호 구성:*

1. 활성 상태인 경우 보안 기본값을 사용하지 않도록 설정합니다.

2. 사용자에 대한 다단계 인증 구성

3. 조건부 액세스를 사용하는 경우 사서함에 대한 POP 액세스에 대한 예외를 확인해야 합니다.

*Microsoft 365 관리 센터에 도메인 추가(선택 사항):*

1. 탐색에서 설정 > 도메인을 선택한 다음, 도메인 추가를 선택합니다.

2. 적절한 필드에 도메인 이름을 입력합니다.

3. 화면의 지침에 따라 TXT 레코드를 사용하여 도메인을 확인합니다.

4. 메시지가 표시되면 Microsoft에서 DNS를 구성할 수 있도록 허용합니다.

5. Microsoft 365 MX 레코드 경로를 확인하는 지침을 완료합니다.

6. Microsoft 365 포함하도록 SPF TXT 레코드 구성

7. Microsoft 365 DKIM TXT 레코드를 구성하기 위한 지침을 완료합니다.

8. 로그아웃하고 관리 센터에 다시 로그인하여 DKIM이 활성화되었는지 확인합니다.

#### <a name="3-configure-gmail"></a>3. Gmail 구성

1. 시스템에 Exchange Online 메일을 끌어오도록 Gmail 구성

2. Teams 일정 추가 기능 구성

3. Gmail에서 비즈니스 도메인을 사용하도록 설정(선택 사항)
