---
title: 비즈니스용 Skype에 대 한 오디오 회의 설정
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
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '휴대폰을 사용 하 여 전화 회의에 참가 해야 하는 사용자에 대해 전화 접속 또는 오디오 회의를 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 499a8a8ef05d23c74b030536d33b7a02cd6d9a1a
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2019
ms.locfileid: "37924979"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>비즈니스용 Skype에 대 한 오디오 회의 설정

조직의 사용자가 모임에 전화를 걸 때 휴대폰을 사용 해야 하는 경우가 있습니다. 비즈니스용 Skype에는 이러한 상황에 대 한 오디오 회의 기능이 포함 되어 있습니다. 모바일 장치 또는 PC에서 비즈니스용 Skype 앱을 사용 하는 대신 휴대폰을 사용 하 여 비즈니스용 Skype 모임으로 전화를 걸 수 있습니다. 
  
모임 일정을 계획하거나 주도하는 사용자들을 위해 오디오 회의를 설정하기만 하면 됩니다. 전화를 걸 수 있는 모임 참석자는 해당 사용자 또는 다른 설정에 할당 된 라이선스가 필요 하지 않습니다.
  
오디오 회의에 대 한 질문과 대답은 [오디오 회의 일반적인 질문](/MicrosoftTeams/audio-conferencing-common-questions)을 참조 하세요.

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>1 단계: 자신의 국가/지역에서 음성 회의를 사용할 수 있는지 확인
<a name="__top"> </a>

오디오 회의 [및 통화 요금제에 대 한 국가 및 지역](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) 으로 이동 하 고, 전화 시스템, 통화 요금제, 유료 및 무료 번호, 통신 크레딧에 대 한 정보를 비롯 하 여 오디오 회의에 대 한 가용성 정보를 얻을 국가 또는 지역을 선택 합니다. 
 
## <a name="step-2-get-and-assign-licenses"></a>2 단계: 라이선스 가져오기 및 할당
 
1. 오디오 회의의 경우 전화 접속 모임을 설정 하는 각 사용자에 대 한 라이선스가 필요 합니다. 오디오 회의를 위해 구입 해야 하는 라이선스와 비용의 소모량을 알아보려면 비즈니스용 [Skype 추가 기능 라이선스](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)를 참조 하세요.

    >[!NOTE] 
    > 오디오 회의는 Office 365 Enterprise E5 라이선스에 포함 되어 있으며 추가 기능으로 제공 됩니다.
        
2. 오디오 회의 라이선스를 구입한 후에는 모임을 예약 하거나 진행 하는 조직의 사용자에 게 할당 해야 합니다. 조직에서 일정을 예약 하거나 잠재 고객으로 진행 하는 사용자에 게 구매한 [비즈니스용 Office 365에 대 한 라이선스 할당 또는 제거](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) 를 참조 하세요.
    
3. 또한 이전 단계에서 라이선스를 할당 한 동일한 사람에 게 통신 크레딧 라이선스 (아무런 비용 없음)를 할당 하는 것이 좋습니다. 통신 크레딧을 설정 하는 방법에 [대 한 자세한 내용은 조직의 통신 크레딧 설정을](/microsoftteams/set-up-communications-credits-for-your-organization)참조 하세요.
    
> [!NOTE]
> [분당 유료 오디오 회의](/microsoftteams/audio-conferencing-pay-per-minute)를 설정할 수도 있습니다.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>3 단계: 회의 브리지에 대 한 서비스 번호 가져오기
<a name="__top"> </a>

오디오 회의의 경우 사용자에 게 전화 번호를 사용할 수 없습니다. 서비스 번호를 구해야 할 것입니다. 회의 브리지에 대해 유료 또는 무료 서비스 번호를 받을 수 있습니다. 다음과 같은 세 가지 방법으로 유료 및 무료 서비스 번호를 받을 수 있습니다. 
  
- **비즈니스용 Skype 관리 센터를 사용**합니다. 일부 국가/지역의 경우 비즈니스용 Skype 관리 센터를 사용 하 여 회의 브리지의 서비스 번호를 얻을 수 있습니다. [서비스 전화 번호 가져오기를](/microsoftteams/getting-service-phone-numbers)참조 하세요.
    
- **기존 서비스 번호를 이식**합니다. 현재 서비스 공급자 또는 전화 통신 회사의 기존 번호를 Office 365으로 이식 하거나 이전 합니다. 이 작업을 수행 하는 데 도움이 되는 자세한 내용은 [팀에 전화 번호 전송](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 또는 [조직에 대 한 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization) 를 참고 하세요.  
  
- **새 번호에 요청 양식을 사용**합니다. 때로는 (국가/지역에 따라) 비즈니스용 Skype 관리 센터를 사용 하 여 새 서비스 번호를 받을 수 없거나, 특정 전화 번호 또는 지역 코드가 필요 합니다. 그렇다면 양식을 다운로드 하 여 다시 전송 해야 합니다. 자세한 내용은 [조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization) 를 참조 하세요. 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>4 단계: 회의 브리지에 서비스 번호 할당
<a name="__top"> </a>

회의 브리지에 대해 유료 및/또는 무료 전화 번호를 받은 후에는 모임 초대에 사용할 수 있도록 번호를 할당 해야 합니다.  

오디오 회의 브리지에 새 전화 번호를 지정 하려면 다음을 수행 합니다.

![비즈니스용 skype](../images/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘:

 1. **Microsoft 365 관리 센터** > **관리** > 센터**팀** > **레거시 포털로**이동 합니다.
 2. **음성** > **전화 번호**를 선택 합니다.
 3. 전화 번호를 선택 하 고 **할당**을 클릭 합니다.

자세한 내용은 [오디오 회의 브리지에서 전화 번호 변경을](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)참조 하세요.

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>5 단계: 회의 브리지의 기본 및 대체 언어 설정
<a name="__top"> </a>

다음으로, 오디오 [회의에 대 한 자동 전화 교환 언어를 설정](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) 하 여 회의 자동 전화 교환에서 음성 회의에 대 한 전화 번호로 전화를 걸 때 발신자를 인사 합니다. 

![Microsoft](../images/teams-logo-30x30.png) **팀 관리 센터를 사용 하 여**microsoft 팀 로고를 표시 하는 아이콘:

1. 대시보드에서 **모임** > **회의 브리지로**이동 합니다.
2. 회의 브리지 전화 번호를 선택 하 고 **편집**을 클릭 한 다음 기본 언어를 선택 합니다.

![비즈니스용 skype](../images/sfb-logo-30x30.png) **관리 센터를 사용 하 여**비즈니스용 skype 로고를 표시 하는 아이콘:

1. 관리 센터 > **관리자** > 센터**팀** > **레거시 포털로**이동 합니다.
2. **오디오 회의** > **Microsoft bridge**를 선택 합니다. 
3. 회의 브리지 전화 번호를 선택 하 고 **언어 설정을**선택한 다음 기본 언어를 선택 합니다.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>6 단계: 회의 브리지 설정 설정
<a name="__top"> </a>
    
회의 브리지를 설정한 후에는 입력/종료 알림과 PIN 길이 등의 기본 설정이 사용할 것인지 확인 합니다. 그렇지 않은 경우 변경할 수 있습니다. 

![Microsoft](../images/teams-logo-30x30.png) **팀 관리 센터를 사용 하 여**microsoft 팀 로고를 표시 하는 아이콘:

1. 대시보드에서 **모임** > **회의 브리지로**이동 합니다.
2. **브리지 설정을**선택 합니다. 이렇게 하면 **브리지 설정** 창이 열립니다. 

자세한 내용은 [오디오 회의 브리지에 대 한 설정 변경을](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)참조 하세요.

![비즈니스용 skype](../images/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘:

1. **Microsoft 365 관리 센터** > **관리** > 센터**팀** > **레거시 포털로**이동 합니다.
2. **오디오 회의** > **Microsoft bridge 설정을**선택 합니다. **Microsoft bridge 설정** 페이지를 엽니다. 

자세한 내용은 [오디오 회의 브리지에 대 한 설정 변경을](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)참조 하세요.

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>7 단계: 모임 리더 사용자를 위한 전화 접속 전화 번호 지정

오디오 회의 브리지를 만든 후에는 사용자의 유료 및 무료 전화 번호를 설정 해야 합니다.

모임에 참가 하거나 일정을 예약 하는 조직의 모든 사용자에 대해이 작업을 수행 해야 합니다. 

![Microsoft](../images/teams-logo-30x30.png) **팀 관리 센터를 사용 하 여**microsoft 팀 로고를 표시 하는 아이콘:

1. 대시보드에서 **사용자**를 클릭 하 고 목록에서 사용자를 선택한 다음 **편집**을 선택 합니다.
2. **오디오 회의**옆에 있는 **편집** 을 선택 하 고 **오디오 회의** 창의 **유료 번호** 및 무료 번호 목록 **에서 번호를** 선택 합니다.

![비즈니스용 skype](../images/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘:

1. **Microsoft 365 관리 센터** > **팀** > **레거시 포털로**이동 합니다.
2. **오디오 회의** > **사용자**를 선택한 다음 목록에서 사용자를 선택 하 고 **편집**을 클릭 합니다. 

자세한 내용은 [Microsoft를 오디오 회의 공급자로 지정](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)을 참조 하세요.


## <a name="step-8-set-up-meeting-invitations-optional"></a>8 단계: 모임 초대 설정 (선택 사항)
<a name="__top"> </a>
 
사용자에 대해 설정 된 전화 접속 번호가 모임 참석자에 게 전송 되는 모임 초대에 자동으로 추가 됩니다. 그러나 원하는 경우 자신만의 도움말 및 법률 링크, 문자 메시지, 작은 회사 그래픽을 추가할 수 있습니다. [모임 초대 사용자 지정](../set-up-skype-for-business-online/customize-meeting-invitations.md)을 참조 하세요.
   
## <a name="related-topics"></a>관련 항목

[오디오 회의 일반적인 질문](/MicrosoftTeams/audio-conferencing-common-questions)
  
[비즈니스용 Skype 온라인 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[오디오 회의의 전화 번호](phone-numbers-for-audio-conferencing.md)
  
[온라인 모임 및 컨퍼런스 통화에 대 한 옵션 설정](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
