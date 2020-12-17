---
title: 조직에서 전화 시스템 설정
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
description: Microsoft 365 또는 Office 365에서 조직에 대해 전화 시스템(클라우드 PBX)을 설정하는 방법을 자세히 설명하는 단계별 가이드입니다.
ms.openlocfilehash: c00b628716a54adcb19c3dd1f00e8e9e2b6f4c40
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701216"
---
# <a name="set-up-phone-system-in-your-organization"></a>조직에서 전화 시스템 설정

다음은 Microsoft 365 또는 Office 365에서 전화 시스템을 설정하기 위한 단계별 가이드입니다. 자세한 추가 정보에 대한 링크는 각 단계의 끝에서 사용할 수 있습니다.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>1단계: 전화 시스템을 해당 국가 또는 지역에서 사용할 수 있는지 확인

1.    먼저 오디오 회의 및 통화 요금제에 대한 국가 및 지역 가용성으로 이동하고 [페이지](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)맨 위에 있는 목록에서 국가 또는 지역을 선택합니다. 
2.    전화 **시스템 아래에서** 기능 및 세부 정보 목록을 검토합니다. 
3.    전화 시스템을 사용할 수 있는 경우 2단계로 이동하십시오. 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>2단계: 전화 시스템 및 통화 요금제 라이선스 구입 및 할당

단일 사용자에게 전화 시스템 및 통화 요금제 라이선스를 할당하는 단계는 Microsoft 365 또는 Office 365 라이선스를 할당하는 단계와 동일합니다.  여러 사용자에게 라이선스를 일괄 할당할 수도 있습니다. 자세한 내용은 Microsoft Teams 추가 기능 라이선스 [할당을 참조하세요.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

해당 국가 또는 지역에서 통화 요금제가 제공되지 않는 경우 직접 라우팅을 사용하여 전화 시스템에 On-프레미스 전화 통신 인프라를 연결하는 것을 고려합니다.  자세한 내용은 전화 시스템 직접 [라우팅을 참조하세요.](direct-routing-landing-page.md)

## <a name="step-3-get-phone-numbers-for-your-users"></a>3단계: 사용자의 전화 번호 확인

조직에서 전화를 걸고 받을 사용자를 설정하려면 먼저 해당 사용자의 전화 번호를 받아야 합니다.

다음 세 가지 방법으로 사용자에 대한 번호를 사용할 수 있습니다.
- Teams 관리 센터를 사용하여 새 번호를 얻습니다.
- Teams 관리 센터에서 사용할 수 없는 새 번호를 얻습니다.
- 현재 서비스 공급자 또는 통신 사업자에서 Microsoft 365 또는 Office 365로 기존 번호를 포터하거나 이전합니다.

숫자 추가  페이지를 사용하여 해당 번호를 보고, 검색하고, 획득하고, 예약해야 합니다. 국가/지역, 주 및 구/시/별로 검색한 다음 사용자에게 필요한 전화 번호 수를 입력할 수 있습니다.

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>Teams 관리 센터를 사용하여 새 사용자 전화 번호 얻기

1. 직장 또는 학교 계정으로 Microsoft 365에 로그인합니다.

2. Teams 관리 **센터로 이동**
    
3. 왼쪽 탐색에서 음성 **전화** 번호로 이동하고 추가를 클릭한 다음  >  프롬프트를 따르습니다. 
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Teams 관리 센터에서 사용할 수 없는 새 번호 다운로드
  
경우에 따라(국가/지역에 따라) Teams 관리 센터를 사용하여 새 번호를 얻을 수 없는 경우도 있습니다. 이 경우 양식을 다운로드하여 다시 보내야 합니다. 새 사용자 번호를 요청하는 방법에 대한 자세한 내용은 조직의 전화 번호 [관리를 참조합니다.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>서비스 공급자 또는 통신 사업자로부터 전화 번호 포터 또는 전송
  
- 사용자에게 999개 이하의 전화 번호가 필요한 경우  Teams 관리 센터에서 새 로컬 번호 포트 주문 마법사를 사용할 수 있습니다. 전화 번호 전송에 있는 단계를 따라 [Teams로](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 전화 번호를 전송합니다.
    
- 999개가 넘게 전화 번호를 포식해야 하는 경우 조직의 전화 번호 관리를 참조하여 포트 주문 서비스 요청 또는 주문을 제출합니다. [](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 

새 전화 번호를 옮기거나 기존 번호를 이전하는 자세한 내용은 조직의 전화 번호 관리를 [참조하세요.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>4단계: 서비스 전화 번호(오디오 회의, 통화 큐, 자동 전화 회의)

Microsoft 365 또는 Office 365에서 사용자의 전화 번호를 확보하는 것 외에도 오디오 회의(전화 회의용), 자동 전화 회의 및 통화 큐와 같은 서비스에 대한 무료 전화 번호를 검색하고 획득할 수 있습니다. 서비스 전화 번호는 사용자 또는 구독자 전화 번호보다 동시 통화 용량이 더 높습니다. 예를 들어 서비스 번호는 수백 개의 호출을 동시에 처리할 수 있는 반면, 사용자의 전화 번호는 동시에 몇 개의 호출만 처리할 수 있습니다.

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>Teams 관리 센터를 사용하여 새 서비스 번호 얻기


1. 직장 또는 학교 계정으로 로그인합니다.

2. Teams 관리 **센터로 이동하세요.**

3. 왼쪽 탐색 창에서 음성 **전화** 번호 추가 새 번호로 이동한 다음 새 서비스  >    >   **번호를 클릭합니다.**

    > [!IMPORTANT]
    > Teams 관리 센터의 왼쪽 탐색 창에서 음성 옵션을 표시하려면 먼저 하나 이상의 **Enterprise E5**  라이선스, 전화 시스템 추가  기능 라이선스 하나 또는 오디오 회의 추가 기능 라이선스 1개 이상을 구입해야 합니다. 

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Teams 관리 센터에서 사용할 수 없는 새 번호 다운로드
  
경우에 따라(국가/지역에 따라) Teams 관리 센터를 사용하여 새 번호를 얻을 수 없는 경우도 있습니다. 이 경우 양식을 다운로드하여 다시 보내야 합니다. 새 번호를 요청하는 방법에 대한 자세한 내용은 조직의 전화 번호 [관리를 참조합니다.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 

### <a name="port-or-transfer-existing-service-numbers"></a>기존 서비스 번호 포트 또는 전송

현재 서비스 공급자 또는 통신 사업자로부터 서비스 번호를 전송하려는 경우 포트 주문을 Microsoft에 수동으로 제출해야 합니다. LOA(승인서)를 사용하여 전송할 각 서비스 번호 유형(무료 및 무료)에 대해 별도의 포트 주문을 제출해야 합니다. LOA(승인 서신)에서 올바른 서비스 번호를 선택해야 합니다. Microsoft 지원에 문의할 때 서비스 번호(사용자또는 구독자 번호가 아닌)를 전송하도록 지정하거나, 동시 호출 용량이 호출 볼륨을 처리하기에 충분하지 않을 수 있습니다. 전화 번호를 이전하거나 전화 번호로 다른 작업을 하려는 경우 조직의 전화 번호 관리를 [참조합니다.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>5단계: 통화 요금제 설정

위의 단계를 수행한 경우 이미 전화 시스템 및 라이선스 및 통화 요금제(2단계)를 구입하여 할당하고 사용자에 대한 전화 번호를 획득(3단계)했기 때문에 통화 계획이 부분적으로 설정됩니다. 통화 요금제 설정 절차를 완료하기 위해 통화 요금제 설정을 [참조합니다.](set-up-calling-plans.md)


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>6단계: 오디오 회의를 설정하려는 경우

경우에 따라 조직의 사용자가 전화를 사용하여 모임에 전화해야 하는 경우가 있습니다. Microsoft Teams에는 이 상황에 대한 오디오 회의 기능이 포함되어 있습니다. 모바일 장치나 PC에서 Teams 앱을 사용하는 대신 전화를 사용하여 Teams 모임에 참가할 수 있습니다.
오디오 회의를 설정하는 방법에 대한 자세한 내용은 Teams에 대한 오디오 회의 [설정을 참조하세요.](set-up-audio-conferencing-in-teams.md)

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>7단계: 클라우드 호출 큐를 설정하려는 경우

클라우드 통화 큐에는 누군가가 조직의 전화 번호로 전화를 걸 때 사용되는 인사말, 자동으로 통화를 보류할 수 있는 능력, 통화를 대기 중인 사람이 음악을 듣는 동안 통화를 처리하기 위해 사용 가능한 다음 통화 에이전트를 검색하는 기능을 포함합니다. 조직에 대한 단일 또는 여러 호출 큐를 만들 수 있습니다.

호출 큐에 대한 자세한 내용은 클라우드 호출 큐 [만들기를 참조하세요.](create-a-phone-system-call-queue.md)

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>8단계: 클라우드 자동 Attendant를 설정하려는 경우

자동 전화 회의를 통해 조직에 전화를 걸고 메뉴 시스템을 탐색하여 올바른 부서, 통화 큐, 사람 또는 운영자에게 전화를 걸 수 있습니다. Teams 관리 센터를 사용하여 조직에 대한 자동 문의를 만들 수 있습니다.

클라우드 자동 참석자 설정에 대한 자세한 내용은 클라우드 자동 참석자 [설정을 참조하세요.](create-a-phone-system-auto-attendant.md)


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>9단계: 서비스 전화 번호 할당(오디오 회의, 통화 큐, 자동 전화 회의)

위의 **4단계에서** 서비스 번호를 지정한 후 원하는 각 서비스 유형에 할당해야 합니다. 예를 들어 전용 서비스 전화 번호(무료 또는 무료)를 원하는 경우 회의 브리지에 번호를 할당해야 합니다.

- 오디오 회의의 경우 **Teams** 관리 센터 모임 회의 브리지로 연결하여 회의 브리지에 전용 번호를 할당하고 프롬프트를 따를  >    >   수 있습니다.  자세한 내용은 오디오 회의 브리지에서 무료 또는 무료 번호 변경을 [참조하세요.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

- 자동 전화 회의의 경우 **Teams** 관리 센터 음성 자동 전화 회의로 가고 지시에 따라 자동 전화 회의에 전용 번호를  >    >   할당할 수 있습니다.  자세한 내용은 클라우드 자동 [참석자 설정을 참조하세요.](create-a-phone-system-auto-attendant.md)

- 통화 큐의 경우 **Teams** 관리 센터 음성 통화 큐로 가고 프롬프트를 따라 통화 큐에 전용 번호를 할당할  >    >   수 있습니다. 자세한 내용은 클라우드 호출 [큐 만들기를 참조하세요.](create-a-phone-system-call-queue.md)

새 서비스 번호를 받고 기존 서비스 번호를 포식하는 자세한 내용은 서비스 전화 번호 [확인을 참조하세요.](getting-service-phone-numbers.md)

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>10단계: 조직에 대한 통신 크레딧 설정

Microsoft Teams에서 무료 번호를 사용하려면 통신 크레딧을 설정해야 합니다. 모든 대상에 전화를 걸 수 있는 능력이 필요한 통화 요금제(국내 또는 국제) 및 오디오 회의 사용자에 대한 통신 크레딧을 설정하는 것이 좋습니다. 많은 국가/지역이 포함되지만 일부 목적지는 통화 요금제 또는 오디오 회의 구독에 포함되지 않을 수 있습니다. 

통신 크레딧 청구를 설정하고 사용자에게 통신 크레딧  라이선스를 할당하지 않은 경우(해당 국가/지역의 통화 요금제 또는 오디오 회의 계획에 따라) 조직에 대해 몇 분이 소요되는 경우 해당 사용자는 오디오 회의 모임에서 전화를 걸거나 전화를 걸 수 없습니다. 권장 금액을 포함한 자세한 내용은 통신 [크레딧이란?](what-are-communications-credits.md) 및 조직에 대한 통신 크레딧을 설정하는 방법을 [참조하세요.](set-up-communications-credits-for-your-organization.md)
  

## <a name="related-topics"></a>관련 항목
[Microsoft 365 또는 Office 365에서 전화 시스템을 사용할 수 있는 제품](here-s-what-you-get-with-phone-system.md)

[조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 받기](getting-service-phone-numbers.md)

[오디오 회의 및 통화 플랜의 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
