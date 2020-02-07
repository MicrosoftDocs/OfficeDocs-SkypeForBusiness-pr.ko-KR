---
title: 통화 공원 및 Microsoft 팀에서 검색
ms.author: lolaj
author: LolaJacobsen
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
description: 통화 대기를 사용 하 고 클라우드의 팀 서비스에서 통화를 보류 하는 것을 검색 합니다.
ms.openlocfilehash: b4b5200f139f5610ff1109b97742607d3b633ff6
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824596"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="51e78-103">통화 공원 및 Microsoft 팀에서 검색</span><span class="sxs-lookup"><span data-stu-id="51e78-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="51e78-104">통화 공원 및 검색은 사용자가 클라우드의 팀 서비스에서 통화를 대기 상태로 설정할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="51e78-105">통화가 파킹 되 면 서비스에서 호출 검색에 대 한 고유 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="51e78-106">통화를 대기 하거나 다른 사용자가 해당 코드와 지원 되는 앱 또는 장치를 사용 하 여 통화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="51e78-107">통화 공원 사용에 대 한 일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="51e78-108">Receptionist는 공장에서 작업 하는 사람에 게 전화를 공원 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="51e78-109">그런 다음 receptionist는 공용 주소 시스템을 통해 통화와 코드 번호를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="51e78-110">전화를 받은 사용자는 공장 바닥에서 팀 전화를 선택 하 고 통화를 검색 하는 코드를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="51e78-111">디바이스 배터리의 전원이 부족 하 여 모바일 장치에서 통화를 공원.</span><span class="sxs-lookup"><span data-stu-id="51e78-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="51e78-112">그러면 사용자는 팀의 일반 전화기에서 통화를 검색 하는 코드를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="51e78-113">지원 담당자는 고객에 게 전화를 걸고 전문가를 위해 팀 채널에 알림을 보내 고객에 게 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="51e78-114">전문가는 전화를 검색 하기 위해 팀 클라이언트에 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51e78-115">이 기능은 팀 전용 배포 모드 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="51e78-116">팀 배포 모드에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51e78-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="51e78-117">라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="51e78-117">License required</span></span>

<span data-ttu-id="51e78-118">통화를 대기 하 고 검색 하려면 사용자가 엔터프라이즈 음성 사용자 여야 하 고 관리자가 사용자에 게 통화 공원 정책을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="51e78-119">라이선스 모델에 대 한 자세한 내용은 [Microsoft 팀 용 Office 365 라이선스](office-365-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51e78-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="51e78-120">통화 대기 및 기능 가용성 검색</span><span class="sxs-lookup"><span data-stu-id="51e78-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="51e78-121">통화 공원 및 검색은 현재 다음 클라이언트 및 장치에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="51e78-122">(팀 전용 모드에서는 PSTN 연결 여부에 관계 없이 지원 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="51e78-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="51e78-123">성능</span><span class="sxs-lookup"><span data-stu-id="51e78-123">Capability</span></span> | <span data-ttu-id="51e78-124">팀 데스크톱</span><span class="sxs-lookup"><span data-stu-id="51e78-124">Teams Desktop</span></span> | <span data-ttu-id="51e78-125">팀 Mac 앱</span><span class="sxs-lookup"><span data-stu-id="51e78-125">Teams Mac App</span></span> | <span data-ttu-id="51e78-126">팀 웹 앱 (Edge)</span><span class="sxs-lookup"><span data-stu-id="51e78-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="51e78-127">팀 모바일 iOS/Android 앱</span><span class="sxs-lookup"><span data-stu-id="51e78-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="51e78-128">팀 IP 전화</span><span class="sxs-lookup"><span data-stu-id="51e78-128">Teams IP phone</span></span> | <span data-ttu-id="51e78-129">비즈니스용 Skype IP 전화</span><span class="sxs-lookup"><span data-stu-id="51e78-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="51e78-130">통화 파킹</span><span class="sxs-lookup"><span data-stu-id="51e78-130">Park a call</span></span> | <span data-ttu-id="51e78-131">예</span><span class="sxs-lookup"><span data-stu-id="51e78-131">Yes</span></span> | <span data-ttu-id="51e78-132">예</span><span class="sxs-lookup"><span data-stu-id="51e78-132">Yes</span></span> | <span data-ttu-id="51e78-133">예</span><span class="sxs-lookup"><span data-stu-id="51e78-133">Yes</span></span> | <span data-ttu-id="51e78-134">예</span><span class="sxs-lookup"><span data-stu-id="51e78-134">Yes</span></span> | <span data-ttu-id="51e78-135">개봉박두</span><span class="sxs-lookup"><span data-stu-id="51e78-135">Coming soon</span></span>| <span data-ttu-id="51e78-136">아니요</span><span class="sxs-lookup"><span data-stu-id="51e78-136">No</span></span> |
| <span data-ttu-id="51e78-137">파킹 된 통화 검색</span><span class="sxs-lookup"><span data-stu-id="51e78-137">Retrieve a parked call</span></span> | <span data-ttu-id="51e78-138">예</span><span class="sxs-lookup"><span data-stu-id="51e78-138">Yes</span></span> | <span data-ttu-id="51e78-139">예</span><span class="sxs-lookup"><span data-stu-id="51e78-139">Yes</span></span> | <span data-ttu-id="51e78-140">예</span><span class="sxs-lookup"><span data-stu-id="51e78-140">Yes</span></span> | <span data-ttu-id="51e78-141">예</span><span class="sxs-lookup"><span data-stu-id="51e78-141">Yes</span></span> | <span data-ttu-id="51e78-142">개봉박두</span><span class="sxs-lookup"><span data-stu-id="51e78-142">Coming soon</span></span>| <span data-ttu-id="51e78-143">아니요</span><span class="sxs-lookup"><span data-stu-id="51e78-143">No</span></span> |
| <span data-ttu-id="51e78-144">통화 링 뒤로 검색</span><span class="sxs-lookup"><span data-stu-id="51e78-144">Unretrieved call ring back</span></span> | <span data-ttu-id="51e78-145">예</span><span class="sxs-lookup"><span data-stu-id="51e78-145">Yes</span></span> | <span data-ttu-id="51e78-146">예</span><span class="sxs-lookup"><span data-stu-id="51e78-146">Yes</span></span> | <span data-ttu-id="51e78-147">예</span><span class="sxs-lookup"><span data-stu-id="51e78-147">Yes</span></span> | <span data-ttu-id="51e78-148">예</span><span class="sxs-lookup"><span data-stu-id="51e78-148">Yes</span></span> | <span data-ttu-id="51e78-149">개봉박두</span><span class="sxs-lookup"><span data-stu-id="51e78-149">Coming soon</span></span>| <span data-ttu-id="51e78-150">아니요</span><span class="sxs-lookup"><span data-stu-id="51e78-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="51e78-151">통화 공원 구성 및 검색</span><span class="sxs-lookup"><span data-stu-id="51e78-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="51e78-152">관리자만 통화 대기를 구성 하 고 검색을 할 수 있으며 기본적으로이 기능은 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="51e78-153">사용자에 대해이 기능을 사용 하도록 설정 하 고 통화 공원 정책을 사용 하 여 사용자 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="51e78-154">사용자 집합에 같은 정책을 적용 하는 경우에는 서로 간에 전화를 걸고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="51e78-155">사용자에 대 한 통화 공원를 구성 하 고 통화 공원 사용자 그룹을 만들려면 아래 [통화 공원 할당 정책](#assign-a-call-park-policy) 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="51e78-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="51e78-156">통화 공원 및 검색 기능을 사용 하는 방법에 대 한 자세한 내용은 [팀에서 통화](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)대기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51e78-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="51e78-157">통화 공원 정책 사용</span><span class="sxs-lookup"><span data-stu-id="51e78-157">Enable a call park policy</span></span>

<span data-ttu-id="51e78-158">통화 공원 정책을 사용 하도록 설정 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="51e78-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="51e78-159">**Microsoft 팀 관리 센터** > **음성** > **통화 공원 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="51e78-160">**새 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-160">Select **New policy**.</span></span>
3. <span data-ttu-id="51e78-161">정책 이름을 지정한 다음 **통화 대기 허용** 을 **설정**으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="51e78-162">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="51e78-163">통화 공원 정책 할당</span><span class="sxs-lookup"><span data-stu-id="51e78-163">Assign a call park policy</span></span>

<span data-ttu-id="51e78-164">한 명 이상의 사용자에 게 통화 공원 정책을 할당 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="51e78-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="51e78-165">**Microsoft 팀 관리 센터** > **음성** > **통화 공원 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="51e78-166">정책 이름 왼쪽에 있는을 클릭 하 여 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="51e78-167">**사용자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="51e78-168">**사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="51e78-169">추가 하려는 각 사용자에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="51e78-170">사용자 추가를 마쳤으면 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="51e78-171">호출 공원 구성 및 PowerShell을 사용 하 여 검색</span><span class="sxs-lookup"><span data-stu-id="51e78-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="51e78-172">[새 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet을 사용 하 여 통화 공원 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="51e78-173">[CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet을 사용 하 여 통화 공원 정책을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="51e78-174">다음과 같이 [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) 를 사용 하 여 기본 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="51e78-175">해결사</span><span class="sxs-lookup"><span data-stu-id="51e78-175">Troubleshooting</span></span>

<span data-ttu-id="51e78-176">사용자가 공원 또는 검색 단추를 볼 수 없는 경우:</span><span class="sxs-lookup"><span data-stu-id="51e78-176">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="51e78-177">사용자가 통화 공원 정책을 사용 하도록 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="51e78-178">사용자가 전화를 검색 하 려 할 때 실패 하는 경우 다음을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="51e78-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="51e78-179">사용자가 팀 클라이언트 또는 팀 사용 가능 장치/전화를 사용 하 고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="51e78-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="51e78-180">그룹화 – 사용자가 통화 공원 그룹의 구성원이 며,이는 같은 팀 통화 공원 정책이 할당 된 것을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-180">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="51e78-181">섬 모드 – 팀 섬 모드에서는 통화 공원 및 읽어들이기를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="51e78-182">통화가 이미 검색 되었거나 종료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="51e78-183">추가 정보</span><span class="sxs-lookup"><span data-stu-id="51e78-183">More information</span></span>

<span data-ttu-id="51e78-184">[팀에서 통화를 파킹](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)합니다.</span><span class="sxs-lookup"><span data-stu-id="51e78-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>
