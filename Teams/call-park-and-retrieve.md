---
title: 통화 공원 및 Microsoft 팀에서 검색
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
description: 통화 대기를 사용 하 고 Microsoft 팀에서 통화를 진행 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424596"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="ebe0d-103">통화 공원 및 Microsoft 팀에서 검색</span><span class="sxs-lookup"><span data-stu-id="ebe0d-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="ebe0d-104">통화 공원 및 검색은 사용자가 통화를 대기 상태로 설정할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="ebe0d-105">통화가 파킹 되 면 서비스에서 호출 검색에 대 한 고유 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="ebe0d-106">통화를 대기 하거나 다른 사용자가 해당 코드를 지원 되는 앱 또는 장치와 함께 사용 하 여 통화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="ebe0d-107">자세한 내용은 [팀에서 통화 대기의 파킹을](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="ebe0d-108">통화 공원 사용에 대 한 일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="ebe0d-109">Receptionist는 공장에서 작업 하는 사람에 게 전화를 공원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="ebe0d-110">그런 다음 receptionist는 공용 주소 시스템을 통해 통화와 코드 번호를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="ebe0d-111">전화를 받은 사용자는 공장 바닥에서 팀 전화를 선택 하 고 통화를 검색 하는 코드를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="ebe0d-112">디바이스 배터리의 전원이 부족 하 여 모바일 장치에서 통화를 공원.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="ebe0d-113">그러면 사용자는 팀의 일반 전화기에서 통화를 검색 하는 코드를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="ebe0d-114">지원 담당자는 고객에 게 전화를 걸고 전문가를 위해 팀 채널에 알림을 보내 고객에 게 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="ebe0d-115">전문가는 전화를 검색 하기 위해 팀 클라이언트에 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="ebe0d-116">통화를 대기 하 고 검색 하려면 사용자가 엔터프라이즈 음성 사용자 여야 하며 통화 대기 정책에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-116">To park and retrieve calls, a user must be an Enterprise Voice user and and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="ebe0d-117">통화 공원 및 검색은 [팀 전용 배포 모드](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 에서만 사용할 수 있으며 비즈니스용 Skype IP 전화에서는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="ebe0d-118">통화 공원 구성 및 검색</span><span class="sxs-lookup"><span data-stu-id="ebe0d-118">Configure call park and retrieve</span></span>

<span data-ttu-id="ebe0d-119">통화 공원 및 검색을 구성 하려면 팀 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="ebe0d-120">이 기능은 기본적으로 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-120">It is disabled by default.</span></span> <span data-ttu-id="ebe0d-121">사용자에 대해이 기능을 사용 하도록 설정 하 고 통화 공원 정책을 사용 하 여 사용자 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="ebe0d-122">사용자 집합에 같은 정책을 적용 하는 경우에는 서로 간에 전화를 걸고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="ebe0d-123">통화 공원 정책을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="ebe0d-123">To enable a call park policy</span></span>

1. <span data-ttu-id="ebe0d-124">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **통화 공원 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="ebe0d-125">**정책 관리** 탭에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="ebe0d-126">정책 이름을 지정한 다음 **통화 대기 허용** 을 **설정**으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![통화 공원 정책 설정 스크린샷](media/call-park-add-policy.png)

4. <span data-ttu-id="ebe0d-128">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-128">Select **Save**.</span></span>

<span data-ttu-id="ebe0d-129">목록에서 정책을 선택 하 고 **편집**을 클릭 하 여 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="ebe0d-130">정책이 작동 하려면 사용자에 게 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="ebe0d-131">[정책을 사용자에 게 개별적으로 할당](assign-policies.md) 하거나 그룹에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="ebe0d-132">전화 파트 정책을 그룹에 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="ebe0d-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="ebe0d-133">**통화 공원 정책** 페이지의 **그룹 정책 할당** 탭에서 **그룹 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="ebe0d-134">사용할 그룹을 검색 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="ebe0d-135">다른 그룹 배정과 비교한 순위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="ebe0d-136">**정책 선택**에서이 그룹에 할당할 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="ebe0d-137">**적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe0d-137">Click **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ebe0d-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ebe0d-138">Related topics</span></span>

[<span data-ttu-id="ebe0d-139">팀에서 통화 대기</span><span class="sxs-lookup"><span data-stu-id="ebe0d-139">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="ebe0d-140">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="ebe0d-140">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="ebe0d-141">새로운 CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="ebe0d-141">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="ebe0d-142">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="ebe0d-142">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="ebe0d-143">부여-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="ebe0d-143">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)