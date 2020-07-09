---
title: 통화 분석을 사용 하 여 통화 품질 저하 문제 해결
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 장치, 네트워크 및 연결에 대 한 사용자별 통화 분석 세부 정보를 사용 하 여 Microsoft 팀원의 통화 및 모임에서 발생 하는 문제를 해결할 수 있습니다.
ms.openlocfilehash: fa923a133ac6a56edcbc6f6445d2859692adf351
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085324"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="05597-103">통화 분석을 사용 하 여 통화 품질 저하 문제 해결</span><span class="sxs-lookup"><span data-stu-id="05597-103">Use call analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="05597-104">이 문서에서는 팀 관리자 또는 팀 통신 지원 전문가 또는 엔지니어의 경우 통화 분석을 사용 하 여 개별 사용자의 불충분 한 Microsoft 팀 통화 또는 모임 품질 문제를 해결 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-104">This article explains how to use call analytics to troubleshoot poor Microsoft Teams call or meeting quality for individual users if you're a Teams admin or a Teams communications support specialist or engineer.</span></span>


  
## <a name="call-analytics-permissions"></a><span data-ttu-id="05597-105">통화 분석 사용 권한</span><span class="sxs-lookup"><span data-stu-id="05597-105">Call Analytics permissions</span></span>

<span data-ttu-id="05597-106">이 문서에서는 이미 통화 분석을 설정한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-106">This article assumes that you've already set up call analytics.</span></span> <span data-ttu-id="05597-107">그렇지 않은 경우 [팀에 대 한 통화 분석 설정을](set-up-call-analytics.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="05597-107">If you haven't, read [Set up call analytics for Teams](set-up-call-analytics.md).</span></span>

## <a name="introduction-to-call-analytics"></a><span data-ttu-id="05597-108">통화 분석 소개</span><span class="sxs-lookup"><span data-stu-id="05597-108">Introduction to call analytics</span></span>

<span data-ttu-id="05597-109">통화 분석에서는 Office 365 계정에서 각 사용자의 팀 호출 및 모임에 대 한 자세한 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05597-109">Call analytics shows detailed information about Teams calls and meetings for each user in your Office 365 account.</span></span> <span data-ttu-id="05597-110">여기에는 장치, 네트워크, 연결, 통화 품질에 대 한 정보가 포함 되어 있습니다 (통화 품질이 좋지 않을 수 있습니다.).</span><span class="sxs-lookup"><span data-stu-id="05597-110">It includes information about devices, networks, connectivity, and call quality (any of these can be a factor in poor call or meeting quality).</span></span> <span data-ttu-id="05597-111">빌드, 사이트 및 테 넌 트 정보를 업로드 하는 경우, 각 통화와 모임에 대 한 정보도 함께 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-111">If you upload building, site, and tenant information, this information will also be shown for each call and meeting.</span></span> <span data-ttu-id="05597-112">통화 분석을 사용 하 여 사용자의 통화 또는 모임 환경이 좋지 않은 이유를 알아낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-112">Use call analytics to help you figure out why a user had a poor call or meeting experience.</span></span>

<span data-ttu-id="05597-113">통화 분석에서는 한 명의 참가자에서 두 번째 참가자에 이르기까지 통화 또는 모임의 각 레그를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05597-113">Call analytics shows you each leg of a call or meeting - for example, from one participant to a second participant.</span></span> <span data-ttu-id="05597-114">팀 관리자는 이러한 세부 정보를 분석 하 여 문제 영역을 분리 하 고 품질이 좋지 않은 경우 근본 원인을 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-114">By analyzing these details, a Teams admin can isolate problem areas and identify the root cause for poor quality.</span></span>
   
<span data-ttu-id="05597-115">팀 관리자는 각 사용자에 대 한 모든 통화 분석 데이터에 대 한 모든 액세스 권한을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-115">As the Teams admin, you get full access to all call analytics data for each user.</span></span> <span data-ttu-id="05597-116">또한 지원 직원에 게 Azure Active Directory 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="05597-117">이러한 역할에 대 한 자세한 내용은 [지원 및 헬프 데스크 직원에 대 한 사용 권한을](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="05597-117">To learn more about these roles, read [Give permission to support and helpdesk staff](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).</span></span> <span data-ttu-id="05597-118">[각 팀이 역할을 지 원하는 기능](#what-does-each-teams-support-role-do) 을 놓치지 마세요.</span><span class="sxs-lookup"><span data-stu-id="05597-118">Don't miss [What does each Teams Support role do?](#what-does-each-teams-support-role-do) below.</span></span>

## <a name="where-to-find-per-user-call-analytics"></a><span data-ttu-id="05597-119">사용자별 통화 분석을 찾을 수 있는 위치</span><span class="sxs-lookup"><span data-stu-id="05597-119">Where to find per-user call analytics</span></span>

<span data-ttu-id="05597-120">사용자의 모든 통화 정보 및 데이터를 보려면 [팀 관리 센터로](https://admin.teams.microsoft.com)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-120">To see all call information and data for a user, go to the [Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="05597-121">사용자 **에서**사용자를 선택한 다음 사용자 프로필 페이지에서 **통화 기록** 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="05597-121">Under **Users**, select a user and then open the **Call History** tab on the user's profile page.</span></span> <span data-ttu-id="05597-122">여기에서 지난 30 일간 해당 사용자의 모든 통화와 모임을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-122">Here you'll find all calls and meetings for that user for the last 30 days.</span></span>

![모든 분석 사용자 데이터의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="05597-124">자세한 미디어 및 네트워킹 통계를 포함 하 여 지정 된 세션에 대 한 추가 정보를 얻으려면 세션을 클릭 하 여 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-124">To get additional information about a given session, including detailed media and networking statistics, click a session to see the details.</span></span>

![통화 분석 사용자 세션 데이터 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a><span data-ttu-id="05597-126">각 팀이 역할을 지 원하는 기능은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="05597-126">What does each Teams Support role do?</span></span>

<span data-ttu-id="05597-127">**팀 의사 소통 지원 전문가** (계층 1 지원)는 기본 통화 품질 문제를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-127">The **Teams communications support specialist** (Tier 1 support) handles basic call-quality problems.</span></span> <span data-ttu-id="05597-128">모임 관련 문제를 조사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-128">They don't investigate issues with meetings.</span></span> <span data-ttu-id="05597-129">그 대신 관련 정보를 수집한 다음 통신 지원 엔지니어로 승격 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-129">Instead, they collect related information and then escalate to a communications support engineer.</span></span> 

<span data-ttu-id="05597-130">**팀 의사 소통 지원 엔지니어** (계층 2 지원)는 팀 통신 지원 전문가에 게 서 숨겨진 자세한 콜 로그의 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-130">The **Teams communications support engineer** (Tier 2 support) sees information in detailed call logs that are hidden from the Teams communications support specialist.</span></span> <span data-ttu-id="05597-131">아래 표에는 각 팀 통신 지원 역할에 사용할 수 있는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-131">The table below lists the information available to each Teams communication support role.</span></span>

<span data-ttu-id="05597-132">다음 표에서는 각 통신 지원 역할에 사용할 수 있는 사용자별 정보를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="05597-132">The following table tells you what per-user information is available for each communications support role.</span></span>

|<span data-ttu-id="05597-133">**활동**</span><span class="sxs-lookup"><span data-stu-id="05597-133">**Activity**</span></span>|<span data-ttu-id="05597-134">**방법**</span><span class="sxs-lookup"><span data-stu-id="05597-134">**Information**</span></span>|<span data-ttu-id="05597-135">통신 지원 **전문가가** 볼 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="05597-135">What the communications support **specialist** sees</span></span>|<span data-ttu-id="05597-136">통신 지원 **엔지니어가** 볼 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="05597-136">What the communications support **engineer** sees</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="05597-137">**전화가**</span><span class="sxs-lookup"><span data-stu-id="05597-137">**Calls**</span></span> <br/> |<span data-ttu-id="05597-138">발신자 이름</span><span class="sxs-lookup"><span data-stu-id="05597-138">Caller name</span></span>  <br/> |<span data-ttu-id="05597-139">에이전트에서 검색 한 사용자의 이름만</span><span class="sxs-lookup"><span data-stu-id="05597-139">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="05597-140">사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="05597-140">User name.</span></span>  <br/> |
||<span data-ttu-id="05597-141">받는 사람 이름</span><span class="sxs-lookup"><span data-stu-id="05597-141">Recipient name</span></span>  <br/> |<span data-ttu-id="05597-142">내부 사용자 또는 외부 사용자로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-142">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="05597-143">받는 사람 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="05597-143">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="05597-144">호출자 전화 번호</span><span class="sxs-lookup"><span data-stu-id="05597-144">Caller phone number</span></span>  <br/> |<span data-ttu-id="05597-145">마지막 세 자리 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-145">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="05597-146">예를 들어 15552823 \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="05597-146">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="05597-147">마지막 세 자리 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-147">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="05597-148">예를 들어 15552823 \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="05597-148">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="05597-149">받는 사람 전화 번호</span><span class="sxs-lookup"><span data-stu-id="05597-149">Recipient phone number</span></span>  <br/> |<span data-ttu-id="05597-150">마지막 세 자리 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-150">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="05597-151">예를 들어 15552823 \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="05597-151">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="05597-152">마지막 세 자리 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-152">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="05597-153">예를 들어 15552823 \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="05597-153">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="05597-154">**통화 정보**  >  **고급** 탭</span><span class="sxs-lookup"><span data-stu-id="05597-154">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="05597-155">정보가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-155">Information not shown.</span></span>  <br/> |<span data-ttu-id="05597-156">표시 되는 모든 정보 (예: 장치 이름, IP 주소, 서브넷 매핑 등)</span><span class="sxs-lookup"><span data-stu-id="05597-156">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="05597-157">**통화 정보**  >  **고급**  >  **디버그** 탭</span><span class="sxs-lookup"><span data-stu-id="05597-157">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="05597-158">정보가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-158">Information not shown.</span></span>  <br/> |<span data-ttu-id="05597-159">DNS 접미사 및 SSID와 같이 표시 되는 모든 정보</span><span class="sxs-lookup"><span data-stu-id="05597-159">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="05597-160">**모임**</span><span class="sxs-lookup"><span data-stu-id="05597-160">**Meetings**</span></span> <br/> |<span data-ttu-id="05597-161">참가자 이름</span><span class="sxs-lookup"><span data-stu-id="05597-161">Participant names</span></span>  <br/> |<span data-ttu-id="05597-162">에이전트에서 검색 한 사용자의 이름만</span><span class="sxs-lookup"><span data-stu-id="05597-162">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="05597-163">다른 참가자가 내부 사용자 또는 외부 사용자로 식별 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-163">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="05597-164">모든 이름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-164">All names shown.</span></span>  <br/> |
||<span data-ttu-id="05597-165">참가자 수</span><span class="sxs-lookup"><span data-stu-id="05597-165">Participant count</span></span>  <br/> |<span data-ttu-id="05597-166">참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="05597-166">Number of participants.</span></span>  <br/> |<span data-ttu-id="05597-167">참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="05597-167">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="05597-168">세션 정보</span><span class="sxs-lookup"><span data-stu-id="05597-168">Session details</span></span>  <br/> |<span data-ttu-id="05597-169">세션 정보가 예외와 함께 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-169">Session details shown with exceptions.</span></span> <span data-ttu-id="05597-170">에이전트가 검색 한 사용자의 이름만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-170">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="05597-171">다른 참가자가 내부 사용자 또는 외부 사용자로 식별 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-171">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="05597-172">별표 기호로 난독 처리 된 전화 번호의 마지막 세 자리입니다.</span><span class="sxs-lookup"><span data-stu-id="05597-172">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="05597-173">세션 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-173">Session details shown.</span></span> <span data-ttu-id="05597-174">사용자 이름 및 세션 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-174">User names and session details shown.</span></span> <span data-ttu-id="05597-175">별표 기호로 난독 처리 된 전화 번호의 마지막 세 자리입니다.</span><span class="sxs-lookup"><span data-stu-id="05597-175">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a><span data-ttu-id="05597-176">사용자 통화 품질 문제 해결</span><span class="sxs-lookup"><span data-stu-id="05597-176">Troubleshoot user call quality problems</span></span> 

1. <span data-ttu-id="05597-177">팀 관리 센터를 열고 https://admin.teams.microsoft.com) 팀 통신 지원 또는 팀 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-177">Open the Teams admin center (https://admin.teams.microsoft.com) and sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="05597-178">**대시보드의** **사용자 검색**에서 문제를 해결할 사용자의 이름 또는 SIP 주소를 입력 하거나 **사용자 보기** 를 선택 하 여 사용자 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-178">On the **Dashboard**, in **User Search**, start typing either the name or SIP address of the user whose calls you want to troubleshoot, or select **View users** to see a list of users.</span></span>

3. <span data-ttu-id="05597-179">목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-179">Select the user from the list.</span></span>

4. <span data-ttu-id="05597-180">**통화 내역**을 선택한 다음 문제를 해결할 통화 또는 모임을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-180">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>
    
5. <span data-ttu-id="05597-181">**고급** 탭을 선택 하 고 잘못 된 통화 음질 또는 연결 문제를 나타내는 노란색 및 빨간색 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-181">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="05597-182">각 통화 또는 모임에 대 한 세션 세부 정보에서 경미한 문제는 노란색으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-182">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="05597-183">노란색이 있는 것은 정상 범위를 벗어나므로 문제가 될 수 있지만 문제의 주요 원인이 되는 경우는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-183">If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="05597-184">무언가 빨간색 인 경우 중대 한 문제가 될 수 있으며,이 세션에 대 한 통화 품질이 좋지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-184">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
      
<span data-ttu-id="05597-185">드문 경우 지만 오디오 세션에 대 한 경험 치 데이터를 받지 못하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-185">In rare cases, Quality of Experience data isn't received for audio sessions.</span></span> <span data-ttu-id="05597-186">이 오류는 일반적으로 호출 손실 또는 클라이언트와의 연결이 종료 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-186">Often this is caused by the a dropped call or when the connection with the client terminates.</span></span> <span data-ttu-id="05597-187">이 문제가 발생 하면 세션 등급을 **사용할 수 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="05597-187">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="05597-188">체감 품질 (환경 품질) 데이터를 사용 하는 오디오 세션의 경우 다음 표에서는 세션을 **불량**으로 정규화 하는 주요 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-188">For audio sessions that do have Quality of Experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="05597-189">**문제**</span><span class="sxs-lookup"><span data-stu-id="05597-189">**Issue**</span></span>|<span data-ttu-id="05597-190">**지역을**</span><span class="sxs-lookup"><span data-stu-id="05597-190">**Area**</span></span>|<span data-ttu-id="05597-191">**설명**</span><span class="sxs-lookup"><span data-stu-id="05597-191">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="05597-192">전화 걸기 설정</span><span class="sxs-lookup"><span data-stu-id="05597-192">Call setup</span></span>  <br/> |<span data-ttu-id="05597-193">세션</span><span class="sxs-lookup"><span data-stu-id="05597-193">Session</span></span>  <br/> |<span data-ttu-id="05597-194">오류 코드 Ms-diag 20-29는 통화 설정이 실패 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05597-194">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="05597-195">사용자가 통화 또는 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-195">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="05597-196">오디오 네트워크에서 낮은 통화 분류</span><span class="sxs-lookup"><span data-stu-id="05597-196">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="05597-197">세션</span><span class="sxs-lookup"><span data-stu-id="05597-197">Session</span></span>  <br/> |<span data-ttu-id="05597-198">네트워크 품질 문제 (예: 패킷 손실, 지터, NMOS 성능 저하, RTT 또는 숨겨진 비율)가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-198">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span>  <br/> |
|<span data-ttu-id="05597-199">장치가 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="05597-199">Device not functioning</span></span>  <br/> |<span data-ttu-id="05597-200">장치</span><span class="sxs-lookup"><span data-stu-id="05597-200">Device</span></span>  <br/> | <span data-ttu-id="05597-201">장치가 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-201">A device isn't functioning correctly.</span></span> <span data-ttu-id="05597-202">장치 작동 비율이 아닌 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05597-202">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="05597-203">DeviceRenderNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="05597-203">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="05597-204">DeviceCaptureNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="05597-204">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="05597-205">관련 항목</span><span class="sxs-lookup"><span data-stu-id="05597-205">Related topics</span></span>

[<span data-ttu-id="05597-206">사용자별 통화 분석 설정</span><span class="sxs-lookup"><span data-stu-id="05597-206">Set up per-user call analytics</span></span>](set-up-call-analytics.md)



  
 
