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
ms.openlocfilehash: ffce659c2c4dc6c91ba4e4935b72c15e4cef4da5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a>Lync Server 2013의 응용 프로그램 수준 응답 그룹 설정 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

응답 그룹 응용 프로그램에 대 한 응용 프로그램 수준 설정에는 기본 음악 보존 구성, 기본 음악 대기 오디오 파일, 에이전트 ringback 유예 기간 및 통화 컨텍스트 구성이 포함 됩니다. 풀 당 하나의 응용 프로그램 수준 설정 집합을 정의할 수 있습니다. 응용 프로그램 수준 설정을 보려면 **Get-CsRgsConfiguration** cmdlet을 사용 합니다. 응용 프로그램 수준 설정을 수정 하려면 **Set-CsRgsConfiguration** cmdlet을 사용 합니다.

보류 중인 사용자 지정 음악을 정의 하지 않은 경우에만 통화 대기의 기본 음악이 재생 됩니다. 대화형 워크플로에 할당 된 큐 에서만 호출 컨텍스트를 사용할 수 있습니다. 호출 컨텍스트를 사용 하는 경우 상담원은 통화를 받을 때 발신자 대기 시간 또는 워크플로 질문과 대답 등의 정보를 볼 수 있습니다.

<div>

## <a name="to-modify-response-group-application-level-settings"></a>응답 그룹 응용 프로그램 수준 설정을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  명령줄에서 다음을 실행 합니다.
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    예를 들면 다음과 같습니다.
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    대기 중인 기본 음악으로 사용할 오디오 파일을 지정 하려면 먼저 오디오 파일을 가져와야 합니다. 예를 들면 다음과 같습니다.
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[가져오기-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

