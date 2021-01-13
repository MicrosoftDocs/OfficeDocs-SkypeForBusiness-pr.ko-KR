---
title: 비즈니스용 Skype 서버에서 위치 정책 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: 이 항목을 읽고 비즈니스용 Skype 서버 2016에서 E9-1-1(고급 응급 서비스) 위치 정책을 구성하는 Enterprise Voice.
ms.openlocfilehash: 4230d6ac1a820cb9612d58b21a2e5b6ae36d8f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822548"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 위치 정책 만들기

이 항목을 읽고 비즈니스용 Skype 서버 2016에서 E9-1-1(고급 응급 서비스) 위치 정책을 구성하는 Enterprise Voice. 

비즈니스용 Skype 서버는 위치 정책을 사용하여 클라이언트 등록 중에 비즈니스용 Skype 클라이언트가 E9-1-1을 사용할 수 있도록 합니다. 위치 정책에는 E9-1-1 구현 방법을 정의하는 설정이 포함되어 있습니다. 자세한 내용은 비즈니스용 Skype 서버의 위치 [정책 계획을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)

비즈니스용 Skype 제어판 또는 [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet을 사용하여 위치 정책을 정의합니다.

> [!NOTE]
> 비즈니스용 Skype 서버는 이제 클라이언트에 대해 여러 긴급 번호 구성을 지원합니다. 여러 긴급 번호를 구성하려면 비즈니스용 [Skype](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) 서버에서 여러 긴급 번호 계획의 정보를 따르고 비즈니스용 Skype에서 여러 긴급 번호를 [구성해야 합니다.](configure-multiple-emergency-numbers.md) 

전역 위치 정책을 편집하고 태그가 있는 새 위치 정책을 만들 수 있습니다. 클라이언트는 연결된 위치 정책이 있는 서브넷 내에 있지 않은 경우 또는 클라이언트에 위치 정책이 직접 할당되지 않은 경우 전역 정책을 얻습니다. 태그가 지정된 정책은 서브넷 또는 사용자에게 할당됩니다. 

위치 정책을 만들하려면 RTCUniversalServerAdmins 그룹의 구성원인 계정 또는 CsVoiceAdministrator 관리 역할의 구성원 또는 동등한 관리자 권한이 있는 계정을 사용해야 합니다.

자세한 내용은 비즈니스용 Skype 서버의 [위치 정책 계획을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md) 이 절차의 cmdlet은 다음 값을 사용하여 정의된 위치 정책을 사용합니다. cmdlet 매개 변수 및 값에 대한 자세한 내용은 [New-CsLocationPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)


| **요소**                               | **값**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **True** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **고지 사항** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | 회사 정책에 따라 위치를 설정해야 합니다. 위치를 설정하지 않은 경우 응급 서비스에서 응급 서비스를 찾을 수 없습니다. 위치를 설정하세요.  <br/> |
| UseLocationForE911Only  <br/>             | **False** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>위치 정책을 만들 수 있습니다.

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**

    > [!NOTE]
    > **PstnUsage 설정이 PstnUsages의** 전역 목록에 아직 없는 경우 CsLocationPolicy가 실패합니다.

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
