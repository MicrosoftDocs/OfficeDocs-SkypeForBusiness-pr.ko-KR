---
title: 2016에서 위치 정책 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: 이 항목을 통해 E9-1-1(Enhanced Emergency Service) 위치 정책을 구성하는 방법을 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: d601fddcb66fd5b963ab24caf3a7289a2188628b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594742"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>2016에서 위치 정책 비즈니스용 Skype 서버

이 항목을 통해 E9-1-1(Enhanced Emergency Service) 위치 정책을 구성하는 방법을 비즈니스용 Skype 서버 Enterprise Voice. 

비즈니스용 Skype 서버 등록하는 동안 위치 정책을 사용하여 비즈니스용 Skype 클라이언트에서 E9-1-1을 사용하도록 설정할 수 있습니다. 위치 정책에는 E9-1-1을 구현하는 방법을 정의하는 설정이 포함되어 있습니다. 자세한 내용은 [Plan location policies for 비즈니스용 Skype 서버.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)

위치 정책은 비즈니스용 Skype [또는 New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet을 사용하여 정의합니다.

> [!NOTE]
> 비즈니스용 Skype 서버 클라이언트에 대해 여러 긴급 번호 구성을 지원할 수 있습니다. 여러 긴급 번호를 구성하려면 에서 여러 긴급 [](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) 번호 계획 및 에서 여러 긴급 비즈니스용 Skype 서버 구성의 정보를 따라야 [비즈니스용 Skype.](configure-multiple-emergency-numbers.md) 

전역 위치 정책을 편집하고 태그가 지정한 새 위치 정책을 만들 수 있습니다. 클라이언트는 연결된 위치 정책이 있는 서브넷 내에 있지 않은 경우 또는 클라이언트에 위치 정책이 직접 할당되지 않은 경우 전역 정책을 얻습니다. 태그가 지정된 정책은 서브넷 또는 사용자에게 할당됩니다. 

위치 정책을 만들하려면 RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator 관리 역할의 구성원 또는 동등한 관리자 권한 및 사용 권한이 있는 계정을 사용해야 합니다.

자세한 내용은 [Plan location policies for 비즈니스용 Skype 서버.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md) 이 절차의 cmdlet은 다음 값을 사용하여 정의된 위치 정책을 사용합니다. cmdlet 매개 변수 및 값에 대한 자세한 내용은 [New-CsLocationPolicy를 참조하세요.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)


| **요소**                               | **값**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **True** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **고지 사항** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | 회사 정책을 사용하려면 위치를 설정해야 합니다. 위치를 설정하지 않은 경우 응급 서비스가 긴급 상황 시 위치를 찾을 수 없습니다. 위치를 설정하세요.  <br/> |
| UseLocationForE911Only  <br/>             | **거짓** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>위치 정책을 만들 수 있습니다.

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

    > [!NOTE]
    > **PstnUsage의 설정이 PstnUsages의** 전역 목록에 없는 경우 CsLocationPolicy가 실패합니다.

2. 선택적으로 다음 cmdlet을 실행하여 전역 위치 정책을 편집합니다.

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. 다음을 실행하여 태그가 지정된 위치 정책을 만들 수 있습니다.

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. 다음 cmdlet을 실행하여 3단계에서 만든 태그가 지정한 위치 정책을 사용자 정책에 적용합니다.

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```