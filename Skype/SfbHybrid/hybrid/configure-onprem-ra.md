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
ms.localizationpriority: medium
ms.collection: ''
description: 비즈니스용 Skype 서버 2019에 대한 리소스 계정을 설정합니다.
ms.openlocfilehash: ebaf79229097df8d3477b4d9b74504c278bfd59c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615614"
---
# <a name="configure-resource-accounts"></a>리소스 계정 구성

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

비즈니스용 Skype 서버 2019 하이브리드 구현은 통합 메시징을 위해 Phone System에서 제공하는 클라우드 서비스만 사용하며 Exchange Online 통합되지 않습니다. 비즈니스용 Skype 서버 2019에서는 이제 [Microsoft 365 또는 Office 365 전화 시스템에서 얻을 수 있는 항목에](/MicrosoftTeams/here-s-what-you-get-with-phone-system) 설명된 클라우드 통화 큐 및 자동 전화 교환을 사용할 수 있습니다.

비즈니스용 Skype 서버 2019에서 전화 시스템 자동 전화 교환 또는 통화 큐를 사용하려면 애플리케이션 엔드포인트 역할을 하고 전화 번호를 할당할 수 있는 리소스 계정을 만든 다음 온라인 Teams 관리 센터를 사용하여 통화 큐 또는 자동 전화 교환을 구성해야 합니다. 이 리소스 계정은 이 문서에 설명된 대로 온라인( [Microsoft Teams에서 리소스 계정 관리](/MicrosoftTeams/manage-resource-accounts) 참조) 온라인 또는 온-프레미스에서 홈으로 사용할 수 있습니다. 일반적으로 여러 전화 시스템 자동 전화 교환 또는 통화 큐 노드가 있으며, 각 노드는 리소스 계정에 매핑되며, 이 노드는 온라인 또는 2019년 비즈니스용 Skype 서버 홈으로 사용할 수 있습니다.

기존 Exchange UM 자동 전화 교환 및 통화 큐 시스템이 있는 경우 Exchange Server 2019 또는 Exchange Online으로 전환하기 전에 아래 설명된 대로 세부 정보를 수동으로 기록한 다음 Teams 관리 센터를 사용하여 완전히 새로운 시스템을 구현해야 합니다.

## <a name="overview"></a>개요

전화 시스템 자동 전화 교환 또는 통화 큐에 서비스 번호가 필요한 경우 다음과 같은 순서로 다양한 종속성을 충족할 수 있습니다.

1. 서비스 번호를 가져옵니다.
2. 리소스 계정과 함께 사용할 [무료 Microsoft Teams 전화 리소스 계정 라이선스](/MicrosoftTeams/teams-add-on-licensing/virtual-user) 또는 유료 전화 시스템 라이선스를 얻습니다.
3. 리소스 계정을 만듭니다. 연결된 리소스 계정을 사용하려면 자동 전화 교환 또는 통화 큐가 필요합니다.
4. 온라인과 온-프레미스 간의 Active Directory 동기화를 기다립니다.
5. 리소스 계정에 전화 시스템 라이선스를 할당합니다.
6. 리소스 계정에 서비스 번호를 할당합니다.
7. 전화 시스템 통화 큐 또는 자동 전화 교환을 만듭니다.
8. 리소스 계정을 자동 전화 교환 또는 호출 큐에 연결합니다(New-CsApplicationInstanceAssociation).

자동 전화 교환 또는 통화 큐가 최상위 자동 전화 교환 아래에 중첩된 경우 연결된 리소스 계정에는 자동 전화 교환 및 통화 큐 구조에 여러 지점의 진입점이 필요한 경우에만 전화 번호가 필요합니다.

온라인이 있는 조직의 사용자에게 전화를 리디렉션하려면 **전화 시스템** 라이선스가 있어야 하며 Enterprise Voice 사용할 수 있거나 Microsoft 365 또는 Office 365 통화 플랜이 있어야 합니다. [Microsoft Teams 라이선스 할당을 참조하세요](/MicrosoftTeams/assign-teams-licenses). Enterprise Voice 사용하도록 설정하려면 Windows PowerShell 사용할 수 있습니다. 예를 들어 다음을 실행합니다.  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

만드는 전화 시스템 자동 전화 교환 또는 통화 큐가 중첩되고 전화 번호가 필요하지 않은 경우 프로세스는 다음과 같습니다.

1. 리소스 계정 만들기  
2. 온라인과 온-프레미스 간에 Active Directory 동기화 대기
3. 전화 시스템 자동 전화 교환 또는 통화 큐 만들기
4. 리소스 계정을 전화 시스템 자동 전화 교환 또는 통화 큐에 연결

## <a name="create-a-resource-account-with-a-phone-number"></a>전화 번호가 있는 리소스 계정 만들기

전화 번호를 사용하는 리소스 계정을 만들려면 다음 순서대로 다음 작업을 수행해야 합니다.

1. 유료 또는 무료 서비스 번호를 포트하거나 받을 수 있습니다. 이 번호는 다른 음성 서비스 또는 리소스 계정에 할당할 수 없습니다.

   리소스 계정에 전화 번호를 할당하기 전에 기존 통행료 또는 무료 서비스 번호를 받거나 포팅해야 합니다. 유료 또는 무료 서비스 전화 번호를 받은 후 **Microsoft Teams 관리 센터** > **음성** > **전화 번호** 에 표시되고 나열된 **번호 유형** 이 **서비스 - 무료** 로 나열됩니다. 서비스 번호를 가져오려면 [서비스 전화 번호 가져오기](/MicrosoftTeams/getting-service-phone-numbers) 또는 기존 서비스 번호를 전송하려는 경우 [Teams로 전화 번호 전송을](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 참조하세요.

   미국 외부에 있는 경우 Microsoft Teams 관리 센터를 사용하여 서비스 번호를 가져올 수 없습니다. 대신 [조직의 전화 번호 관리](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)로 이동하여 미국 외부에서 수행하는 방법을 확인합니다.

2. 전화 시스템 라이선스를 구입합니다. 자세한 내용은 다음을 참조하세요.  
   - [리소스 계정 라이선스 Microsoft Teams 전화](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 and E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 각 전화 시스템 자동 전화 교환 또는 통화 큐에 대한 cmdlet을 실행 `New-CsHybridApplicationEndpoint` 하여 온-프레미스 리소스 계정을 만들고 각각 이름, sip 주소 등을 지정합니다.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    이 명령에 대한 자세한 내용은 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 를 참조하세요.

4. (선택 사항) 리소스 계정이 만들어지면 AD가 온라인과 온-프레미스 간에 동기화되기를 기다리거나 강제로 동기화하고 전화 시스템 자동 전화 교환 또는 통화 큐의 온라인 구성으로 진행할 수 있습니다. 동기화를 강제로 수행하려면 AAD Connect를 실행하는 컴퓨터에서 다음 명령을 실행합니다(아직 수행하지 않은 경우 명령을 실행하려면 로드 `import-module adsync` 해야 함).

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    이 명령에 대한 자세한 내용은 [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 을 참조하세요.

    이 시점에서 계정이 동기화되었을 수 있지만 프로비전이 완료되지 않을 수 있습니다.  [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint)의 출력을 확인합니다.  동기화된 엔드포인트가 아직 프로비저닝을 완료하지 않은 경우 여기에 표시되지 않습니다.  [Teams 설치 상태](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning) 아래의 M365 포털에서 프로비저닝 요청의 상태를 확인할 수 있습니다.  이 프로비저닝 단계는 최대 24시간이 걸릴 수 있습니다.

5. **리소스 계정에 Microsoft Teams 전화 리소스 계정** 라이선스 또는 **Teams 전화 표준 요금제** 라이선스를 할당합니다. [Microsoft Teams 추가 기능 라이선스 할당](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) 및 [사용자에게 라이선스 할당을 참조하세요](/microsoft-365/admin/manage/assign-licenses-to-users).

   리소스 계정에 전화 번호를 할당하는 경우 이제 비용 없는 **Microsoft Teams 전화 Resource Account** 라이선스를 사용할 수 있습니다. 이렇게 하면 조직 수준에서 전화 번호에 전화 시스템 기능을 제공하고 자동 전화 교환 및 통화 큐 기능을 만들 수 있습니다.

6. 리소스 계정에 서비스 번호를 할당합니다. 명령을 `Set-CsHybridApplicationEndpoint` 사용하여 리소스 계정에 전화 번호(-LineURI 옵션 포함)를 할당합니다.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    이 명령에 대한 자세한 내용은 [Set-CsHybridApplicationEndpoint](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 를 참조하세요.

    리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당하려면 다음 cmdlet을 사용합니다.

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   최상위 자동 전화 교환 또는 통화 큐에 할당되는 경우 리소스 계정에 할당된 전화 번호가 필요합니다. 사용자(구독자) 전화 번호는 리소스 계정에 할당할 수 없으며 서비스 요금 또는 무료 전화 번호만 사용할 수 있습니다.

     리소스 계정에 직접 라우팅 또는 하이브리드 번호를 할당할 수 있습니다. 자세한 내용은 [직접 라우팅 계획](/MicrosoftTeams/direct-routing-plan) 및 [클라우드 자동 전화 교환 계획을 참조하세요](plan-cloud-auto-attendant.md).

     > [!NOTE]
     > 자동 전화 교환 및 통화 큐에 대한 리소스 계정에 할당된 직접 라우팅 서비스 번호는 Microsoft Teams 사용자 및 에이전트에 대해서만 지원됩니다.

7. 전화 시스템 자동 전화 교환 또는 통화 큐를 만듭니다. 다음 중 하나를 참조하세요.

   - [클라우드 자동 전화 교환 설정](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [클라우드 통화 큐 만들기](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. 리소스 계정을 이전에 선택한 전화 시스템 자동 전화 교환 또는 통화 큐에 연결합니다.

## <a name="create-a-resource-account-without-a-phone-number"></a>전화 번호 없이 리소스 계정 만들기

이 섹션에서는 온-프레미스에 있는 리소스 계정을 만드는 방법을 설명합니다. 온라인 홈이 있는 리소스 계정 만들기는 [Microsoft Teams의 리소스 계정 관리에서 설명합니다](/MicrosoftTeams/manage-resource-accounts).

이러한 단계는 새로운 전화 시스템 자동 전화 교환 또는 통화 큐 구조를 만들거나 Exchange UM에서 원래 만든 구조를 다시 빌드하는 경우에 필요합니다.

비즈니스용 Skype 프런트 엔드 서버에 로그인하고 다음 PowerShell cmdlet을 실행합니다.

1. 각 전화 시스템 자동 전화 교환 또는 통화 큐에 대한 cmdlet을 실행 `New-CsHybridApplicationEndpoint` 하여 온-프레미스 리소스 계정을 만들고 각각 이름, sip 주소 등을 지정합니다.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    이 명령에 대한 자세한 내용은 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 를 참조하세요.

2. (선택 사항) 리소스 계정이 만들어지면 AD가 온라인과 온-프레미스 간에 동기화되기를 기다리거나 강제로 동기화하고 전화 시스템 자동 전화 교환 또는 통화 큐의 온라인 구성으로 진행할 수 있습니다. 동기화를 강제로 수행하려면 AAD Connect를 실행하는 컴퓨터에서 다음 명령을 실행합니다(아직 수행하지 않은 경우 명령을 실행하려면 로드 `import-module adsync` 해야 함).

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    이 명령에 대한 자세한 내용은 [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 을 참조하세요.

3. 전화 시스템 자동 전화 교환 또는 통화 큐를 만듭니다. 다음 중 하나를 참조하세요.
   - [클라우드 자동 전화 교환 설정](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [클라우드 통화 큐 만들기](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 이전에 선택한 리소스 계정 및 전화 시스템 자동 전화 교환 또는 통화 큐를 연결합니다.

## <a name="test-the-implementation"></a>구현 테스트

구현을 테스트하는 가장 좋은 방법은 전화 시스템 자동 전화 교환 또는 통화 큐에 대해 구성된 번호를 호출하고 에이전트 또는 메뉴 중 하나에 연결하는 것입니다. 관리 센터 작업 창의 테스트 **단추를 사용하여 테스트** 호출을 빠르게 수행할 수도 있습니다. 전화 시스템 자동 전화 교환 또는 통화 큐를 변경하려면 이를 선택한 다음 작업 창에서 **편집** 을 클릭합니다. 

> [!TIP]
> 리소스 계정에 통화 큐 또는 자동 전화 교환에 할당하는 데 어려움이 있는 경우 [Microsoft Teams의 알려진 문제 및 Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) 블로그의 [하이브리드 애플리케이션 인스턴스 수정 방법](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) 섹션을 참조하세요.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Exchange UM 자동 전화 교환 또는 통화 큐를 전화 시스템으로 이동

Exchange UM에서 전화 시스템으로 마이그레이션하려면 통화 큐 및 자동 전화 교환 구조를 다시 만들어야 하며, 한 쪽에서 다른 시스템으로 직접 마이그레이션하는 것은 지원되지 않습니다. 통화 큐 및 자동 전화 교환 집합을 다시 구현하려면 다음을 수행합니다.

1. 관리자로 로그인하는 동안 Exchange 2013 또는 2016 시스템에서 다음 명령을 실행하여 모든 Exchange UM 자동 전화 교환 및 통화 큐 목록을 가져옵니다.

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 나열된 각 Exchange UM 통화 큐 또는 자동 전화 교환에 대해 구조, 설정 및 관련 사운드 또는 텍스트 음성 변환 파일의 복사본을 가져옵니다(출력의 GUID는 파일이 저장된 폴더의 이름이 됩니다). 다음 명령을 실행하여 이러한 세부 정보를 가져올 수 있습니다.

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    이 명령에 대한 자세한 내용은 [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 를 참조하세요. 캡처해야 할 수 있는 옵션의 전체 목록은 [UMAutoAttendant 멤버](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) 에 있지만 가장 중요한 옵션은 다음과 같습니다.

    - 업무 시간
    - 업무 외 시간
    - 언어
    - 휴일 일정

3. 앞에서 설명한 대로 새 온-프레미스 엔드포인트를 만듭니다.
   테스트 목적으로 최상위 자동 전화 교환에 임시 번호를 할당합니다.

4. 앞에서 설명한 대로 엔드포인트를 사용하는 전화 시스템 자동 전화 교환 또는 통화 큐를 구성합니다.

5. 전화 시스템 자동 전화 교환 또는 통화 큐를 테스트합니다.

6. Exchange UM 통화 큐 또는 자동 전화 교환에 연결된 전화 번호를 해당 전화 시스템 자동 전화 교환 또는 통화 큐에 다시 할당합니다.  

   이 시점에서 UM Voicemail을 이미 마이그레이션한 경우 Exchange Server 2019로 마이그레이션할 수 있어야 합니다.

## <a name="see-also"></a>참고 항목

[클라우드 통화 큐 만들기](/MicrosoftTeams/create-a-phone-system-call-queue)

[클라우드 자동 전화 교환이란?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[클라우드 자동 전화 교환 설정](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[클라우드 자동 전화 교환 계획](plan-cloud-auto-attendant.md)

[클라우드 통화 큐 계획](plan-call-queue.md)

[온-프레미스 사용자를 위한 클라우드 음성 사서함 서비스 계획](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

Microsoft Teams  - \( [에서 리소스 계정 관리](/MicrosoftTeams/manage-resource-accounts) 온라인으로 홈된 리소스 계정을 만들려면\)