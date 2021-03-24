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
description: 비즈니스용 Skype 서버 2013에서 보류 음악 및 벨소리 설정과 같은 응용 프로그램 수준 응답 그룹 Enterprise Voice.
ms.openlocfilehash: 941164fb3a99f62303b45f587b64e7aff9cb1393
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103474"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="6945c-103">비즈니스용 Skype에서 응용 프로그램 수준 응답 그룹 설정 관리</span><span class="sxs-lookup"><span data-stu-id="6945c-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="6945c-104">비즈니스용 Skype 서버 2013에서 보류 음악 및 벨소리 설정과 같은 응용 프로그램 수준 응답 그룹 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6945c-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="6945c-105">응답 그룹 응용 프로그램에 대한 응용 프로그램 수준 설정에는 기본 보류 음악 구성, 기본 통화 보류 오디오 파일, 에이전트 벨백 유예 기간 및 통화 컨텍스트 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6945c-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="6945c-106">풀당 응용 프로그램 수준 설정 집합을 한 개만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6945c-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="6945c-107">응용 프로그램 수준 설정을 보기 위해 **Get-CsRgsConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6945c-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="6945c-108">응용 프로그램 수준 설정을 수정하려면 **Set-CsRgsConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6945c-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="6945c-109">사용자 지정 보류 음악이 정의되어 있는 경우 통화가 보류 중일 때만 기본 보류 음악이 재생됩니다.</span><span class="sxs-lookup"><span data-stu-id="6945c-109">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="6945c-110">통화 컨텍스트는 대화형 워크플로에 할당된 큐에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6945c-110">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="6945c-111">통화 컨텍스트를 사용하도록 설정하면 에이전트가 발신자 대기 시간 또는 워크플로 질문과 같은 정보를 볼 수 있으며 통화가 수신될 때 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6945c-111">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="6945c-112">응답 그룹 응용 프로그램 수준 설정을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="6945c-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="6945c-113">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6945c-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="6945c-114">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6945c-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6945c-115">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6945c-115">At the command line, run:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="6945c-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6945c-116">For example:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="6945c-117">기본 보류 음악으로 사용할 오디오 파일을 지정하려면 먼저 오디오 파일을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6945c-117">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="6945c-118">예:</span><span class="sxs-lookup"><span data-stu-id="6945c-118">For example:</span></span>
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="6945c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6945c-119">See also</span></span>

[<span data-ttu-id="6945c-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6945c-120">Get-CsRgsConfiguration</span></span>](/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="6945c-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6945c-121">Set-CsRgsConfiguration</span></span>](/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="6945c-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="6945c-122">Import-CsRgsAudioFile</span></span>](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)