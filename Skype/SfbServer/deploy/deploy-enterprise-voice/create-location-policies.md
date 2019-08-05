---
title: 비즈니스용 Skype 서버에서 위치 정책 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: 비즈니스용 Skype Server Enterprise Voice에서 향상 된 응급 서비스 (E9-1-1) 위치 정책을 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: e3e98394b660174eeb58b259de0121196934ad3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190470"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 위치 정책 만들기

비즈니스용 Skype Server Enterprise Voice에서 향상 된 응급 서비스 (E9-1-1) 위치 정책을 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요. 

비즈니스용 skype Server는 위치 정책을 사용 하 여 E9에서 비즈니스용 Skype 클라이언트를 사용 하도록 설정 합니다 (클라이언트 등록 중-1-1). 위치 정책에는 E9-1-1이 구현 되는 방법을 정의 하는 설정이 포함 되어 있습니다. 자세한 내용은 [비즈니스용 Skype 서버용 계획 위치 정책을](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)참조 하세요.

Skype for 비즈니스용 제어판을 사용 하거나 [새-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet을 사용 하 여 위치 정책을 정의 합니다.

> [!NOTE]
> 비즈니스용 Skype 서버는 이제 클라이언트에 대 한 여러 응급 번호 구성을 지원 합니다. 여러 비상 번호를 구성 하려는 경우 비즈니스용 [Skype 서버에서 여러 응급 번호 계획](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) 의 정보를 따르고 [비즈니스용 skype에서 여러 응급 번호를 구성](configure-multiple-emergency-numbers.md)해야 합니다. 

전역 위치 정책을 편집 하 고 태그가 지정 된 새 위치 정책을 만들 수 있습니다. 클라이언트는 연결 된 위치 정책을 사용 하 여 서브넷 내에 있지 않거나 클라이언트에 위치 정책이 직접 할당 되지 않은 경우 전역 정책을 가져옵니다. 태그가 지정 된 정책은 서브넷 또는 사용자에 게 할당 됩니다. 

위치 정책을 만들려면 RTCUniversalServerAdmins 그룹의 구성원 이거나 CsVoiceAdministrator 관리 역할의 구성원 이거나 해당 관리자 권한 및 사용 권한이 있는 계정을 사용 해야 합니다.

자세한 내용은 [비즈니스용 Skype 서버용 계획 위치 정책을](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)참조 하세요. 이 절차의 cmdlet에서는 다음 값을 사용 하 여 정의 된 위치 정책을 사용 합니다. Cmdlet 매개 변수 및 값에 대 한 자세한 내용은 [신규-CsLocationPolicy 정책을](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)참조 하세요.


| **요소**                               | **값**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **False** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **고 지 사항** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | 회사 정책에 따라 위치를 설정 해야 합니다. 위치를 설정 하지 않으면 비상 서비스는 비상 시 사용자를 찾을 수 없게 됩니다. 위치를 설정 하십시오.  <br/> |
| UseLocationForE911Only  <br/>             | **해제** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>위치 정책 만들기

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

    > [!NOTE]
    > **PstnUsage** 에 대 한 설정이 PstnUsages의 전역 목록에 없으면 CsLocationPolicy가 실패 합니다.

2. 필요에 따라 다음 cmdlet을 실행 하 여 전역 위치 정책을 편집 합니다.

   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. 다음을 실행 하 여 태그가 지정 된 위치 정책을 만듭니다.

   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. 3 단계에서 만든 태그가 지정 된 위치 정책을 사용자 정책에 적용 하려면 다음 cmdlet을 실행 합니다.

   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
