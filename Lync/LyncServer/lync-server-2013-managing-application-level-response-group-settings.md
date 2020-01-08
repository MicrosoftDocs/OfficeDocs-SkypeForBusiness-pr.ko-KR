---
title: 'Lync Server 2013: 응용 프로그램 수준 응답 그룹 설정 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bac03eaafc40ccd86aca8514319e3bf632ea6a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="e7cd1-102">Lync Server 2013의 응용 프로그램 수준 응답 그룹 설정 관리</span><span class="sxs-lookup"><span data-stu-id="e7cd1-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7cd1-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e7cd1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e7cd1-104">응답 그룹 응용 프로그램에 대 한 응용 프로그램 수준 설정에는 기본 음악 보존 구성, 기본 음악 대기 오디오 파일, 에이전트 ringback 유예 기간 및 통화 컨텍스트 구성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="e7cd1-105">풀 당 하나의 응용 프로그램 수준 설정 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="e7cd1-106">응용 프로그램 수준 설정을 보려면 **Get-CsRgsConfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="e7cd1-107">응용 프로그램 수준 설정을 수정 하려면 **Set-CsRgsConfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="e7cd1-108">보류 중인 사용자 지정 음악을 정의 하지 않은 경우에만 통화 대기의 기본 음악이 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-108">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="e7cd1-109">대화형 워크플로에 할당 된 큐 에서만 호출 컨텍스트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-109">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="e7cd1-110">호출 컨텍스트를 사용 하는 경우 상담원은 통화를 받을 때 발신자 대기 시간 또는 워크플로 질문과 대답 등의 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-110">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="e7cd1-111">응답 그룹 응용 프로그램 수준 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="e7cd1-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="e7cd1-112">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="e7cd1-113">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e7cd1-114">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="e7cd1-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="e7cd1-116">대기 중인 기본 음악으로 사용할 오디오 파일을 지정 하려면 먼저 오디오 파일을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-116">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="e7cd1-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e7cd1-117">For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7cd1-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7cd1-118">See Also</span></span>


[<span data-ttu-id="e7cd1-119">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7cd1-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="e7cd1-120">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7cd1-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="e7cd1-121">가져오기-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="e7cd1-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

