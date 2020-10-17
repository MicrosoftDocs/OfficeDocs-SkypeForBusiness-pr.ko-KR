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
# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="cf019-102">Lync Server 2013에서 응용 프로그램 수준 응답 그룹 설정 관리</span><span class="sxs-lookup"><span data-stu-id="cf019-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf019-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cf019-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cf019-104">응답 그룹 응용 프로그램에 대 한 응용 프로그램 수준 설정에는 기본 보류 구성, 기본 음악 대기 오디오 파일, 에이전트의 되 걸기 유예 기간 및 호출 컨텍스트 구성 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="cf019-105">풀당 응용 프로그램 수준 설정 집합을 한 개만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="cf019-106">응용 프로그램 수준 설정을 보려면 **export-csrgsconfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="cf019-107">응용 프로그램 수준 설정을 수정 하려면 **export-csrgsconfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="cf019-108">보류 중인 사용자 지정 음악을 정의 하지 않은 경우에만 통화 대기의 기본 음악을 재생 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-108">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="cf019-109">대화형 워크플로에 할당 된 큐 에서만 통화 컨텍스트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-109">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="cf019-110">호출 컨텍스트를 사용 하는 경우 상담원은 통화를 받을 때 발신자 대기 시간 또는 워크플로 질문과 대답 등의 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-110">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="cf019-111">응답 그룹 응용 프로그램 수준 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="cf019-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="cf019-112">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="cf019-113">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cf019-114">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="cf019-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="cf019-116">대기 기본 음악으로 사용할 오디오 파일을 지정 하려면 먼저 오디오 파일을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-116">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="cf019-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf019-117">For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cf019-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf019-118">See Also</span></span>


[<span data-ttu-id="cf019-119">Export-csrgsconfiguration</span><span class="sxs-lookup"><span data-stu-id="cf019-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="cf019-120">Export-csrgsconfiguration</span><span class="sxs-lookup"><span data-stu-id="cf019-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="cf019-121">Import-csrgsaudiofile</span><span class="sxs-lookup"><span data-stu-id="cf019-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

