---
title: 다른 사용자가 참가할 수 있도록 모임에서 전화 걸기
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 3c2db9a5-3a19-4e19-b59e-8e5587f25d31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 모임 이끌이는 다른 사용자가 자신의 전화를 사용 하 여 동일한 모임에 참가할 수 있도록 팀 앱을 사용 하 여 전화를 거는 방법을 알아봅니다.
ms.openlocfilehash: f84f811d89847bfdf17f123abe9c2df88536bc76
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662108"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="37edb-103">다른 사용자가 참여할 수 있도록 Microsoft 팀 모임에서 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="37edb-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="37edb-104">모임 이끌이는 팀 앱을 사용 하 여 전화를 걸어 다른 사람이 전화기를 사용 하 여 동일한 모임에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="37edb-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="37edb-105">다른 사람에 게 전화를 걸 때 전체 전화 번호 (국가/지역 코드-E-164 형식 포함)를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="37edb-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="37edb-106">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="37edb-106">Please note that:</span></span>

- <span data-ttu-id="37edb-107">팀을 사용 하 여 모임에 참가 하는 경우에만 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37edb-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="37edb-108">모임 이끌이는 오디오 회의에 사용 하도록 설정 되어 있거나, 오디오 회의 라이선스가 할당 되지 않은 경우, 온라인 통화 계획 또는 직접 라우팅을 통해 공용 전환 전화 네트워크에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37edb-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="37edb-109">모임 이끌이는 [회의에서 전화를 걸 수 있는 온라인 전화 접속 정책이 부여](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37edb-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="37edb-110">다음과 같은 방법으로 전화를 걸어 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37edb-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="37edb-111">**1 단계:** 모임에서 **Add people** ![ 사람 추가 단추에 대 한 사용자 추가 스크린샷을 사용 하 여 ](media/add-people-button.png) 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37edb-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="37edb-112">**2 단계:** **다른 사람 초대 또는 전화 걸기** 상자에 국가/지역 번호를 포함 하 여 전체 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="37edb-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![다른 사용자 초대 또는 전화 번호 상자 스크린샷](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="37edb-114">지원 되는 국가 및 지역</span><span class="sxs-lookup"><span data-stu-id="37edb-114">Supported countries and regions</span></span>

<span data-ttu-id="37edb-115">전화 걸기는 일부 국가/지역 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37edb-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="37edb-116">전체 목록은 [오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37edb-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="37edb-117">사용자의 전화 접속 허용</span><span class="sxs-lookup"><span data-stu-id="37edb-117">Allow users to dial in</span></span>

<span data-ttu-id="37edb-118">사용자가 팀 모임에 전화를 걸 수 있도록 하는 방법에 대 한 지침을 찾으려면 [Microsoft 팀에서 오디오 회의에 대 한 전화 번호](phone-numbers-for-audio-conferencing-in-teams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37edb-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="37edb-119">오디오 회의에 대 한 자세한 내용을 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="37edb-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="37edb-120">오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="37edb-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="37edb-121">Microsoft Teams 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="37edb-121">Microsoft Teams add-on licensing</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
