---
title: 통화 공원 및 Microsoft 팀에서 검색
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 04/12/2019
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
description: 통화 공원을 사용 하 고 클라우드의 팀 서비스에서 통화를 보류 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 8c6f275ea1b1aac9bfa011fba76d17aeb1811e10
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582655"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="4d7a9-103">통화 공원 및 Microsoft 팀에서 검색</span><span class="sxs-lookup"><span data-stu-id="4d7a9-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="4d7a9-104">통화 공원 및 검색은 사용자가 클라우드의 팀 서비스에서 통화를 대기 상태로 설정할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="4d7a9-105">통화가 파킹 되 면 서비스에서 호출 검색에 대 한 고유 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="4d7a9-106">통화를 대기 하거나 다른 사용자가 해당 코드와 지원 되는 앱 또는 장치를 사용 하 여 통화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="4d7a9-107">통화 공원 사용에 대 한 일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="4d7a9-108">Receptionist는 공장에서 작업 하는 사람에 게 전화를 공원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="4d7a9-109">그런 다음 receptionist는 공용 주소 시스템을 통해 통화와 코드 번호를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="4d7a9-110">전화를 받은 사용자는 공장 바닥에서 팀 전화를 선택 하 고 통화를 검색 하는 코드를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="4d7a9-111">디바이스 배터리의 전원이 부족 하 여 모바일 장치에서 통화를 공원.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="4d7a9-112">그러면 사용자는 팀의 일반 전화기에서 통화를 검색 하는 코드를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="4d7a9-113">지원 담당자는 고객에 게 전화를 걸고 전문가를 위해 팀 채널에 알림을 보내 고객에 게 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="4d7a9-114">전문가는 전화를 검색 하기 위해 팀 클라이언트에 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d7a9-115">이 기능은 팀 전용 배포 모드 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="4d7a9-116">팀 배포 모드에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="4d7a9-117">라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="4d7a9-117">License required</span></span>

<span data-ttu-id="4d7a9-118">통화를 대기 하 고 검색 하려면 사용자가 엔터프라이즈 음성 사용자 여야 하 고 관리자가 사용자에 게 통화 공원 정책을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="4d7a9-119">라이선스 모델에 대 한 자세한 내용은 [Microsoft 팀 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-119">For more information about the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="4d7a9-120">통화 대기 및 기능 가용성 검색</span><span class="sxs-lookup"><span data-stu-id="4d7a9-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="4d7a9-121">통화 공원 및 검색은 현재 다음 클라이언트 및 장치에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="4d7a9-122">(팀 전용 모드에서는 PSTN 연결 여부에 관계 없이 지원 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="4d7a9-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="4d7a9-123">기능</span><span class="sxs-lookup"><span data-stu-id="4d7a9-123">Capability</span></span> | <span data-ttu-id="4d7a9-124">팀 데스크톱</span><span class="sxs-lookup"><span data-stu-id="4d7a9-124">Teams Desktop</span></span> | <span data-ttu-id="4d7a9-125">팀 Mac 앱</span><span class="sxs-lookup"><span data-stu-id="4d7a9-125">Teams Mac App</span></span> | <span data-ttu-id="4d7a9-126">팀 웹 앱 (Edge)</span><span class="sxs-lookup"><span data-stu-id="4d7a9-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="4d7a9-127">팀 모바일 iOS/Android 앱</span><span class="sxs-lookup"><span data-stu-id="4d7a9-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="4d7a9-128">팀 IP 전화</span><span class="sxs-lookup"><span data-stu-id="4d7a9-128">Teams IP phone</span></span> | <span data-ttu-id="4d7a9-129">비즈니스용 Skype IP 전화</span><span class="sxs-lookup"><span data-stu-id="4d7a9-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="4d7a9-130">통화 파킹</span><span class="sxs-lookup"><span data-stu-id="4d7a9-130">Park a call</span></span> | <span data-ttu-id="4d7a9-131">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-131">Yes</span></span> | <span data-ttu-id="4d7a9-132">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-132">Yes</span></span> | <span data-ttu-id="4d7a9-133">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-133">Yes</span></span> | <span data-ttu-id="4d7a9-134">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-134">Yes</span></span> | <span data-ttu-id="4d7a9-135">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-135">Yes</span></span> | <span data-ttu-id="4d7a9-136">아니요</span><span class="sxs-lookup"><span data-stu-id="4d7a9-136">No</span></span> |
| <span data-ttu-id="4d7a9-137">파킹 된 통화 검색</span><span class="sxs-lookup"><span data-stu-id="4d7a9-137">Retrieve a parked call</span></span> | <span data-ttu-id="4d7a9-138">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-138">Yes</span></span> | <span data-ttu-id="4d7a9-139">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-139">Yes</span></span> | <span data-ttu-id="4d7a9-140">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-140">Yes</span></span> | <span data-ttu-id="4d7a9-141">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-141">Yes</span></span> | <span data-ttu-id="4d7a9-142">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-142">Yes</span></span> | <span data-ttu-id="4d7a9-143">아니요</span><span class="sxs-lookup"><span data-stu-id="4d7a9-143">No</span></span> |
| <span data-ttu-id="4d7a9-144">통화 링 뒤로 검색</span><span class="sxs-lookup"><span data-stu-id="4d7a9-144">Unretrieved call ring back</span></span> | <span data-ttu-id="4d7a9-145">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-145">Yes</span></span> | <span data-ttu-id="4d7a9-146">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-146">Yes</span></span> | <span data-ttu-id="4d7a9-147">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-147">Yes</span></span> | <span data-ttu-id="4d7a9-148">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-148">Yes</span></span> | <span data-ttu-id="4d7a9-149">예</span><span class="sxs-lookup"><span data-stu-id="4d7a9-149">Yes</span></span> | <span data-ttu-id="4d7a9-150">아니요</span><span class="sxs-lookup"><span data-stu-id="4d7a9-150">No</span></span> |

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="4d7a9-151">통화 공원 구성 및 검색</span><span class="sxs-lookup"><span data-stu-id="4d7a9-151">Configure call park and retrieve</span></span>

<span data-ttu-id="4d7a9-152">통화 공원 및 검색을 구성 하려면 관리자 여야 하며 기본적으로이 기능은 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-152">You must be an admin to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="4d7a9-153">사용자에 대해이 기능을 사용 하도록 설정 하 고 통화 공원 정책을 사용 하 여 사용자 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="4d7a9-154">사용자 집합에 같은 정책을 적용 하는 경우에는 서로 간에 전화를 걸고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="4d7a9-155">사용자에 대 한 통화 공원를 구성 하 고 통화 공원 사용자 그룹을 만들려면 아래 [통화 공원 할당 정책](#assign-a-call-park-policy) 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="4d7a9-156">통화 공원 및 검색 기능을 사용 하는 방법에 대 한 자세한 내용은 [팀에서 통화](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)대기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="4d7a9-157">통화 공원 정책 사용</span><span class="sxs-lookup"><span data-stu-id="4d7a9-157">Enable a call park policy</span></span>

1. <span data-ttu-id="4d7a9-158">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **통화 공원 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-158">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="4d7a9-159">**추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-159">Select **Add**.</span></span>
3. <span data-ttu-id="4d7a9-160">정책 이름을 지정한 다음 **통화 대기 허용** 을 **설정**으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-160">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>
4. <span data-ttu-id="4d7a9-161">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-161">Select **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="4d7a9-162">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="4d7a9-162">Using PowerShell</span></span>

<span data-ttu-id="4d7a9-163">[새로운 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-163">See [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span></span>

### <a name="edit-a-call-park-policy"></a><span data-ttu-id="4d7a9-164">통화 공원 정책 편집</span><span class="sxs-lookup"><span data-stu-id="4d7a9-164">Edit a call park policy</span></span>

1. <span data-ttu-id="4d7a9-165">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **통화 공원 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-165">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="4d7a9-166">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-166">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="4d7a9-167">통화 대기를 **끄거나** **켜려면**스위치를 **사용** 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-167">Switch **Allow call park** to **Off** or **On**.</span></span>
4. <span data-ttu-id="4d7a9-168">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-168">Click **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="4d7a9-169">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="4d7a9-169">Using PowerShell</span></span>

<span data-ttu-id="4d7a9-170">[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-170">See [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span></span> <span data-ttu-id="4d7a9-171">예를 들어 기본 설정을 변경 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-171">For example, to change the default setting, run the following:</span></span>

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="4d7a9-172">통화 공원 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4d7a9-172">Assign a call park policy</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
<span data-ttu-id="4d7a9-173">[허용-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-173">See also [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="4d7a9-174">문제 해결</span><span class="sxs-lookup"><span data-stu-id="4d7a9-174">Troubleshooting</span></span>

<span data-ttu-id="4d7a9-175">사용자가 공원 또는 검색 단추를 볼 수 없는 경우:</span><span class="sxs-lookup"><span data-stu-id="4d7a9-175">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="4d7a9-176">사용자가 통화 공원 정책을 사용 하도록 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-176">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="4d7a9-177">사용자가 전화를 검색 하 려 할 때 실패 하는 경우 다음을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-177">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="4d7a9-178">사용자가 팀 클라이언트 또는 팀 사용 가능 장치/전화를 사용 하 고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="4d7a9-178">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="4d7a9-179">그룹화 – 사용자가 통화 공원 그룹의 구성원이 며,이는 같은 팀 통화 공원 정책이 할당 된 것을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-179">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="4d7a9-180">섬 모드 – 팀 섬 모드에서는 통화 공원 및 읽어들이기를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-180">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="4d7a9-181">통화가 이미 검색 되었거나 종료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4d7a9-181">The call has already been retrieved or terminated.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4d7a9-182">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4d7a9-182">Related topics</span></span>

[<span data-ttu-id="4d7a9-183">팀에서 통화 대기</span><span class="sxs-lookup"><span data-stu-id="4d7a9-183">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="4d7a9-184">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4d7a9-184">Assign policies to your users in Teams</span></span>](assign-policies.md)
