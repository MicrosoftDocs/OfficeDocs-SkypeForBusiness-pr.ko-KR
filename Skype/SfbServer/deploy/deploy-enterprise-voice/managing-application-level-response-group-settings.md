---
title: 응용 프로그램 수준 응답 그룹 설정 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: 보류 음악 및 벨소리 설정과 같은 응용 프로그램 수준 응답 그룹 설정을 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 6cce6872bc0e1ee017d46eee4ee547c6e9aabd25
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769616"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>응용 프로그램 수준 응답 그룹 설정 비즈니스용 Skype
 
보류 음악 및 벨소리 설정과 같은 응용 프로그램 수준 응답 그룹 설정을 비즈니스용 Skype 서버 Enterprise Voice.
  
응답 그룹 응용 프로그램에 대한 응용 프로그램 수준 설정에는 기본 보류 음악 구성, 기본 통화 보류 오디오 파일, 에이전트 벨백 유예 기간 및 통화 컨텍스트 구성이 포함됩니다. 풀당 응용 프로그램 수준 설정 집합을 한 개만 정의할 수 있습니다. 응용 프로그램 수준 설정을 보기 위해 **Get-CsRgsConfiguration** cmdlet을 사용합니다. 응용 프로그램 수준 설정을 수정하려면 **Set-CsRgsConfiguration** cmdlet을 사용합니다.
  
사용자 지정 보류 음악이 정의되어 있는 경우 통화가 보류 중일 때만 기본 보류 음악이 재생됩니다. 통화 컨텍스트는 대화형 워크플로에 할당된 큐에만 사용할 수 있습니다. 통화 컨텍스트를 사용하도록 설정하면 에이전트가 발신자 대기 시간 또는 워크플로 질문과 같은 정보를 볼 수 있으며 통화가 수신될 때 응답할 수 있습니다.
  
### <a name="to-modify-response-group-application-level-settings"></a>응답 그룹 응용 프로그램 수준 설정을 수정하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 명령줄에서 다음을 실행합니다.
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    기본 보류 음악으로 사용할 오디오 파일을 지정하려면 먼저 오디오 파일을 가져와야 합니다. 예제:
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>참고 항목

[Get-CsRgsConfiguration](/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)