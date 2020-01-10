---
title: 비즈니스용 Skype에서 응용 프로그램 수준 응답 그룹 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: '비즈니스용 Skype Server Enterprise Voice에서 응용 프로그램 수준 응답 그룹 설정 (예: ringback) 및 인터넷 설정 등의 관리'
ms.openlocfilehash: 4c5964d84e5fb84bf1c20c3e43bb0cc4aa25ae17
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001278"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>비즈니스용 Skype에서 응용 프로그램 수준 응답 그룹 설정 관리
 
비즈니스용 Skype Server Enterprise Voice에서 응용 프로그램 수준 응답 그룹 설정 (예: ringback) 및 인터넷 설정 등의 관리
  
응답 그룹 응용 프로그램에 대 한 응용 프로그램 수준 설정에는 기본 음악 보존 구성, 기본 음악 대기 오디오 파일, 에이전트 ringback 유예 기간 및 통화 컨텍스트 구성이 포함 됩니다. 풀 당 하나의 응용 프로그램 수준 설정 집합을 정의할 수 있습니다. 응용 프로그램 수준 설정을 보려면 **Get-CsRgsConfiguration** cmdlet을 사용 합니다. 응용 프로그램 수준 설정을 수정 하려면 **Set-CsRgsConfiguration** cmdlet을 사용 합니다.
  
보류 중인 사용자 지정 음악을 정의 하지 않은 경우에만 통화 대기의 기본 음악이 재생 됩니다. 대화형 워크플로에 할당 된 큐 에서만 호출 컨텍스트를 사용할 수 있습니다. 호출 컨텍스트를 사용 하는 경우 상담원은 통화를 받을 때 발신자 대기 시간 또는 워크플로 질문과 대답 등의 정보를 볼 수 있습니다.
  
### <a name="to-modify-response-group-application-level-settings"></a>응답 그룹 응용 프로그램 수준 설정을 수정 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 명령줄에서 다음을 실행 합니다.
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    대기 중인 기본 음악으로 사용할 오디오 파일을 지정 하려면 먼저 오디오 파일을 가져와야 합니다. 예를 들면 다음과 같습니다.
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>참고 항목

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[가져오기-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
