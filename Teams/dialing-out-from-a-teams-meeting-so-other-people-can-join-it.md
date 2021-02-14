---
title: 다른 사람이 참가할 수 있도록 모임에서 전화 걸기
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
description: 모임 이끌이는 Teams 앱을 사용하여 다른 사람들이 자신의 휴대폰을 사용하여 같은 모임에 참가할 수 있도록 하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 575ed18bd3dbd404dba947c0c4556d52e0653200
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788762"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="01e4d-103">다른 사람이 참가할 수 있도록 Microsoft Teams 모임에서 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="01e4d-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="01e4d-104">모임 이끌이는 Teams 앱을 사용하여 전화를 걸면 다른 사람들이 자신의 휴대폰을 사용하여 같은 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01e4d-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="01e4d-105">다른 사람에게 전화를 걸 때 전체 전화 번호(국가/지역 코드 포함 - E.164 형식)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="01e4d-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="01e4d-106">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="01e4d-106">Please note that:</span></span>

- <span data-ttu-id="01e4d-107">Teams를 사용하여 모임에 참가하는 경우만 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01e4d-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="01e4d-108">모임 이끌이는 오디오 회의를 사용하도록 설정되어 있습니다. 또는 오디오 회의 라이선스가 할당되지 않은 경우 온라인 통화 계획 또는 직접 라우팅을 통해 공용 전화망에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01e4d-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="01e4d-109">모임 이끌이에게 회의에서 전화 걸기를 사용하도록 설정하는 온라인 전화 걸기 [정책이 부여됩니다.](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="01e4d-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="01e4d-110">작동하기 위해 전화 걸기를 하는 방법을 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="01e4d-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="01e4d-111">**1단계:** 모임에서 사용자 **추가** 단추 옵션의 사용자 추가 스크린샷을 사용하여 전화 번호로 전화를 걸 수 ![ ](media/add-people-button.png) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01e4d-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="01e4d-112">**2단계:** 초대에 국가/지역 코드를 포함하여 전체 전화 번호를 입력하거나 **번호 상자에 전화를 걸 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01e4d-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![다른 사람 초대 또는 전화 걸기 상자 스크린샷](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="01e4d-114">지원되는 국가 및 지역</span><span class="sxs-lookup"><span data-stu-id="01e4d-114">Supported countries and regions</span></span>

<span data-ttu-id="01e4d-115">전화 접속은 일부 국가/지역에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01e4d-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="01e4d-116">전체 목록은 오디오 회의 및 통화 계획에 대한 국가 및 지역 [가용성을 참조하세요.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="01e4d-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="01e4d-117">사용자가 전화를 걸 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="01e4d-117">Allow users to dial in</span></span>

<span data-ttu-id="01e4d-118">사용자가 Teams 모임에 전화를 걸 수 있도록 하는 방법에 대한 지침을 찾고 있는 경우 Microsoft Teams의 오디오 회의 전화 번호를 [참조하세요.](phone-numbers-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="01e4d-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="01e4d-119">오디오 회의에 대해 더 알고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="01e4d-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="01e4d-120">오디오 회의 시도 또는 구매</span><span class="sxs-lookup"><span data-stu-id="01e4d-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="01e4d-121">Microsoft Teams 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="01e4d-121">Microsoft Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
