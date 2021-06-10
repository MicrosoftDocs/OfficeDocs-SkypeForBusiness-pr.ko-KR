---
title: 음성 및 통화 정책 관리 Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 음성 및 Teams 정책에 대해 자세히 알아보습니다.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460588"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="183a8-103">음성 및 통화 정책 관리 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="183a8-103">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="183a8-104">음성 및 통화 정책은 음성 및 통화를 제어하는 데 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="183a8-104">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="183a8-105">긴급 통화 정책</span><span class="sxs-lookup"><span data-stu-id="183a8-105">Emergency calling policies</span></span>

<span data-ttu-id="183a8-106">긴급 호출 [정책을](manage-emergency-calling-policies.md) 사용하여 조직의 사용자가 긴급 통화를 할 때 발생하는 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="183a8-106">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="183a8-107">이러한 정책은 관리 센터 또는 Teams 관리 센터에서 관리 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="183a8-107">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![긴급 통화 정책 스크린샷.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="183a8-109">긴급 통화 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="183a8-109">Emergency call routing policies</span></span>

<span data-ttu-id="183a8-110">조직에서 직접 라우팅을 전화 시스템 경우 긴급 통화 라우팅 [](manage-emergency-call-routing-policies.md) 정책을 사용하여 긴급 통화가 라우팅되는 위치, 향상된 응급 서비스를 사용할 수 있는지 여부 및 긴급 서비스에 사용되는 숫자를 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="183a8-110">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="183a8-111">이러한 정책은 PowerShell을 사용하여 관리되거나 관리 Microsoft Teams 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="183a8-111">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![긴급 통화 라우팅 정책 스크린샷.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="183a8-113">발신자 ID 정책</span><span class="sxs-lookup"><span data-stu-id="183a8-113">Caller ID policies</span></span>

<span data-ttu-id="183a8-114">[발신자 ID 정책은](caller-id-policies.md) 발신자 ID를 변경하거나 차단하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="183a8-114">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![발신자 ID 정책 스크린샷.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="183a8-116">음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="183a8-116">Voice routing policies</span></span>

<span data-ttu-id="183a8-117">음성 [라우팅 정책은](manage-voice-routing-policies.md) PSTN(공용 전환 전화 네트워크) 사용 레코드에 대한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="183a8-117">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="183a8-118">조직에서 직접 라우팅을 배포한 경우 이러한 **정책을 전화 시스템 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="183a8-118">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="183a8-119">PowerShell 또는 관리 센터에서 음성 라우팅 정책을 관리할 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="183a8-119">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![음성 라우팅 정책 스크린샷.](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="183a8-121">통화 정책</span><span class="sxs-lookup"><span data-stu-id="183a8-121">Calling policies</span></span>

<span data-ttu-id="183a8-122">[통화 정책은](teams-calling-policy.md) 사용자가 개인 통화를 할 수 있는지, 통화 그룹에 전화를 보내고, 음성 메일로 통화를 라우팅할 수 있는지 여부를 포함하여 사용자가 사용할 수 있는 통화 및 통화 전달 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="183a8-122">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![통화 정책 스크린샷.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="183a8-124">통화 공원 및 정책 검색</span><span class="sxs-lookup"><span data-stu-id="183a8-124">Call park and retrieve policies</span></span>

<span data-ttu-id="183a8-125">[통화 공원 및 검색을](call-park-and-retrieve.md) 사용하면 사용자가 다른 사용자를 보류하고 동일한 사용자 또는 다른 사용자가 통화를 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="183a8-125">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![통화 공원의 스크린샷 및 정책을 검색합니다.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="183a8-127">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="183a8-127">Create and manage dial plans</span></span>

<span data-ttu-id="183a8-128">[전화 요금제는](create-and-manage-dial-plans.md) 통화 권한 부여 및 라우팅을 위해 전화 걸기 전화 번호를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="183a8-128">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="183a8-129">PowerShell 또는 관리 센터에서 전화 걸기 계획을 만들고 관리할 Microsoft Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="183a8-129">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![다이얼 계획의 스크린샷.](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="183a8-131">관련 항목</span><span class="sxs-lookup"><span data-stu-id="183a8-131">Related topics</span></span>

* [<span data-ttu-id="183a8-132">긴급 통화 정책 관리 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="183a8-132">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="183a8-133">긴급 전화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="183a8-133">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="183a8-134">Microsoft Teams에서 발신자 ID 정책 관리</span><span class="sxs-lookup"><span data-stu-id="183a8-134">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="183a8-135">음성 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="183a8-135">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="183a8-136">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="183a8-136">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="183a8-137">통화 공원을 호출하고 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="183a8-137">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="183a8-138">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="183a8-138">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="183a8-139">정책으로 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="183a8-139">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
