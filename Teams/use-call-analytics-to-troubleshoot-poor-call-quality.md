---
title: 통화 분석을 사용하여 통화 품질 저하 문제 해결
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 장치, 네트워크 및 연결에 대 한 통화 분석 세부 정보를 사용 하 여 Microsoft 팀과 비즈니스용 Skype 통화 및 모임에서 발생 하는 사용자 문제를 해결할 수 있습니다.
ms.openlocfilehash: 71a1e1c339c502da5cbbf998c75e758f2bbe3be2
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665250"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="16ab2-103">통화 분석을 사용하여 통화 품질 저하 문제 해결</span><span class="sxs-lookup"><span data-stu-id="16ab2-103">Use Call Analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="16ab2-104">통화 분석을 통해 Microsoft 팀과 비즈니스용 Skype의 통화 또는 연결 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-104">Call Analytics helps you troubleshoot call or connection problems with Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="16ab2-105">통화 분석에서는 Microsoft 365 또는 Office 365 계정에 있는 각 사용자의 통화 및 모임에 대 한 장치, 네트워크 및 연결에 대 한 자세한 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Microsoft 365 or Office 365 account.</span></span> <span data-ttu-id="16ab2-106">빌드, 사이트 및 테 넌 트 정보가 통화 분석에 추가 된 경우 각 통화와 세션에 대해서도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="16ab2-107">통화 분석을 통해 사용할 수 있는 정보는 사용자의 통화 또는 모임 환경이 좋지 않은 이유를 파악 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
## <a name="call-analytics-permissions"></a><span data-ttu-id="16ab2-108">통화 분석 사용 권한</span><span class="sxs-lookup"><span data-stu-id="16ab2-108">Call Analytics permissions</span></span>

<span data-ttu-id="16ab2-109">관리자는 통화 분석의 모든 기능에 대 한 모든 권한을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-109">As the admin, you get full access to all the features of Call Analytics.</span></span> <span data-ttu-id="16ab2-110">또한 지원 직원에 게 Azure Active Directory 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-110">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="16ab2-111">통화 분석을 제한 된 보기를 사용 해야 하는 사용자에 게 팀 의사 소통 지원 전문가 역할을 배정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-111">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="16ab2-112">통화 분석의 전체 기능에 대 한 액세스 권한이 필요한 사용자에 게 팀 의사 소통 지원 엔지니어 역할을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-112">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="16ab2-113">두 사용 권한 수준 모두에서 나머지 Microsoft 팀 관리 센터에 대 한 액세스를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-113">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

<span data-ttu-id="16ab2-114">통신 지원 전문가는 기본 통화 품질 문제를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-114">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="16ab2-115">모임 관련 문제를 조사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-115">They don't investigate issues with meetings.</span></span> <span data-ttu-id="16ab2-116">그 대신 관련 정보를 수집한 다음 통신 지원 엔지니어로 승격 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-116">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="16ab2-117">통신 지원 엔지니어가 통신 지원 전문가에 게 서 숨겨진 자세한 콜 로그의 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-117">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="16ab2-118">다음 표에서는 통화 분석을 사용할 때 통신 지원 엔지니어가 제공 하는 정보에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-118">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

<span data-ttu-id="16ab2-119">사용자에 게 할당 된 사용 권한 수준은 통화 분석에서 액세스할 수 있는 정보 유형을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-119">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="16ab2-120">**팀 서비스 관리자 또는 팀 통신 관리자**: 통화 분석 및 Microsoft 팀 관리 센터의 모든 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-120">**Teams service administrator or Teams communications administrator**: You have access to all the information in Call Analytics and in the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="16ab2-121">**팀 의사 소통 지원 전문가**: 통화 분석에서 제한 된 데이터 집합을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-121">**Teams communications support specialist**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="16ab2-122">통화 문제를 해결할 수 있지만, 팀 의사 소통 지원 엔지니어에 대 한 모임 문제는 해결 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-122">You can troubleshoot calls, but you'll hand off problems with meetings to a Teams communications support engineer.</span></span> <span data-ttu-id="16ab2-123">나머지 Microsoft 팀 관리 센터에 액세스할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-123">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="16ab2-124">**팀 의사 소통 지원 엔지니어**: 통화 분석에서 사용할 수 있는 모든 데이터를 볼 수 있으며, 통화와 모임 모두의 문제를 해결 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-124">**Teams communications support engineer**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="16ab2-125">나머지 Microsoft 팀 관리 센터에 액세스할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-125">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
> [!NOTE]
> <span data-ttu-id="16ab2-126">커뮤니케이션 지원 전문가 역할은 계층 1 지원과 같으며 통신 지원 엔지니어 역할은 계층 2 지원과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-126">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="16ab2-127">팀 관리자 역할에 대 한 자세한 내용은 [Microsoft 팀 관리자 역할을 사용 하 여 팀 관리](using-admin-roles.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="16ab2-127">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="16ab2-128">팀 의사 소통 지원 전문가 및 팀 의사 소통 지원 엔지니어 역할에 대 한 자세한 비교는 [통화 분석 설정을](set-up-call-analytics.md#set-call-analytics-permissions) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="16ab2-128">For a detailed comparison of the Teams communications support specialist and Teams communications support engineer roles, see [Set up Call Analytics](set-up-call-analytics.md#set-call-analytics-permissions)</span></span> 
  
<span data-ttu-id="16ab2-129">사용 권한에 대 한 도움이 필요한 경우 팀과 비즈니스용 Skype 관리자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="16ab2-129">See your Teams and Skype for Business admin if you need help with permissions.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="16ab2-130">통화 분석을 사용 하 여 통화 품질 문제 해결</span><span class="sxs-lookup"><span data-stu-id="16ab2-130">Troubleshoot call quality problems using Call Analytics</span></span>

1. <span data-ttu-id="16ab2-131">팀 통신 지원 또는 팀 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-131">Sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="16ab2-132">웹 브라우저에서으로 이동 *https://admin.teams.microsoft.com* 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-132">In your web browser go to *https://admin.teams.microsoft.com*.</span></span>
    
3. <span data-ttu-id="16ab2-133">**대시보드의** **사용자 검색**에서 문제를 해결할 사용자의 이름 또는 sip 주소를 입력 하거나 사용자 **보기** 를 선택 하 여 사용자 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-133">On the **Dashboard**, in **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot or select **View users** to see a list of users.</span></span>
    
    ![통화 분석의 사용자 검색 상자 스크린샷](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. <span data-ttu-id="16ab2-135">목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-135">Select the user from the list.</span></span>

5. <span data-ttu-id="16ab2-136">**통화 내역**을 선택한 다음 문제를 해결할 통화 또는 모임을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-136">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>  <span data-ttu-id="16ab2-137">최대 500 개의 레코드가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-137">A maximum of 500 records will be returned.</span></span>
    
    ![사용자의 통화 기록 페이지 스크린샷.](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. <span data-ttu-id="16ab2-139">**고급** 탭을 선택 하 고 잘못 된 통화 음질 또는 연결 문제를 나타내는 노란색 및 빨간색 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-139">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="16ab2-140">각 통화 또는 모임에 대 한 세션 세부 정보에서 경미한 문제는 노란색으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-140">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="16ab2-141">예를 들어 다음 스크린샷은 평균 지터, 최대 지터 및 평균 패킷 손실률에 대 한 값이 노란색으로 되어 있습니다. 노란색이 있는 것은 정상 범위를 벗어나므로 문제가 될 수 있지만 문제의 주요 원인이 되는 경우는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-141">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="16ab2-142">무언가 빨간색 인 경우 중대 한 문제가 될 수 있으며,이 세션에 대 한 통화 품질이 좋지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-142">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![<span data-ttu-id="16ab2-143">사용자의 통화 기록 고급 탭 스크린샷</span><span class="sxs-lookup"><span data-stu-id="16ab2-143">Screenshot of the Advanced tab of a user's Call history</span></span> ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
<span data-ttu-id="16ab2-144">드문 경우 지만 오디오 세션에 대 한 경험 치 데이터를 받지 못하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-144">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="16ab2-145">이 오류는 일반적으로 호출을 끊는 것이 고 클라이언트를 종료 하는 연결 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-145">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="16ab2-146">이 문제가 발생 하면 세션 등급을 **사용할 수 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="16ab2-146">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="16ab2-147">체감 품질 (환경 품질) 데이터를 사용 하는 오디오 세션의 경우 다음 표에서는 세션을 **불량**으로 정규화 하는 주요 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-147">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="16ab2-148">**문제**</span><span class="sxs-lookup"><span data-stu-id="16ab2-148">**Issue**</span></span>|<span data-ttu-id="16ab2-149">**지역을**</span><span class="sxs-lookup"><span data-stu-id="16ab2-149">**Area**</span></span>|<span data-ttu-id="16ab2-150">**설명**</span><span class="sxs-lookup"><span data-stu-id="16ab2-150">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="16ab2-151">전화 걸기 설정</span><span class="sxs-lookup"><span data-stu-id="16ab2-151">Call setup</span></span>  <br/> |<span data-ttu-id="16ab2-152">세션</span><span class="sxs-lookup"><span data-stu-id="16ab2-152">Session</span></span>  <br/> |<span data-ttu-id="16ab2-153">오류 코드 Ms-diag 20-29는 통화 설정이 실패 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-153">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="16ab2-154">사용자가 통화 또는 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-154">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="16ab2-155">오디오 네트워크에서 낮은 통화 분류</span><span class="sxs-lookup"><span data-stu-id="16ab2-155">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="16ab2-156">세션</span><span class="sxs-lookup"><span data-stu-id="16ab2-156">Session</span></span>  <br/> |<span data-ttu-id="16ab2-157">네트워크 품질 문제 (예: 패킷 손실, 지터, NMOS 성능 저하, RTT 또는 숨겨진 비율)가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-157">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span> <span data-ttu-id="16ab2-158">불량 통화를 분류 하는 데 사용 되는 조건에 대 한 자세한 내용은이 [Microsoft 블로그 게시물](https://go.microsoft.com/fwlink/p/?linkid=852133)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="16ab2-158">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="16ab2-159">장치가 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="16ab2-159">Device not functioning</span></span>  <br/> |<span data-ttu-id="16ab2-160">장치</span><span class="sxs-lookup"><span data-stu-id="16ab2-160">Device</span></span>  <br/> | <span data-ttu-id="16ab2-161">장치가 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-161">A device isn't functioning correctly.</span></span> <span data-ttu-id="16ab2-162">장치 작동 비율이 아닌 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab2-162">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="16ab2-163">DeviceRenderNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="16ab2-163">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="16ab2-164">DeviceCaptureNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="16ab2-164">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="16ab2-165">관련 항목</span><span class="sxs-lookup"><span data-stu-id="16ab2-165">Related topics</span></span>
[<span data-ttu-id="16ab2-166">통화 분석 설정</span><span class="sxs-lookup"><span data-stu-id="16ab2-166">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="16ab2-167">통화 분석 및 통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="16ab2-167">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
