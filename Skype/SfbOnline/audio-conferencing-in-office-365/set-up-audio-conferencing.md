---
title: 오디오 회의 설정 비즈니스용 Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: '전화를 사용하여 전화 회의에 참여해야 하는 회사의 사용자를 위해 전화 접속 또는 오디오 회의를 설정하는 방법을 알아봅니다. '
ms.openlocfilehash: 55edb015df6e0faf77eb644246677f637b7bace7
ms.sourcegitcommit: cf2f96dbd485ac4cc822c5a591ccce6b47f12cc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2021
ms.locfileid: "59456558"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>오디오 회의 설정 비즈니스용 Skype

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

경우에 따라 조직의 사용자가 전화를 사용하여 모임에 전화해야 하는 경우가 있습니다. 비즈니스용 Skype 상황에 대한 오디오 회의 기능이 포함되어 있습니다. 모바일 디바이스 또는 PC에서 비즈니스용 Skype 앱을 사용하는 대신 휴대폰을 사용하여 비즈니스용 Skype 모임에 전화를 걸 수 있습니다. 
  
모임 일정을 계획하거나 주도하는 사용자들을 위해 오디오 회의를 설정하기만 하면 됩니다. 전화를 거는 모임 참석자는 자신에게 할당된 라이선스 혹은 그 외 설정이 필요하지 않습니다.
  
오디오 회의에 대한 질문과 대답을 확인하려면 [오디오 회의에 대한 일반적인 질문](/MicrosoftTeams/audio-conferencing-common-questions)을 참조하세요.

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>1단계: 사용자의 국가/지역에서 오디오 회의를 사용할 수 있는지 확인하기
<a name="__top"> </a>

[오디오 회의 및 통화 플랜의 국가 및 지역 가용성](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)으로 이동하고 해당 국가나 지역을 선택하여 전화 시스템, 통화 플랜, 유료 및 무료 전화번호, 통신 크레딧에 대한 정보뿐만 아니라 오디오 회의에 대한 가용성 정보를 얻을 수 있습니다. 
 
## <a name="step-2-get-and-assign-licenses"></a>2단계: 라이선스 받기 및 할당하기
 
1. 오디오 회의를 위해서는 전화 접속 모임을 설정할 각 사용자에 대한 라이선스가 필요합니다. 오디오 회의를 위해 구입해야 하는 라이선스와 비용에 대한 자세한 내용은 추가 비즈니스용 Skype 라이선스 를 [참조합니다.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

    >[!NOTE] 
    > 오디오 회의는 Office 365 Enterprise E5 라이선스에 추가 기능으로 포함되어 있습니다.
        
2. 오디오 회의 라이선스를 구입한 후에는 모임을 예약하거나 진행할 조직의 사용자에게 라이선스를 할당해야 합니다. [모임을](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) 예약하거나 이끌 조직의 비즈니스용 Microsoft 365 앱 사용자에 대한 라이선스 할당 또는 제거를 참조합니다.
    
3. 또한 이전 단계에서 라이선스를 할당한 동일한 사용자에게 통신 크레딧 라이선스(비용 없음)를 할당하는 것이 좋습니다. 통신 크레딧을 설정하는 방법을 확인하려면 [조직에 대한 통신 크레딧 설정하기](/microsoftteams/set-up-communications-credits-for-your-organization)를 참조하세요.
    
   > [!NOTE]
   > [오디오 회의(분 단위 요금)](/microsoftteams/audio-conferencing-pay-per-minute)를 설정할 수도 있습니다.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>3단계: 회의 브리지에 대한 서비스 전화번호 받기
<a name="__top"> </a>

오디오 회의의 경우 사용자의 전화번호를 사용할 수 없습니다. 서비스 전화번호를 받아야 합니다. 회의 브리지에 대한 유료 또는 무료 서비스 전화번호를 받을 수 있습니다. 유료 및 무료 서비스 전화번호를 받는 방법에는 세 가지가 있습니다. 
  
- **관리 비즈니스용 Skype 을 사용하세요.** 일부 국가/지역의 경우 관리 센터를 사용하여 회의 브리지에 대한 서비스 비즈니스용 Skype 수 있습니다. [서비스 전화번호 받기](/microsoftteams/getting-service-phone-numbers)를 참조하세요.
    
- **기존 서비스 전화번호 포팅하기** 현재 서비스 공급자 또는 휴대폰 통신사에서 기존 번호를 Microsoft 365 또는 Office 365. 이 작업을 수행 하는 데 도움이 되는 자세한 내용은 [Teams로 전화번호 전송](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 또는 [조직에 대한 전화번호 관리하기](/microsoftteams/manage-phone-numbers-for-your-organization)를 참조하세요.  
  
- **새 전화 번호를 위한 요청 양식 사용하기** 경우에 따라(국가/지역에 따라) 관리 센터를 사용하여 새 서비스 번호를 비즈니스용 Skype 수 없습니다. 또는 특정 전화 번호 또는 지역 코드가 필요합니다. 그럴 경우 양식을 다운로드하여 다시 보내주세요. 자세한 내용은 [조직에서 전화번호 관리하기](/microsoftteams/manage-phone-numbers-for-your-organization)를 참조하세요. 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>4단계: 회의 브리지에 서비스 전화번호 할당하기
<a name="__top"> </a>

회의 브리지에 대한 유료 및/또는 무료 전화번호를 받으면 모임 초대에 사용할 수 있도록 번호를 할당해야 합니다.  

오디오 회의 브리지에 새 전화 번호를 할당하는 경우:

![로고가 비즈니스용 Skype 아이콘입니다.](../images/sfb-logo-30x30.png) **관리 비즈니스용 Skype 사용:**

 1. **Microsoft 365 관리 센터** > **관리 센터** > **Teams** > **레거시 포털** 로 이동합니다.
 2. **음성** > **전화번호** 를 선택합니다.
 3. 전화번호를 선택하고, **할당** 을 클릭합니다.

자세한 내용은 오디오 회의 브리지의 전화 번호 [변경을 참조합니다.](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>5단계: 회의 브리지의 기본 및 대체 언어 설정하기
<a name="__top"> </a>

다음으로, 회의 [](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) 자동 참석자가 오디오 회의를 위해 전화 번호로 전화 접속할 때 전화를 걸 때 회의 자동 참석자가 사용하는 자동 참석 언어를 설정합니다. 

![로고가 Microsoft Teams 아이콘입니다.](../images/teams-logo-30x30.png) **관리 Microsoft Teams 사용:**

1. 집에서 모임 **회의** 브리지로  >  **이동합니다.**
2. 회의 브리지 전화번호를 선택하고 **편집** 을 클릭한 다음 기본 언어를 선택합니다.

![로고가 비즈니스용 Skype 아이콘입니다.](../images/sfb-logo-30x30.png) **관리 비즈니스용 Skype 사용:**

1. 관리 센터 > **관리** 센터 Teams  >    >  **로 이동하세요.**
2. 오디오 회의 Microsoft   >  **브리지를 선택합니다.** 
3. 회의 브리지 전화 번호를 선택하고 언어 설정을 **선택한** 다음 기본 언어를 선택합니다.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>6단계: 회의 브리지 설정 확인하기
<a name="__top"> </a>
    
회의 브리지를 설정한 후에는 입력/종료 알림과 PIN 길이와 같은 기본 설정이 사용하려는 설정인지 확인합니다. 사용하려는 설정이 아니라면 설정을 변경할 수 있습니다. 

![로고가 Microsoft Teams 아이콘입니다.](../images/teams-logo-30x30.png) **관리 Microsoft Teams 사용:**

1. 집에서 모임 **회의** 브리지로  >  **이동합니다.**
2. **브리지 설정** 을 선택합니다. 그러면 **브리지 설정** 창이 열립니다. 

자세한 내용은 [오디오 회의 브리지의 설정 변경하기](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)를 참조하세요.

![로고가 비즈니스용 Skype 아이콘입니다.](../images/sfb-logo-30x30.png) **관리 비즈니스용 Skype 사용:**

1. **Microsoft 365 관리 센터** > **관리 센터** > **Teams** > **레거시 포털** 로 이동합니다.
2. 오디오 **회의** Microsoft 브리지 설정을  >  **선택합니다.** 그러면 Microsoft 브리지 **설정 페이지가 열립니다.** 

자세한 내용은 [오디오 회의 브리지의 설정 변경하기](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)를 참조하세요.

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>7단계: 모임을 진행하는 사용자에게 전화 접속 번호 할당하기

오디오 회의 브리지를 만든 후에는 사용자를 위해 유료 및 무료 전화번호를 설정해야 합니다.

모임을 진행하거나 예약하는 조직의 모든 사용자를 위해 이 작업을 수행해야 합니다. 

![로고가 Microsoft Teams 아이콘입니다.](../images/teams-logo-30x30.png) **관리 Microsoft Teams 사용:**

1. 홈에서 **사용자**, 목록에서 사용자를 선택하고 **편집을 선택합니다.**
2. **오디오 회의** 옆의 **편집** 을 선택한 다음 **오디오 회의** 창에서 **유료 전화번호** 및 **무료** 전화번호 목록에서 번호를 선택합니다.

![로고가 비즈니스용 Skype 아이콘입니다.](../images/sfb-logo-30x30.png) **관리 비즈니스용 Skype 사용:**

1. 레거시 **Microsoft 365 관리 센터** Teams  >    >  **로 이동합니다.**
2. 오디오 **회의** 사용자를 선택한 다음 목록에서 사용자를 선택하고  >   **편집을 클릭합니다.** 

자세한 내용은 [Microsoft를 오디오 회의 공급자로 지정하기](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)를 참조하세요.


## <a name="step-8-set-up-meeting-invitations-optional"></a>8단계: 모임 초대 설정하기(선택 사항)
<a name="__top"> </a>
 
사용자에게 설정되는 전화 접속 번호는 모임 참석자에게 보내지는 모임 초대에 자동으로 추가됩니다. 그러나 원하는 경우 자체 도움말 및 법적인 링크, 문자 메시지 및 작은 회사 그래픽을 추가할 수 있습니다. [모임 초대 사용자 지정하기](../set-up-skype-for-business-online/customize-meeting-invitations.md)를 참조하세요.
   
## <a name="related-topics"></a>관련 항목

[오디오 회의 일반적인 질문](/MicrosoftTeams/audio-conferencing-common-questions)
  
[비즈니스용 Skype 온라인 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[오디오 회의의 전화 번호](phone-numbers-for-audio-conferencing.md)
  
[온라인 모임 및 전화 회의에 대한 옵션 설정하기](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
