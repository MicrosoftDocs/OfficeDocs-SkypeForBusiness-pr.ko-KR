---
title: 비즈니스용 Skype 서버 2019에서 자원 계정 구성
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버 2019에 대 한 리소스 계정을 설정 합니다.
ms.openlocfilehash: a307a5ed40c52579020f4cd0eef6646afdb15649
ms.sourcegitcommit: 5ec5df597614d402917e0585575dd69acda22172
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2019
ms.locfileid: "36253957"
---
# <a name="configure-resource-accounts"></a>자원 계정 구성

비즈니스용 Skype Server 2019 하이브리드 구현은 통합 메시징을 위해 전화 시스템에서 제공 하는 클라우드 서비스만 사용 하 고 Exchange Online과 통합 하지 마세요. 비즈니스용 Skype 서버 2019에서 이제 클라우드 통화 대기열과 자동 전화를 사용할 수 있습니다 [Office 365에서 전화 시스템을](/MicrosoftTeams/here-s-what-you-get-with-phone-system)사용 하 여 다음을 수행 하세요.

비즈니스용 Skype Server 2019에서 전화 시스템 자동 전화 교환 또는 통화 대기열을 사용 하려면 응용 프로그램 끝점 역할을 하는 리소스 계정을 만들고 전화 번호를 할당 하 고 온라인 팀 관리 센터를 사용 하 여 통화 대기열을 구성 해야 합니다. 자동 전화 교환. 이 리소스 계정은이 문서에서 설명 하는 대로 온라인 ( [Microsoft 팀의 리소스 계정 관리](/MicrosoftTeams/manage-resource-accounts) ) 또는 온-프레미스로 할 수 있습니다. 일반적으로 여러 개의 전화 시스템 자동 전화 교환 또는 통화 대기열 노드가 있으며, 각각은 리소스 계정으로 매핑되고 온라인 또는 비즈니스용 Skype 서버 2019에 있습니다.

기존 Exchange UM 자동 전화 교환 및 통화 대기열 시스템을 사용 하는 경우 Exchange Server 2019 또는 Exchange online으로 전환 하기 전에 아래 설명 된 대로 세부 정보를 수동으로 기록해 야 하 고 팀 관리 센터를 사용 하 여 완전히 새로운 시스템을 구현 해야 합니다. .

## <a name="overview"></a>개요

전화 시스템 자동 전화 교환 또는 통화 대기열에 서비스 번호가 필요한 경우 다음 순서에 따라 다양 한 종속성을 충족할 수 있습니다.

1. 서비스 번호 가져오기
2. 무료 전화 시스템- [가상 사용자 라이선스](/MicrosoftTeams/teams-add-on-licensing/virtual-user) 또는 리소스 계정과 함께 사용 하는 유료 전화 시스템 라이선스를 취득 하세요.
3. 자원 계정을 만듭니다. 연결 된 리소스 계정이 있는 경우 자동 전화 교환 또는 통화 대기열이 필요 합니다.
4. 온라인 및 온-프레미스 간의 active directory 동기화가 끝날 때까지 기다립니다.
5. 전화 시스템 라이선스를 리소스 계정에 할당 합니다.
6. 서비스 번호를 리소스 계정에 할당 합니다.
7. 전화 시스템 통화 대기열 또는 자동 전화 교환을 만듭니다.
8. 리소스 계정을 자동 전화 교환 또는 통화 대기열과 연결 합니다 (새-CsApplicationInstanceAssociation).

자동 전화 교환 또는 통화 대기열이 최상위 수준 자동 전화 교환 아래에 중첩 되는 경우 연결 된 리소스 계정은 자동 전화 교환 및 통화 대기열의 구조에 여러 항목을 입력 하려는 경우에만 전화 번호를 필요로 합니다.

온라인 상태인 조직 내 사용자에 게 통화를 리디렉션하려면 **전화 시스템** 라이선스가 있어야 하며 Enterprise Voice를 사용 하도록 설정 되어 있거나 Office 365 통화 계획이 있어야 합니다. [Microsoft 팀 라이선스 할당](/MicrosoftTeams/assign-teams-licenses)을 참조 하세요. 엔터프라이즈 음성에 대해 사용 하도록 설정 하려면 Windows PowerShell을 사용 하면 됩니다. 예를 들어 다음을 실행 합니다.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

생성 하는 전화 시스템 자동 전화 교환 또는 통화 대기열이 중첩 되 고 전화 번호가 필요 하지 않은 경우 프로세스는 다음과 같이 수행 됩니다.

1. 자원 계정 만들기  
2. 온라인 및 온-프레미스 간 active directory 동기화 대기
3. 전화 시스템 자동 전화 교환 또는 통화 대기열 만들기
4. 리소스 계정을 전화 시스템 자동 전화 교환 또는 통화 대기열과 연결

## <a name="create-a-resource-account-with-a-phone-number"></a>전화 번호를 사용 하 여 자원 계정 만들기

전화 번호를 사용 하는 리소스 계정을 만들려면 다음 작업을 순서 대로 수행 해야 합니다.

1. 무료 또는 유료 서비스 번호를 사용 하거나 포트를 구입 합니다. 다른 음성 서비스나 리소스 계정에 번호를 배정할 수 없습니다.

   리소스 계정에 전화 번호를 지정 하기 전에 기존의 유료 또는 무료 서비스 번호를 가져오거나 이식 해야 합니다. 무료 또는 무료 서비스 전화 번호를 얻은 후에는 **Microsoft 팀 관리 센터** > **음성** > **전화 번호로**표시 되며 나열 된 **번호 유형이** 서비스로 나열 됩니다 ( **무료)**. 서비스 번호를 얻으려면 [서비스 전화 번호 가져오기를](/MicrosoftTeams/getting-service-phone-numbers) 참조 하거나 기존 서비스 번호를 전송 하려면 [전화 번호를 Office 365에](/MicrosoftTeams/transfer-phone-numbers-to-office-365)연결을 참조 하세요.

   미국 이외의 지역에 거주 하는 경우에는 Microsoft 팀 관리 센터를 사용 하 여 서비스 번호를 얻을 수 없습니다. 미국 이외의 지역에서이를 수행 하는 방법을 확인 하려면 [조직의 전화 번호 관리](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) 로 이동 하세요.

2. 전화 시스템 라이선스를 구입 합니다. 보기  
   - [전화 시스템-가상 사용자 라이선스](/MicrosoftTeams/teams-add-on-licensing/virtual-user.md)
   - [Office 365 Enterprise E1 및 E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 비즈니스 소프트웨어](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 각 전화 시스템 자동 전화 교환 또는 통화 대기열에 `New-CsHybridApplicationEndpoint` 대해 cmdlet을 실행 하 여 온-프레미스 리소스 계정을 만들고 각 이름에 대 한 이름과 sip 주소를 지정 합니다.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    이 명령에 대 한 자세한 내용은 [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 을 참조 하세요.

4. ) 리소스 계정을 만든 후에는 광고가 온라인 및 구내 간에 동기화 될 때까지 기다리거나 동기화를 강제 하 고 전화 시스템 자동 전화 교환 또는 통화 대기열의 온라인 구성으로 계속 진행할 수 있습니다. 강제로 동기화 하려면 AAD Connect를 실행 하는 컴퓨터에서 다음 명령을 실행 합니다 (명령을 실행 하기 위해 이미 로드 `import-module adsync` 해야 하는 경우에는 완료 하지 않은 경우).

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    이 명령에 대 한 자세한 내용은 [시작-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 을 참조 하세요.

5. 전화 시스템-가상 사용자 또는 전화 시스템 라이선스를 리소스 계정에 할당 합니다. [Microsoft 팀 라이선스 할당](/MicrosoftTeams/assign-teams-licenses) 및 [한 명의 사용자에 게 라이선스 할당](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)을 참조 하세요.

   리소스 계정에 전화 번호를 지정 하는 경우 비용 무료 전화 시스템-가상 사용자 라이선스를 사용할 수 있습니다. 이렇게 하면 조직 수준에서 전화 시스템 기능을 전화 번호에 제공 하 고 자동 전화 교환 및 통화 대기열 기능을 만들 수 있습니다.


6. 서비스 번호를 리소스 계정에 할당 합니다. `Set-CsHybridApplicationEndpoint` 명령을 사용 하 여 리소스 계정에 전화 번호 (-lineuri 옵션 포함)를 할당 합니다.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    이 명령에 대 한 자세한 내용은 [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 을 참조 하세요.

    리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당 하려면 다음 cmdlet을 사용 합니다.

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

최상위 자동 전화 교환 또는 통화 대기열에 할당 되는 경우, 리소스 계정에는 지정 된 전화번호가 필요 합니다. 사용자 (구독자) 전화 번호를 리소스 계정에 할당할 수 없는 경우에는 서비스 수신자 또는 무료 전화 번호만 사용할 수 있습니다.

  직접 라우팅 하이브리드 번호를 리소스 계정에 할당할 수 있습니다.  자세한 내용은 [직접 라우팅 계획](/MicrosoftTeams/direct-routing-plan.md) 을 참조 하세요.

  > [!NOTE]
  > 자동 전화 교환 및 통화 대기열에 대 한 리소스 계정에 할당 된 직접 라우팅 서비스 번호는 Microsoft 팀 사용자 및 에이전트만 사용할 수 있습니다.

7. 전화 시스템 자동 전화 교환 또는 통화 대기열을 만듭니다. 다음 중 하나를 참조 하세요.

   - [클라우드 자동 전화 교환 설정](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [클라우드 통화 대기열 만들기](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. 이전에 선택한 전화 시스템 자동 전화 교환 또는 통화 대기열과 리소스 계정을 연결 합니다.

소규모 비즈니스 구현의 예는 Small business에서 사용할 수 있습니다. [예-자동 전화 교환](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) 및 [small business 설정 예-통화 대기열 설정](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)

## <a name="create-a-resource-account-without-a-phone-number"></a>전화 번호 없이 자원 계정 만들기

이 섹션에서는 온-프레미스에 속한 리소스 계정 만들기에 대해 설명 합니다. 온라인 인 리소스 계정을 만들려면 [Microsoft 팀의 자원 계정 관리](/MicrosoftTeams/manage-resource-accounts)에서 설명 합니다.

이러한 단계는 새 전화 시스템 자동 전화 교환 또는 통화 대기열 구조를 만들거나 Exchange UM에서 원래 만든 구조를 다시 만드는 경우에 필요 합니다.

비즈니스용 Skype 프런트 엔드 서버에 로그인 하 고 다음 PowerShell cmdlet을 실행 합니다.

1. 각 전화 시스템 자동 전화 교환 또는 통화 대기열에 `New-CsHybridApplicationEndpoint` 대해 cmdlet을 실행 하 여 온-프레미스 리소스 계정을 만들고 각 이름에 대 한 이름과 sip 주소를 지정 합니다.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    이 명령에 대 한 자세한 내용은 [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 을 참조 하세요.

2. ) 리소스 계정을 만든 후에는 광고가 온라인 및 구내 간에 동기화 될 때까지 기다리거나 동기화를 강제 하 고 전화 시스템 자동 전화 교환 또는 통화 대기열의 온라인 구성으로 계속 진행할 수 있습니다. 강제로 동기화 하려면 AAD Connect를 실행 하는 컴퓨터에서 다음 명령을 실행 합니다 (명령을 실행 하기 위해 이미 로드 `import-module adsync` 해야 하는 경우에는 완료 하지 않은 경우).

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    이 명령에 대 한 자세한 내용은 [시작-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 을 참조 하세요.

3. 전화 시스템 자동 전화 교환 또는 통화 대기열을 만듭니다. 다음 중 하나를 참조 하세요.
   - [클라우드 자동 전화 교환 설정](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [클라우드 통화 대기열 만들기](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 이전에 선택한 리소스 계정과 전화 시스템 자동 전화 교환 또는 통화 대기열을 연결 합니다.

소규모 비즈니스 구현의 예는 Small business에서 사용할 수 있습니다. [예-자동 전화 교환](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) 및 [small business 설정 예-통화 대기열 설정](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)

## <a name="test-the-implementation"></a>구현 테스트

구현을 테스트 하는 가장 좋은 방법은 전화 시스템 자동 전화 교환 또는 통화 대기열에 대해 구성 된 번호를 호출 하 고 에이전트 또는 메뉴 중 하나에 연결 하는 것입니다. 관리 센터 작업 창의 **테스트 단추** 를 사용 하 여 테스트 호출을 빠르게 수행할 수도 있습니다. 전화 시스템 자동 전화 교환 또는 통화 대기열을 변경 하려는 경우이를 선택 하 고 작업 창에서 **편집**을 클릭 합니다.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Exchange UM 자동 전화 교환 또는 통화 대기열을 전화 시스템으로 이동

Exchange UM에서 전화 시스템으로 마이그레이션한 후에는 통화 대기열 및 자동 전화 교환 구조를 다시 만들어야 하며, 한 쪽에서 다른으로 직접 마이그레이션하는 것은 지원 되지 않습니다. 통화 대기열 및 자동 전화 교환 집합을 다시 구현 하려면 다음을 수행 합니다.

1. 관리자 권한으로 로그인 하는 동안 Exchange 2013 또는 2016 시스템에서 다음 명령을 실행 하 여 모든 Exchange UM 자동 전화 교환 및 통화 큐의 목록을 가져옵니다.

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 나열 된 각 Exchange UM 통화 큐 또는 자동 전화 교환에 대해 구조에서 해당 위치를 확인 하 고, 연결 된 소리 또는 텍스트 음성 변환 파일의 복사본을 가져옵니다 (출력의 guid는 파일이 저장 된 폴더의 이름). 다음 명령을 실행 하 여 이러한 세부 정보를 얻을 수 있습니다.

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    이 명령에 대 한 자세한 내용은 [Get UMAutoAttendant 전화 교환을](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 참조 하세요. 캡처 해야 할 수 있는 옵션의 전체 목록은 [Umautoattendant 전화 교환 구성원](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) 이지만 가장 중요 한 몇 가지 옵션은 다음과 같습니다.

    - 업무 시간
    - 근무 외 시간
    - 언어
    - 휴일 일정

3. 앞에서 설명한 대로 새 온-프레미스 끝점을 만듭니다.
   테스트 목적으로 최상위 자동 전화 교환 임시 번호를 할당 합니다.

4. 앞에서 설명한 대로 끝점을 사용 하는 전화 시스템 자동 전화 교환 또는 통화 대기열을 구성 합니다.

   Small business 이라는 자습서의 연습을 사용 하는 것이 유용할 수 있습니다. 기존 Exchange UM 시스템의 계층 구조에 대 한 논리적 지도를 만들기 위해 [자동 전화 교환 설정](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) 하기를 예로 나와 있습니다.
5. 전화 시스템 자동 전화 교환 또는 통화 대기열을 테스트 합니다.
6. Exchange UM 통화 대기열 또는 자동 전화 교환에 연결 된 전화 번호를 해당 전화 시스템 자동 전화 교환 또는 통화 대기열에 다시 할당 합니다.  

   이 시점에서 이미 UM 보이스 메일을 마이그레이션한 경우에는 Exchange Server 2019으로 마이그레이션해야 하는 위치에 있어야 합니다.

## <a name="see-also"></a>참고 항목

[클라우드 통화 대기열 만들기](/MicrosoftTeams/create-a-phone-system-call-queue)

[클라우드 자동 전화 교환 이란?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[클라우드 자동 전화 교환 설정](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[클라우드 자동 전화 교환 계획](plan-cloud-auto-attendant.md)

[클라우드 통화 대기열 계획](plan-call-queue.md)

[온-프레미스 사용자를 위한 클라우드 보이스 메일 서비스 계획](plan-cloud-voicemail.md)

[새로운 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[새로운 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Microsoft 팀](/MicrosoftTeams/manage-resource-accounts) - \(에서 자원 계정을 관리 하 여 온라인으로 자원 계정 만들기 홈\)
