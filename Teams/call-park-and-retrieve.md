---
title: Microsoft Teams에서 공원 호출 및 검색
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 통화 공원을 사용하여 Microsoft Teams에서 통화를 보류하는 방법을 알아보고 검색합니다.
ms.openlocfilehash: 7474b80975c5fc78285a8bba5a90de782f24ba5b
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260330"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="6d02f-103">Microsoft Teams에서 공원 호출 및 검색</span><span class="sxs-lookup"><span data-stu-id="6d02f-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="6d02f-104">통화 공원 및 검색은 사용자가 통화를 보류할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="6d02f-105">호출이 파크된 경우 서비스는 호출 검색을 위한 고유한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="6d02f-106">통화를 저장한 사용자 또는 다른 사용자가 지원되는 앱 또는 장치에서 해당 코드를 사용하여 통화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="6d02f-107">(자세한 내용은 [Teams에서 Park 통화를](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) 참조합니다.)</span><span class="sxs-lookup"><span data-stu-id="6d02f-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="6d02f-108">호출 공원 사용에 대한 몇 가지 일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="6d02f-109">안내원이 공장에서 근무하는 사람을 위해 전화를 걸고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="6d02f-110">그런 다음, 안내원이 공용 주소 시스템을 통해 전화 및 코드 번호를 발표합니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="6d02f-111">그런 다음 전화를 걸고 있는 사용자는 공장 층에서 Teams 전화를 선택하고 통화를 검색하는 코드를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="6d02f-112">디바이스 배터리가 전원이 부족하기 때문에 사용자가 모바일 디바이스에 통화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="6d02f-113">그러면 사용자는 Teams 데스크 전화에서 통화를 검색하는 코드를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="6d02f-114">지원 담당자는 고객 통화를 저장하고 전문가가 전화를 검색하고 고객을 지원하기 위해 Teams 채널에 공지 사항을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="6d02f-115">전문가가 Teams 클라이언트에서 코드를 입력하여 호출을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="6d02f-116">통화를 정비하고 검색하려면 사용자는 Enterprise Voice 사용자로, 호출 공원 정책에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="6d02f-117">통화 공원 및 검색은 [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 전용 배포 모드에서만 사용할 수 있으며 비즈니스용 Skype IP 전화에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="6d02f-118">호출 공원 구성 및 검색</span><span class="sxs-lookup"><span data-stu-id="6d02f-118">Configure call park and retrieve</span></span>

<span data-ttu-id="6d02f-119">통화 공원을 구성하고 검색하려면 Teams 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="6d02f-120">기본적으로 사용하지 않도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-120">It is disabled by default.</span></span> <span data-ttu-id="6d02f-121">호출 공원 정책을 사용하여 사용자에 대해 사용하도록 설정하고 사용자 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="6d02f-122">사용자 집합에 동일한 정책을 적용하면 사용자들 사이에서 호출을 저장하고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="6d02f-123">통화 공원 정책을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="6d02f-123">To enable a call park policy</span></span>

1. <span data-ttu-id="6d02f-124">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 음성 통화 **공원**  >  **정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="6d02f-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="6d02f-125">정책 **관리 탭에서** 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d02f-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="6d02f-126">정책에 이름을 지정한 다음 호출 허용을 **켜기로** **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d02f-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![호출 공원 정책 설정 스크린샷](media/call-park-add-policy.png)

4. <span data-ttu-id="6d02f-128">저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d02f-128">Select **Save**.</span></span>

<span data-ttu-id="6d02f-129">목록에서 정책을 선택하고 편집을 클릭하여 정책을 편집할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6d02f-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="6d02f-130">정책이 작동하려면 사용자에게 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="6d02f-131">사용자에게 [개별적으로 정책을](assign-policies.md) 할당하거나 그룹에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="6d02f-132">그룹에 통화 파트 정책을 할당하는 경우</span><span class="sxs-lookup"><span data-stu-id="6d02f-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="6d02f-133">통화 공원 **정책 페이지의** 그룹 정책 **할당 탭에서** 그룹 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d02f-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="6d02f-134">사용할 그룹을 검색한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d02f-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="6d02f-135">다른 그룹 할당과 비교하여 순위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="6d02f-136">정책 **선택에서** 이 그룹을 할당하려는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6d02f-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="6d02f-137">적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d02f-137">Click **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6d02f-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6d02f-138">Related topics</span></span>

[<span data-ttu-id="6d02f-139">Teams에서 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="6d02f-139">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="6d02f-140">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6d02f-140">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="6d02f-141">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="6d02f-141">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="6d02f-142">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="6d02f-142">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="6d02f-143">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="6d02f-143">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
