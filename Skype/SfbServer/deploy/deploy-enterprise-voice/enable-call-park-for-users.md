---
title: 비즈니스용 Skype에서 사용자에 게 통화 공원 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 비즈니스용 Skype Server Enterprise Voice에서 통화 공원에 사용자를 설정 합니다.
ms.openlocfilehash: 6642af2a7af698a1127ff2a9bb4e45df73d18c50
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767281"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>비즈니스용 Skype에서 사용자에 게 통화 공원 사용
 
비즈니스용 Skype Server Enterprise Voice에서 통화 공원에 사용자를 설정 합니다.
  
기본적으로 모든 사용자에 대해 통화 대기를 사용할 수 없습니다. 음성 정책에서 통화 대기를 사용할 수 있을 때까지 사용자는 통화를 대기 시 키 지 않거나 파킹 된 통화를 검색 하지 못합니다.
  
전역 범위 또는 사이트 범위 또는 사용자 범위에서 통화 파킹 기능을 사용 하도록 설정할 수 있습니다. 사용자 범위는 사이트 범위 보다 우선 하며 사이트 범위는 전역 범위 보다 우선 합니다. 음성 정책이 여러 개 있는 경우 모든 정책을 검토 하 여 전역 정책만이 아닌 통화 대기 기능을 사용 하도록 설정 하세요.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>비즈니스용 Skype Server 제어판을 사용 하 여 사용자에 게 전화를 걸 수 있도록 설정 하려면

1. **RTCUniversalServerAdmins** 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.
    
4. **음성 정책** 탭을 클릭 합니다.
    
5. 기존 음성 정책을 두 번 클릭 하 여 **음성 정책 편집** 대화 상자를 엽니다.
    
6. **호출 기능**에서 **통화 공원 사용**을 선택 합니다.
    
7. **확인** 을 클릭 하 여 음성 정책 저장
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Cmdlet을 사용 하 여 사용자를 위한 통화 파킹 사용

1. RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 런
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    예를 들어 기본 전역 음성 정책에 대 한 통화 파킹 기능을 사용 하도록 설정 하려면 다음을 수행 합니다.
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>참고 항목



[비즈니스용 Skype에서 음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 구성](voice-policy-and-pstn-usage-records.md)

