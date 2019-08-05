---
title: 비즈니스용 Skype 서버의 DTMF 명령에 대 한 키 매핑 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: '요약: 비즈니스용 Skype 서버에서 DTMF 멀티 주파수) 명령의 키 매핑을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 713c72941a8cc147b751c82b9dbbfbc2c2d16837
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189654"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 DTMF 명령에 대 한 키 매핑 관리
 
**요약:** 비즈니스용 Skype 서버의 DTMF (듀얼 톤 다중 주파수) 명령의 키 매핑을 관리 하는 방법에 대해 알아봅니다.
  
전화 접속 회의 사용자는 전화 키패드의 키를 눌러 이중 톤 다중 주파수 (DTMF) 명령을 수행할 수 있습니다. DTMF 명령을 사용 하면 전화 회의에 전화를 거는 사용자가 전화기에서 키패드를 사용 하 여 전화를 걸고 음소거 해제 하거나, 전화를 잠그거나 잠금 취소 하는 등의 회의 설정을 제어할 수 있습니다. 
  
DTMF 명령에 사용 되는 키를 관리 하려면 비즈니스용 Skype 서버 관리 셸을 사용 하 여 **CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**및 ** 새로운 CsDialinConferencingDtmfConfiguration** cmdlet.
  
사이트에 대 한 새 DTMF 설정을 만들면 사이트 설정이 전역 설정 보다 우선적으로 적용 됩니다. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>DTMF 명령의 키 매핑 관리

1. RTCUniversalServerAdmins 그룹의 구성원 또는 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 전화 접속 회의에 사용 되는 DTMF 설정을 보려면 명령 프롬프트에서 다음 명령을 실행 합니다.
    
   ```
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. 전화 접속 회의에 사용 되는 DTMF 설정을 수정 하려면 다음 cmdlet을 실행 하 고 변경 하려는 각 옵션에 대해 누를 키를 지정 합니다.
    
   ```
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. ) 특정 사이트에 대 한 추가 DTMF 명령 집합을 만들려면 사이트 id와 함께 **CsDialinConferencingDtmfConfiguration** cmdlet을 사용 합니다.
    
다음 예에서는 알림을 사용 하거나 사용 하지 않도록 누른 키와 모든 참가자를 음소거 및 음소거 해제 하기 위해 누른 키를 바꿉니다. Id가 지정 되지 않았으므로 이러한 변경 내용은 전역 DTMF 설정에 적용 됩니다.
  
```
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

자세한 내용은 [get-help, CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)및 [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)을 참조 하세요.
  

