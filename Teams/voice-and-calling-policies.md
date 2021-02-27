---
title: Teams에서 음성 및 통화 정책 관리
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d0ea4db57fbfdc3ab76e8c6c9991e032103b260
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2021
ms.locfileid: "50348037"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="b25f5-102">Microsoft Teams에서 음성 및 통화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="b25f5-102">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="b25f5-103">음성 및 통화 정책은 Microsoft Teams에서 음성 및 통화를 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b25f5-103">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="b25f5-104">긴급 통화 정책</span><span class="sxs-lookup"><span data-stu-id="b25f5-104">Emergency calling policies</span></span>

<span data-ttu-id="b25f5-105">긴급 호출 [정책을](manage-emergency-calling-policies.md) 사용하여 조직의 사용자가 긴급 통화를 할 때 발생하는 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b25f5-105">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="b25f5-106">이러한 정책은 Teams 관리 센터에서 관리되거나 해당 정책을 사용하여 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b25f5-106">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![긴급 통화 정책 스크린샷.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="b25f5-108">긴급 통화 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="b25f5-108">Emergency call routing policies</span></span>

<span data-ttu-id="b25f5-109">조직에서 **전화** 시스템 직접 라우팅을 배포한 경우 [](manage-emergency-call-routing-policies.md) 긴급 통화 라우팅 정책을 사용하여 긴급 통화가 라우팅되는 위치, 향상된 응급 서비스를 사용하도록 설정되어 있는지 여부 및 응급 서비스에 사용되는 숫자를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b25f5-109">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="b25f5-110">이러한 정책은 PowerShell 또는 Microsoft Teams 관리 센터에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b25f5-110">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![긴급 통화 라우팅 정책 스크린샷.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="b25f5-112">발신자 ID 정책</span><span class="sxs-lookup"><span data-stu-id="b25f5-112">Caller ID policies</span></span>

<span data-ttu-id="b25f5-113">[발신자 ID 정책은](caller-id-policies.md) 발신자 ID를 변경하거나 차단하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b25f5-113">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![발신자 ID 정책 스크린샷.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="b25f5-115">음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="b25f5-115">Voice routing policies</span></span>

<span data-ttu-id="b25f5-116">음성 [라우팅 정책은](manage-voice-routing-policies.md) PSTN(공용 전환 전화 네트워크) 사용 레코드에 대한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="b25f5-116">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="b25f5-117">조직에서 Phone System Direct 라우팅을 배포한 경우 이러한 정책을 **사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b25f5-117">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="b25f5-118">PowerShell 또는 Teams 관리 센터에서 음성 라우팅 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b25f5-118">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![음성 라우팅 정책 스크린샷.](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="b25f5-120">통화 정책</span><span class="sxs-lookup"><span data-stu-id="b25f5-120">Calling policies</span></span>

<span data-ttu-id="b25f5-121">[통화 정책은](teams-calling-policy.md) 사용자가 개인 통화를 할 수 있는지, 통화 그룹에 전화를 보내고, 음성 메일로 통화를 라우팅할 수 있는지 여부를 포함하여 사용자가 사용할 수 있는 통화 및 통화 전달 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b25f5-121">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![통화 정책 스크린샷.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="b25f5-123">통화 공원 및 정책 검색</span><span class="sxs-lookup"><span data-stu-id="b25f5-123">Call park and retrieve policies</span></span>

<span data-ttu-id="b25f5-124">[통화 공원 및 검색을](call-park-and-retrieve.md) 사용하면 사용자가 다른 사용자를 보류하고 동일한 사용자 또는 다른 사용자가 통화를 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b25f5-124">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![통화 공원의 스크린샷 및 정책을 검색합니다.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="b25f5-126">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="b25f5-126">Create and manage dial plans</span></span>

<span data-ttu-id="b25f5-127">[전화 요금제는](create-and-manage-dial-plans.md) 통화 권한 부여 및 라우팅을 위해 전화 걸기 전화 번호를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b25f5-127">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="b25f5-128">PowerShell 또는 Microsoft Teams 관리 센터를 통해 전화 걸기 계획을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b25f5-128">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![다이얼 계획의 스크린샷.](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="b25f5-130">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b25f5-130">Related topics</span></span>

* [<span data-ttu-id="b25f5-131">Microsoft Teams에서 긴급 통화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="b25f5-131">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="b25f5-132">긴급 전화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="b25f5-132">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="b25f5-133">Microsoft Teams에서 발신자 ID 정책 관리</span><span class="sxs-lookup"><span data-stu-id="b25f5-133">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="b25f5-134">음성 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="b25f5-134">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="b25f5-135">Microsoft Teams의 통화 정책</span><span class="sxs-lookup"><span data-stu-id="b25f5-135">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="b25f5-136">통화 공원 및 Microsoft Teams에서 검색</span><span class="sxs-lookup"><span data-stu-id="b25f5-136">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="b25f5-137">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="b25f5-137">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="b25f5-138">정책으로 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="b25f5-138">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
