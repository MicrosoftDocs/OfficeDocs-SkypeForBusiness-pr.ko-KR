---
title: 비즈니스용 Skype 서버 2019에서 리소스 계정 구성
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버 2019에 대한 리소스 계정을 설정합니다.
ms.openlocfilehash: 1d8294eb717982b5ac68df06a5370059e83a62c5
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919014"
---
# <a name="configure-resource-accounts"></a>리소스 계정 구성

비즈니스용 Skype 서버 2019 하이브리드 구현에서는 전화 시스템에서 제공하는 클라우드 서비스만 통합 메시징에 사용하며 Exchange Online과 통합되지 않습니다. 비즈니스용 Skype 서버 2019에서는 [이제 Microsoft 365 또는 Office 365의](/MicrosoftTeams/here-s-what-you-get-with-phone-system)전화 시스템으로 얻을 수 있는 클라우드 통화 큐 및 자동 전화 번호를 사용할 수 있습니다.

비즈니스용 Skype 서버 2019에서 전화 시스템 자동 전화 걸기 또는 통화 큐를 사용하려면 응용 프로그램 끝점 역할을 하는 리소스 계정을 만들고 전화 번호를 할당할 수 있는 리소스 계정을 만든 다음 온라인 Teams 관리 센터를 사용하여 통화 큐 또는 자동 전화 걸기 기능을 구성해야 합니다. 이 리소스 계정은 온라인에 있을 수 있습니다(온라인에 있는 리소스 계정을 만들 수 [있는 Microsoft Teams의](/MicrosoftTeams/manage-resource-accounts) 리소스 계정 관리 참조) 또는 이 문서에 설명된 바와 같이 프레미스에서 사용할 수 있습니다. 일반적으로 여러 개의 전화 시스템 자동 전화 연결 또는 통화 큐 노드가 있습니다. 각 노드는 온라인 또는 비즈니스용 Skype 서버 2019에 있을 수 있는 리소스 계정에 매핑됩니다.

기존 Exchange UM 자동 전화 교환 및 통화 큐 시스템이 있는 경우 Exchange Server 2019 또는 Exchange Online으로 전환하기 전에 아래 설명된 세부 정보를 수동으로 기록한 다음 Teams 관리 센터를 사용하여 완전히 새로운 시스템을 구현해야 합니다.

## <a name="overview"></a>개요

전화 시스템 자동 전화 연결 또는 통화 큐에 서비스 번호가 필요한 경우 다음과 같은 순서로 다양한 종속성을 충족할 수 있습니다.

1. 서비스 번호를 얻습니다.
2. 무료 전화 시스템 - 가상 [사용자 라이선스](/MicrosoftTeams/teams-add-on-licensing/virtual-user) 또는 리소스 계정과 함께 사용할 유료 전화 시스템 라이선스를 얻습니다.
3. 리소스 계정을 생성합니다. 연결된 리소스 계정이 있는 경우 자동 전화 통신 또는 통화 큐가 필요합니다.
4. 온라인과 프레미스 간의 Active Directory 동기화를 기다릴 수 있습니다.
5. 전화 시스템 라이선스를 리소스 계정에 할당합니다.
6. 서비스 번호를 리소스 계정에 할당합니다.
7. 전화 시스템 통화 큐 또는 자동 전화 걸기 만들기
8. 리소스 계정을 자동 전화 통신 또는 통화 큐에 연결합니다. (New-CsApplicationInstanceAssociation).

자동 전화 걸기 또는 통화 큐가 최상위 자동 전화 통신 아래에 중첩된 경우 자동 전화 걸기 및 통화 큐의 구조에 여러 지점을 입력하려는 경우 연결된 리소스 계정에는 전화 번호만 필요합니다.

온라인에 있는 조직의 사용자로 통화를 리디렉션하려면 전화  시스템 라이선스가 있어야 합니다. 이 사용자가 전화 시스템 라이선스를 Enterprise Voice 또는 Microsoft 365 또는 Office 365 통화 플랜을 사용할 수 있도록 설정되어 있어야 합니다. [Microsoft Teams 라이선스 할당을 참조합니다.](/MicrosoftTeams/assign-teams-licenses) 사용자에 대해 사용하도록 Enterprise Voice 수 있도록 설정하려면 다음을 Windows PowerShell. 예를 들어 다음을 실행합니다.  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

만들 전화 시스템 자동 전화 연결 또는 통화 큐가 중첩되어 전화 번호가 필요하지 않은 경우 프로세스는 다음입니다.

1. 리소스 계정 만들기  
2. 온라인과온-프레미스 간의 Active Directory 동기화 대기
3. 전화 시스템 자동 전화 연결 또는 통화 큐 만들기
4. 리소스 계정을 전화 시스템 자동 전화 연결 또는 통화 큐와 연결

## <a name="create-a-resource-account-with-a-phone-number"></a>전화 번호가 있는 리소스 계정 만들기

전화 번호를 사용하는 리소스 계정을 만들 경우 다음 순서로 다음 작업을 수행해야 합니다.

1. 무료 또는 무료 서비스 번호를 포트하거나 받을 수 있습니다. 이 번호는 다른 음성 서비스 또는 리소스 계정에 할당할 수 없습니다.

   리소스 계정에 전화 번호를 할당하기 전에 기존 무료 또는 무료 서비스 번호를 얻거나 이식해야 합니다. 무료 또는 무료 서비스 전화 번호를 다운로드하면 **Microsoft Teams** 관리 센터 음성 전화 번호에 표시하며 나열된 번호 유형이 서비스 - 무료로  >    >   **나열됩니다.**  서비스 번호를 확인하거나 [](/MicrosoftTeams/getting-service-phone-numbers) 기존 서비스 번호를 전송하려는 경우 Teams로 전화 번호 전송을 [참조합니다.](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)

   미국 이외 국가인 경우 Microsoft Teams 관리 센터를 사용하여 서비스 번호를 받을 수 없습니다. 대신 [조직의](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) 전화 번호 관리로 이동하여 미국 외부에서 전화 번호를 관리하는 방법을 참조하세요.

2. 전화 시스템 라이선스를 구입합니다. 자세한 내용은 다음을 참조하세요.  
   - [전화 시스템–가상 사용자 라이선스](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 and E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business 소프트웨어](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 각 전화 시스템 자동 전화 연결 또는 통화 큐에 대해 cmdlet을 실행하여 프레미스 리소스 계정을 만들고 각 계정에 이름, sip 주소 등이 `New-CsHybridApplicationEndpoint` 지정됩니다.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    이 명령에 대한 자세한 내용은 [New-CsHybridApplicationEndpoint를](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 참조합니다.

4. (선택 사항) 리소스 계정을 만든 후 AD가 온라인과 프레미스 간에 동기화될 때까지 기다리거나 동기화를 강제 적용하고 전화 시스템 자동 전화 연결 또는 통화 큐의 온라인 구성을 진행할 수 있습니다. 동기화를 강제로 수행하려면 AAD Connect를 실행하는 컴퓨터에서 다음 명령을 실행합니다(아직 실행하지 않은 경우 명령을 실행하려면 로드해야 `import-module adsync` 합니다).

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    이 명령에 대한 자세한 내용은 [Start-ADSyncSyncCycle을](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 참조하세요.
    
    이때 계정이 동기화된 것일 수 있지만 프로비전이 완료되지 않을 수 있습니다.  [Get-CsOnlineApplicationEndpoint의 출력을 검사합니다.](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint)  동기화된 끝점이 아직 프로비전을 완료하지 않은 경우 여기에 나타나지 않습니다.  Teams 설치 상태의 M365 포털에서 프로비전 요청의 [상태를 확인할 수 있습니다.](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)  이 프로비전 단계는 최대 24시간이 걸릴 수 있습니다.

5. 전화 시스템 - 가상 사용자 또는 전화 시스템 라이선스를 리소스 계정에 할당합니다. Microsoft [Teams 추가 기능](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) 라이선스 할당 및 사용자에게 라이선스 [할당을 참조합니다.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

   리소스 계정에 전화 번호를 할당하는 경우 이제 무료 전화 시스템인 가상 사용자 라이선스를 사용할 수 있습니다. 이렇게 하면 조직 수준의 전화 번호에 전화 시스템 기능이 제공될 수 있으며 자동 전화 걸기 및 통화 큐 기능을 만들 수 있습니다.


6. 서비스 번호를 리소스 계정에 할당합니다. 이 명령을 사용하여 -LineURI 옵션과 함께 전화 번호를 리소스 계정에 `Set-CsHybridApplicationEndpoint` 할당합니다.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    이 명령에 대한 자세한 내용은 [Set-CsHybridApplicationEndpoint를](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 참조합니다.

    리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당하려면 다음 cmdlet을 사용하세요.

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   리소스 계정에는 할당된 전화 번호가 필요한 경우 최상위 자동 전화 번호 또는 통화 큐에 할당됩니다. 사용자(구독자) 전화 번호를 리소스 계정에 할당할 수 없습니다. 서비스 전화 번호 또는 무료 전화 번호만 사용할 수 있습니다.

     직접 라우팅 또는 하이브리드 번호를 리소스 계정에 할당할 수 있습니다. 자세한 내용은 [직접](/MicrosoftTeams/direct-routing-plan) 라우팅 계획 및 클라우드 자동 연결 [계획(Plan Cloud auto attendants)을 참조합니다.](plan-cloud-auto-attendant.md)

     > [!NOTE]
     > 자동 전화 연결 및 통화 큐에 대한 리소스 계정에 할당된 직접 라우팅 서비스 번호는 Microsoft Teams 사용자 및 에이전트에 한해 지원됩니다.

7. 전화 시스템 자동 전화 연결 또는 통화 큐를 만들 수 있습니다. 다음 중 하나를 참조하세요.

   - [클라우드 자동 전화 교환 설정](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [클라우드 통화 큐 만들기](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. 리소스 계정을 이전에 선택한 전화 시스템 자동 전화 통신 또는 통화 큐와 연결합니다.

## <a name="create-a-resource-account-without-a-phone-number"></a>전화 번호 없이 리소스 계정 만들기

이 섹션에서는 프레미스에 있는 리소스 계정 만들기에 대해 설명합니다. 온라인에 있는 리소스 계정 만들기는 Microsoft Teams의 리소스 계정 관리에서 [설명됩니다.](/MicrosoftTeams/manage-resource-accounts)

이러한 단계는 새 전화 시스템 자동 전화 교환 또는 통화 큐 구조를 만들거나 Exchange UM에서 원래 만든 구조를 다시 작성하는 경우 모두 필요합니다.

비즈니스용 Skype 프런트 엔드 서버에 로그인하고 다음 PowerShell cmdlet을 실행합니다.

1. 각 전화 시스템 자동 전화 연결 또는 통화 큐에 대해 cmdlet을 실행하여 프레미스 리소스 계정을 만들고 각 계정에 이름, sip 주소 등이 `New-CsHybridApplicationEndpoint` 지정됩니다.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    이 명령에 대한 자세한 내용은 [New-CsHybridApplicationEndpoint를](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 참조합니다.

2. (선택 사항) 리소스 계정을 만든 후 AD가 온라인과 프레미스 간에 동기화될 때까지 기다리거나 동기화를 강제 적용하고 전화 시스템 자동 전화 연결 또는 통화 큐의 온라인 구성을 진행할 수 있습니다. 동기화를 강제로 수행하려면 AAD Connect를 실행하는 컴퓨터에서 다음 명령을 실행합니다(아직 실행하지 않은 경우 명령을 실행하려면 로드해야 `import-module adsync` 합니다).

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    이 명령에 대한 자세한 내용은 [Start-ADSyncSyncCycle을](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 참조하세요.

3. 전화 시스템 자동 전화 연결 또는 통화 큐를 만들 수 있습니다. 다음 중 하나를 참조하세요.
   - [클라우드 자동 전화 교환 설정](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [클라우드 통화 큐 만들기](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 이전에 선택한 리소스 계정과 전화 시스템 자동 전화 통신 또는 통화 큐를 연결합니다.

## <a name="test-the-implementation"></a>구현 테스트

구현을 테스트하는 가장 좋은 방법은 전화 시스템 자동 전화 연결 또는 통화 큐에 대해 구성된 번호를 호출하고 에이전트 또는 메뉴 중 하나에 연결하는 것입니다. 관리 센터 작업 창에서 테스트 단추를 사용하여 테스트 호출을 신속하게 **걸** 수도 있습니다. 전화 시스템 자동 전화 연결 또는 통화 큐를 변경하려면 이 옵션을 선택하고 작업 창에서 편집을 **클릭합니다.** 

> [!TIP]
> 리소스 계정이 통화 큐 또는 자동 전화 회의에 할당되는 데 어려움이 있는 [](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) 경우 [Microsoft Teams에](/MicrosoftTeams/Known-issues#phone-system) 대한 알려진 문제와 Microsoft Teams 블로그의 하이브리드 응용 프로그램 인스턴스를 수정하는 방법 섹션을 참조하세요.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Exchange UM 자동 전화 교환 또는 통화 큐를 전화 시스템으로 이동

Exchange UM에서 전화 시스템으로 마이그레이션하려면 통화 큐 및 자동 전화 교환 구조를 다시 설정해야 합니다. 이 경우 통화 큐와 자동 전화 교환 구조를 직접 마이그레이션할 수 없습니다. 통화 큐 및 자동 전화 걸기 집합을 다시 구현하는 경우:

1. 관리자로 로그인한 동안 Exchange 2013 또는 2016 시스템에서 다음 명령을 실행하여 모든 Exchange UM 자동 전화 교환 및 통화 큐 목록을 얻습니다.

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 나열된 각 Exchange UM 통화 큐 또는 자동 전화 교환에 대해 구조, 설정 및 관련 소리 또는 텍스트 음성 음성 파일의 복사본을 확인합니다(출력의 GUID는 파일이 저장된 폴더의 이름임). 다음 명령을 실행하여 이러한 세부 정보를 얻을 수 있습니다.

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    이 명령에 대한 자세한 내용은 [Get-UMAutoAttendant를](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 참조합니다. 캡처해야 할 수 있는 옵션의 전체 목록은 [UMAutoAttendant](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) 구성원이지만 가장 중요한 옵션은 다음과 같습니다.

    - 업무 시간
    - 업무 시간 이행 시간
    - 언어
    - 휴일 일정

3. 앞서 설명한 새 On-premises 끝점을 만드시다.
   테스트 목적으로 최상위 자동 전화 번호를 임시로 할당합니다.

4. 앞서 설명한 바와 같이 끝점을 사용하는 전화 시스템 자동 전화 연결 또는 통화 큐를 구성합니다.

5. 전화 시스템 자동 전화 연결 또는 통화 큐를 테스트합니다.

6. Exchange UM 통화 큐 또는 자동 전화 교환에 연결된 전화 번호를 해당 전화 시스템 자동 전화 교환 또는 통화 큐에 다시 배정합니다.  

   이제 이미 UM 음성메일을 마이그레이션한 경우 2019년 10월로 마이그레이션할 Exchange Server 있습니다.

## <a name="see-also"></a>참고 항목

[클라우드 통화 큐 만들기](/MicrosoftTeams/create-a-phone-system-call-queue)

[클라우드 자동 전화 교환이란?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[클라우드 자동 전화 교환 설정](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[클라우드 자동 전화 교환 계획](plan-cloud-auto-attendant.md)

[클라우드 통화 큐 계획](plan-call-queue.md)

[On-premises 사용자를 위한 클라우드 음성메일 서비스 계획](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Microsoft Teams에서 리소스 계정 관리](/MicrosoftTeams/manage-resource-accounts)  -  \( 온라인에 있는 리소스 계정을 만들 수 있습니다.\)
