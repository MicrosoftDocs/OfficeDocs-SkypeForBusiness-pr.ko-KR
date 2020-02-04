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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: '조직의 전화 시스템 (클라우드 PBX)을 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 8c2b65bf1a9b209ca64d2a8b915f04cfc9669971
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706883"
---
# <a name="set-up-phone-system-in-your-organization"></a>조직에서 전화 시스템 설정

다음은 Office 365에서 전화 시스템을 설정 하는 단계별 지침입니다. 자세한 정보에 대 한 링크는 각 단계의 마지막에 나와 있습니다.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>1 단계: 전화 시스템을 해당 국가 또는 지역에서 사용할 수 있는지 확인

1.  먼저 [오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)으로 이동 하 고 페이지 위쪽에 있는 목록에서 국가 또는 지역을 선택 합니다. 
2.  **전화 시스템**에서 기능 목록과 세부 정보를 검토 합니다. 
3.  전화 시스템을 사용할 수 있는 경우 2 단계로 이동 합니다. 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>2 단계: 전화 시스템 및 통화 계획 라이선스 구입 및 할당

전화 시스템 및 통화 계획 라이선스를 단일 사용자에 게 할당 하려면 Office 365 라이선스를 할당 하는 것과 같은 단계를 수행 합니다.  라이선스를 여러 사용자에 게 대량으로 배정할 수도 있습니다. 자세한 내용은 [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)을 참조 하세요.

해당 국가나 지역에 대 한 통화 요금제를 사용할 수 없는 경우 직접 라우팅 기능을 사용 하 여 온-프레미스 전화 통신 인프라를 전화 시스템에 연결 하는 것이 좋습니다.  자세한 내용은 [전화 시스템 직접 라우팅을](direct-routing-landing-page.md)참조 하세요.

## <a name="step-3-get-phone-numbers-for-your-users"></a>3 단계: 사용자의 전화 번호 가져오기

전화를 걸고 받을 수 있도록 조직에 사용자를 설정 하려면 먼저 전화 번호를 받아야 합니다.

다음과 같은 세 가지 방법으로 사용자에 대 한 번호를 얻을 수 있습니다.
- 팀 관리 센터를 사용 하 여 새 번호를 받으세요.
- 팀 관리 센터에서 사용할 수 없는 새 번호를 가져옵니다.
- 현재 서비스 공급자 또는 전화 통신 회사의 기존 번호를 Office 365으로 이식 하거나 이전 합니다.

이러한 번호를 보고, 검색 하 고, 가져오고, 예약 하려면 **숫자 추가** 페이지를 사용 해야 합니다. 국가/지역, 시/도, 시/도를 기준으로 검색할 수 있으며, 사용자에 게 필요한 전화 번호 수를 입력 합니다.

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>팀 관리 센터를 사용 하 여 새 사용자 전화 번호 받기

1. 회사 또는 학교 계정으로 Microsoft 365에 로그인 합니다.

2. **팀 관리 센터로**이동 합니다.
    
3. 왼쪽 탐색 창에서 **음성** > **전화 번호로**이동한 다음 **추가**를 클릭 하 고 화면의 지시를 따릅니다.
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>팀 관리 센터에서 사용할 수 없는 새 번호 가져오기
  
때로는 (국가/지역에 따라) 팀 관리 센터를 사용 하 여 새 번호를 받을 수 없습니다. 이 경우 양식을 다운로드 하 여 다시 전송 해야 합니다. 새 사용자 번호를 요청 하는 방법을 알아보려면 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>서비스 공급자 또는 전화 통신 회사의 전화 번호를 이식 하거나 전송 합니다.
  
- 사용자에 게 999 이하의 전화 번호가 필요한 경우 팀 관리 센터에서 **새 로컬 번호 포트 주문** 마법사를 사용할 수 있습니다. 전화 [번호를 팀에 게 전송](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 에 나와 있는 단계를 따라 전화 번호를 전송 합니다.
    
- 999 개 이상의 전화 번호를 이식 해야 하는 경우 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 를 참조 하 여 포트 주문 서비스 요청 또는 주문을 제출할 수 있습니다. 

새 전화 번호를 받고 있거나 기존 번호를 전송 하는 방법에 대 한 자세한 내용은 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>4 단계: 서비스 전화 번호 가져오기 (오디오 회의, 통화 대기열, 자동 전화 교환)

Office 365에서 사용자의 전화 번호를 가져올 수 있을 뿐만 아니라 오디오 회의 (컨퍼런스 브리지), 자동 전화 교환, 통화 대기열 등의 서비스에 대해 유료 또는 유료 전화 번호를 검색 하 고 받을 수도 있습니다. 서비스 전화 번호는 사용자 또는 구독자 전화 번호 보다 높은 동시 통화 용량을가지고 있습니다. 예를 들어 서비스 번호는 여러 개의 통화를 동시에 처리할 수 있지만, 사용자의 전화 번호는 일부 통화를 동시에 처리할 수 있습니다.

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>팀 관리 센터를 사용 하 여 새 서비스 번호 받기


1. 회사 또는 학교 계정으로 Office 365에 로그인 합니다.

2. **팀 관리 센터로**이동 합니다.

3. 왼쪽 탐색 창에서 **음성** > **전화 번호로** > 이동한 다음**새 번호를 추가**하 고 **새 서비스 번호**를 클릭 합니다.

    > [!IMPORTANT]
    > 팀 관리 센터의 왼쪽 탐색 창에서 **음성** 옵션을 보려면 먼저 하나 이상의 **Enterprise E5 라이선스**, 하나의 **전화 시스템** 추가 기능 라이선스 또는 하나의 **오디오 회의** 추가 기능 라이선스를 구입 해야 합니다.

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>팀 관리 센터에서 사용할 수 없는 새 번호 가져오기
  
때로는 (국가/지역에 따라) 팀 관리 센터를 사용 하 여 새 번호를 받을 수 없습니다. 이 경우 양식을 다운로드 하 여 다시 전송 해야 합니다. 새 번호를 요청 하는 방법을 알아보려면 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요. 

### <a name="port-or-transfer-existing-service-numbers"></a>기존 서비스 번호 포트 또는 전송

현재 서비스 공급자 또는 통신 회사에서 서비스 번호를 전송 하려면 Microsoft에 수동으로 포트 순서를 제출 해야 합니다. 각 서비스 번호 유형 (유료 및 무료)에 대해 별도의 포트 주문을 제출 하 여 승인 문자 (LOA)를 사용 하 여 전송 해야 합니다. 인증 문자 (LOA)에서 올바른 서비스 번호 유형을 선택 해야 합니다. Microsoft 지원에 문의 하는 경우*사용자 또는 구독자 번호가 아닌*서비스 번호를 전송 하도록 지정 하거나 동시 통화 용량이 통화 볼륨을 처리 하는 데 충분 하지 않을 수 있습니다. 전화 번호를 전송 하거나 전화 번호를 사용 하 여 다른 작업을 수행 하려는 경우 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>5 단계: 통화 계획을 설정 하려는 경우

위의 단계를 수행한 후에는 이미 전화 시스템 및 라이선스와 통화 요금제 (2 단계)를 구입 하 고 할당 하 고 사용자에 게 확보 한 전화 번호 (3 단계)를 사용 하 여 통화 계획이 부분적으로 설정 되어 있습니다. 통화 계획을 설정 하는 절차를 완료 하려면 [통화 계획](set-up-calling-plans.md)설정을 참조 하세요.


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>6 단계: 오디오 회의를 설정 하려는 경우

조직의 사용자가 모임에 전화를 걸 때 휴대폰을 사용 해야 하는 경우가 있습니다. Microsoft 팀에는 이러한 상황에 대 한 오디오 회의 기능도 포함 되어 있습니다. 사용자는 모바일 장치 또는 PC에서 팀 앱을 사용 하는 대신 휴대폰을 사용 하 여 팀 회의에 통화할 수 있습니다.
오디오 회의를 설정 하는 방법에 대 한 자세한 내용은 [팀에 대 한 오디오 회의 설정을](set-up-audio-conferencing-in-teams.md)참조 하세요.

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>7 단계: 클라우드 통화 큐를 설정 하려면

클라우드 통화 큐에는 사용자가 조직의 전화 번호를 호출할 때 사용 되는 인사말, 통화 대기를 자동으로 전환 하는 기능, 전화를 거는 사용자가 통화를 처리 하기 위해 사용할 수 있는 다음 통화 에이전트 검색 기능 등이 포함 됩니다. 대기 중인 음악 듣기. 조직에 대 한 단일 또는 복수 통화 대기열을 만들 수 있습니다.

통화 대기열에 대 한 자세한 내용은 [클라우드 통화 대기열 만들기](create-a-phone-system-call-queue.md)를 참조 하세요.

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>8 단계: 클라우드 자동 전화 교환을 설정 하려면

자동 전화 교환을 통해 조직에 전화를 걸고 메뉴 시스템을 탐색 하 여 올바른 부서, 통화 대기열, 사람, 교환원에 게 얻을 수 있습니다. 비즈니스용 Skype 관리 센터를 사용 하 여 조직의 자동 전화 교환을 만들 수 있습니다.

클라우드 자동 전화 교환 설정에 대 한 자세한 내용은 [클라우드 자동 전화 교환을 설정](create-a-phone-system-auto-attendant.md)attendendant을 참조 하세요.


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>9 단계: 서비스 전화 번호 지정 (오디오 회의, 통화 대기열, 자동 전화 교환)

**위의 4 단계**에서 서비스 번호를 찾았으면 원하는 각 서비스 유형에 할당 해야 합니다. 예를 들어 유료 또는 무료 서비스 전화 번호를 원할 경우 회의 브리지에 해당 번호를 할당 해야 합니다.

- 오디오 회의의 경우 **팀 관리 센터** > **모임** > 발송 브리지로 연결 하 고 화면의 지시에 따라**전화** 회의 브리지에 전용 번호를 할당할 수 있습니다.  자세한 내용은 [오디오 회의 브리지의 유료 또는 무료 전화 번호 변경을](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)참조 하세요.

- 자동 전화 교환의 경우 **팀 관리 센터** > **음성** > **자동 전화 교환** 으로 이동 하 여 메시지에 따라 전용 번호를 자동 전화 교환에 할당할 수 있습니다.  자세한 내용은 [클라우드 자동 전화 교환 설정을](create-a-phone-system-auto-attendant.md)참조 하세요.

- 통화 대기열의 경우 **팀 관리 센터** > **음성** > **통화 전담팀** 으로 이동 하 여 메시지에 따라 전용 번호를 통화 대기열에 할당할 수 있습니다. 자세한 내용은 [클라우드 통화 대기열 만들기](create-a-phone-system-call-queue.md)를 참조 하세요.

새 서비스 번호를 받고 기존 서비스 번호를 포팅 하는 방법에 대 한 자세한 내용은 [서비스 전화 번호 가져오기를](getting-service-phone-numbers.md)참조 하세요.

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>10 단계: 조직의 통신 크레딧을 설정

Microsoft 팀에 무료 전화 번호를 사용 하려면 통신 크레딧을 설정 해야 합니다. 통화 요금제 (국내 또는 국제) 및 오디오 회의 사용자에 게 통신 크레딧을 설정 하 고 대상에 게 전화를 걸 수 있는 기능이 필요한 경우에 권장 합니다. 여러 국가/지역이 포함 되어 있지만 일부 대상은 통화 요금제 또는 오디오 회의 구독에 포함 되지 않을 수 있습니다. 

통신 크레딧 청구를 설정 하지 않고 사용자에 게 **통신 크레딧** 라이선스를 할당 하지 않으면 해당 국가/지역의 통화 요금제 또는 오디오 회의 요금제에 따라 해당 사용자가 오디오 회의 모임에서 통화 하거나 전화를 걸 수 없습니다. 권장 자금 액수를 포함 하 여 자세한 내용은 [통신 크레딧을 소개](what-are-communications-credits.md) 하 고 [조직의 통신 크레딧을 설정](set-up-communications-credits-for-your-organization.md)하세요.
  

## <a name="related-topics"></a>관련 주제
[Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능](here-s-what-you-get-with-phone-system.md)

[조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 가져오기](getting-service-phone-numbers.md)

[오디오 회의 및 통화 요금제 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
