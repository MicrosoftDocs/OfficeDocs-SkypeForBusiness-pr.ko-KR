---
title: 비즈니스용 Skype 서버에서 DTMF 명령에 대한 키 매핑 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: '요약: 비즈니스용 Skype 서버에서 DTMF(Dual-Tone Multi-Frequency) 명령의 키 매핑을 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: b804c9a0923630f6de3d1b5af2acdda123cc6331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828098"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 DTMF 명령에 대한 키 매핑 관리
 
**요약:** 비즈니스용 Skype 서버에서 DTMF(Dual-Tone Multi-Frequency) 명령의 키 매핑을 관리하는 방법을 학습합니다.
  
전화 접속 회의 사용자는 전화기 키패드의 키를 눌러 DTMF(Dual-tone Multi-frequency) 명령을 수행할 수 있습니다. DTMF 명령을 사용하면 회의에 전화 접속한 사용자가 전화기의 키패드를 사용하여 음소거 설정 및 해제 또는 회의 잠금 설정 및 해제와 같은 회의 설정을 제어할 수 있습니다. 
  
DTMF 명령에 사용되는 키를 관리하기 위해 **Get-CsDialinConferencingDtmfConfiguration,** **Set-CsDialinConferencingDtmfConfiguration** 및 **New-CsDialinConferencingDtmfConfiguration** cmdlet과 함께 비즈니스용 Skype 서버 관리 셸을 사용하세요.
  
사이트에 대해 새 DTMF 설정을 만들면 이 사이트 설정이 전역 설정보다 우선합니다. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>DTMF 명령의 키 매핑 관리

1. RTCUniversalServerAdmins 그룹의 구성원이나 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
3. 전화 접속 회의에 사용되는 DTMF 설정을 표시하려면 명령 프롬프트에서 다음 명령을 실행합니다.
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. 전화 접속 회의에 사용되는 DTMF 설정을 수정하려면 다음 cmdlet을 실행하고 변경할 각 옵션에 대해 누를 키를 지정합니다.
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (선택 사항) 특정 사이트에 대해 DTMF 명령 집합을 추가로 만들려면 사이트 ID와 함께 **New-CsDialinConferencingDtmfConfiguration** cmdlet를 사용합니다.
    
다음은 모든 참가자를 음소거 및 음소거 해제하기 위해 누르는 키와 공지 사항을 활성화 또는 비활성화하기 위해 누름 키를 바꾸는 예제입니다. IDENTITY를 지정하지 않은 경우 이러한 변경 내용은 전역 DTMF 설정에 적용됩니다.
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

자세한 내용은 [Get-CsDialInConferencingDtmfConfiguration,](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)및 [New-CsDialInConferencingDtmfConfiguration을](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)참조하십시오.
  

