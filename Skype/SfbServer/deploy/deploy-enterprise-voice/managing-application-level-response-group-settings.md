---
title: 비즈니스용 Skype에서 응용 프로그램 수준 응답 그룹 설정 관리
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: 비즈니스용 Skype 서버에서 보류 음악 및 벨백 설정과 같은 응용 프로그램 수준 응답 그룹 설정 Enterprise Voice.
ms.openlocfilehash: d41211b83e5ce0c27bb9efe1d3d15a6289ae38fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830788"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>비즈니스용 Skype에서 응용 프로그램 수준 응답 그룹 설정 관리
 
비즈니스용 Skype 서버에서 보류 음악 및 벨백 설정과 같은 응용 프로그램 수준 응답 그룹 설정 Enterprise Voice.
  
응답 그룹 응용 프로그램에 대한 응용 프로그램 수준 설정에는 기본 보류 음악 구성, 기본 보류 음악 오디오 파일, 에이전트 다시 울림 유예 기간 및 통화 컨텍스트 구성이 포함됩니다. 풀당 응용 프로그램 수준 설정 집합을 한 개만 정의할 수 있습니다. 응용 프로그램 수준 설정을 보기 위해 **Get-CsRgsConfiguration** cmdlet을 사용합니다. 응용 프로그램 수준 설정을 수정하려면 **Set-CsRgsConfiguration** cmdlet을 사용합니다.
  
사용자 지정 보류 음악이 정의되어 있는 경우 통화가 보류 중일 때만 기본 보류 음악이 재생됩니다. 통화 컨텍스트는 대화형 워크플로에 할당된 큐에만 사용할 수 있습니다. 통화 컨텍스트를 사용하도록 설정하면 에이전트는 발신자 대기 시간 또는 워크플로 질문과 통화 수신 시 답변 등의 정보를 볼 수 있습니다.
  
### <a name="to-modify-response-group-application-level-settings"></a>응답 그룹 응용 프로그램 수준 설정을 수정하려면

1. RTCUniversalServerAdmins 그룹의 구성원으로 로그온하거나 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
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

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
