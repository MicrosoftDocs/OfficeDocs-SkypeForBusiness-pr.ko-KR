---
title: 'Lync Server 2013: 응용 프로그램 수준 응답 그룹 설정 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af64929beba67b29b4588bae12a5a45c9de64460
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498345"
---
# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a>Lync Server 2013에서 응용 프로그램 수준 응답 그룹 설정 관리

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

응답 그룹 응용 프로그램에 대 한 응용 프로그램 수준 설정에는 기본 보류 구성, 기본 음악 대기 오디오 파일, 에이전트의 되 걸기 유예 기간 및 호출 컨텍스트 구성 등이 포함 됩니다. 풀당 응용 프로그램 수준 설정 집합을 한 개만 정의할 수 있습니다. 응용 프로그램 수준 설정을 보려면 **export-csrgsconfiguration** cmdlet을 사용 합니다. 응용 프로그램 수준 설정을 수정 하려면 **export-csrgsconfiguration** cmdlet을 사용 합니다.

보류 중인 사용자 지정 음악을 정의 하지 않은 경우에만 통화 대기의 기본 음악을 재생 합니다. 대화형 워크플로에 할당 된 큐 에서만 통화 컨텍스트를 사용할 수 있습니다. 호출 컨텍스트를 사용 하는 경우 상담원은 통화를 받을 때 발신자 대기 시간 또는 워크플로 질문과 대답 등의 정보를 볼 수 있습니다.

<div>

## <a name="to-modify-response-group-application-level-settings"></a>응답 그룹 응용 프로그램 수준 설정을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에서 다음을 실행합니다.
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    예를 들면 다음과 같습니다.
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    대기 기본 음악으로 사용할 오디오 파일을 지정 하려면 먼저 오디오 파일을 가져와야 합니다. 예를 들면 다음과 같습니다.
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Export-csrgsconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[Export-csrgsconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[Import-csrgsaudiofile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

