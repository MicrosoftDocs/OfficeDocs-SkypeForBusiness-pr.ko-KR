---
title: 비즈니스용 Skype에서 응용 프로그램 수준 응답 그룹 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '비즈니스용 Skype Server Enterprise Voice에서 응용 프로그램 수준 응답 그룹 설정 (예: ringback) 및 인터넷 설정 등의 관리'
ms.openlocfilehash: 99a3d6bc82cffd39608d2da0be013d4fbb8389e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767111"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="31ea7-103">비즈니스용 Skype에서 응용 프로그램 수준 응답 그룹 설정 관리</span><span class="sxs-lookup"><span data-stu-id="31ea7-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="31ea7-104">비즈니스용 Skype Server Enterprise Voice에서 응용 프로그램 수준 응답 그룹 설정 (예: ringback) 및 인터넷 설정 등의 관리</span><span class="sxs-lookup"><span data-stu-id="31ea7-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="31ea7-105">응답 그룹 응용 프로그램에 대 한 응용 프로그램 수준 설정에는 기본 음악 보존 구성, 기본 음악 대기 오디오 파일, 에이전트 ringback 유예 기간 및 통화 컨텍스트 구성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="31ea7-106">풀 당 하나의 응용 프로그램 수준 설정 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="31ea7-107">응용 프로그램 수준 설정을 보려면 **Get-CsRgsConfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="31ea7-108">응용 프로그램 수준 설정을 수정 하려면 **Set-CsRgsConfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="31ea7-109">보류 중인 사용자 지정 음악을 정의 하지 않은 경우에만 통화 대기의 기본 음악이 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-109">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="31ea7-110">대화형 워크플로에 할당 된 큐 에서만 호출 컨텍스트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-110">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="31ea7-111">호출 컨텍스트를 사용 하는 경우 상담원은 통화를 받을 때 발신자 대기 시간 또는 워크플로 질문과 대답 등의 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-111">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="31ea7-112">응답 그룹 응용 프로그램 수준 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="31ea7-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="31ea7-113">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="31ea7-114">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="31ea7-115">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-115">At the command line, run:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="31ea7-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-116">For example:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="31ea7-117">대기 중인 기본 음악으로 사용할 오디오 파일을 지정 하려면 먼저 오디오 파일을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-117">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="31ea7-118">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="31ea7-118">For example:</span></span>
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="31ea7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31ea7-119">See also</span></span>

[<span data-ttu-id="31ea7-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="31ea7-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="31ea7-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="31ea7-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="31ea7-122">가져오기-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="31ea7-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
