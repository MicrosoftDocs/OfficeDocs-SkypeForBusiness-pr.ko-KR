---
title: 통화 분석을 사용하여 통화 품질 불량 문제 해결
ms.author: serdars
author: SerdarSoysal
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
description: 장치, 네트워크 및 연결에 대한 사용자당 통화 분석 세부 정보를 사용하여 Microsoft Teams 통화 및 모임의 사용자 문제를 해결합니다.
ms.openlocfilehash: 8bee41e79f2610adcb9a1fed3f895c728526f5ea
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583627"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="560f5-103">통화 분석을 사용하여 통화 품질 불량 문제 해결</span><span class="sxs-lookup"><span data-stu-id="560f5-103">Use call analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="560f5-104">이 문서에서는 Teams 관리자 또는 Teams 통신 지원 전문가 또는 엔지니어인 경우 통화 분석을 사용하여 개별 사용자의 Microsoft Teams 통화 또는 모임 품질 문제를 해결하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-104">This article explains how to use call analytics to troubleshoot poor Microsoft Teams call or meeting quality for individual users if you're a Teams admin or a Teams communications support specialist or engineer.</span></span>


  
## <a name="call-analytics-permissions"></a><span data-ttu-id="560f5-105">Analytics 사용 권한 호출</span><span class="sxs-lookup"><span data-stu-id="560f5-105">Call Analytics permissions</span></span>

<span data-ttu-id="560f5-106">이 문서에서는 호출 분석을 이미 설정했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-106">This article assumes that you've already set up call analytics.</span></span> <span data-ttu-id="560f5-107">아직 없는 경우 Teams에 대한 [통화 분석 설정을 읽어 읽습니다.](set-up-call-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="560f5-107">If you haven't, read [Set up call analytics for Teams](set-up-call-analytics.md).</span></span>

## <a name="introduction-to-call-analytics"></a><span data-ttu-id="560f5-108">호출 분석 소개</span><span class="sxs-lookup"><span data-stu-id="560f5-108">Introduction to call analytics</span></span>

<span data-ttu-id="560f5-109">통화 분석은 Office 365 계정의 각 사용자에 대한 Teams 통화 및 모임에 대한 자세한 정보를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-109">Call analytics shows detailed information about Teams calls and meetings for each user in your Office 365 account.</span></span> <span data-ttu-id="560f5-110">여기에는 장치, 네트워크, 연결 및 통화 품질에 대한 정보가 포함됩니다(이러한 기능 중 어느 것이든 통화 또는 모임 품질이 좋지 않은 요인이 될 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="560f5-110">It includes information about devices, networks, connectivity, and call quality (any of these can be a factor in poor call or meeting quality).</span></span> <span data-ttu-id="560f5-111">건물, 사이트 및 테넌트 정보를 업로드하는 경우 각 통화 및 모임에 대해 이 정보도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-111">If you upload building, site, and tenant information, this information will also be shown for each call and meeting.</span></span> <span data-ttu-id="560f5-112">통화 분석을 사용하여 사용자가 통화 또는 모임 환경이 좋지 않은 이유를 알아내기 위해 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-112">Use call analytics to help you figure out why a user had a poor call or meeting experience.</span></span>

<span data-ttu-id="560f5-113">통화 분석은 한 참가자에서 두 번째 참가자까지 통화 또는 모임의 각 레그를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-113">Call analytics shows you each leg of a call or meeting - for example, from one participant to a second participant.</span></span> <span data-ttu-id="560f5-114">Teams 관리자는 이러한 세부 정보를 분석하여 문제 영역을 격리하고 품질이 나쁜 근본 원인을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-114">By analyzing these details, a Teams admin can isolate problem areas and identify the root cause for poor quality.</span></span>
   
<span data-ttu-id="560f5-115">Teams 관리자는 각 사용자에 대한 모든 통화 분석 데이터에 대한 모든 액세스 권한을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-115">As the Teams admin, you get full access to all call analytics data for each user.</span></span> <span data-ttu-id="560f5-116">또한 지원 담당자에게 Azure Active Directory 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="560f5-117">이러한 역할에 대한 자세한 내용은 지원 및 기술 지원 기술 지원 직원에게 권한 [부여를 읽어 보아야 합니다.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)</span><span class="sxs-lookup"><span data-stu-id="560f5-117">To learn more about these roles, read [Give permission to support and helpdesk staff](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).</span></span> <span data-ttu-id="560f5-118">각 Teams 지원 역할의 역할을 놓치지 [마세요.](#what-does-each-teams-support-role-do)</span><span class="sxs-lookup"><span data-stu-id="560f5-118">Don't miss [What does each Teams Support role do?](#what-does-each-teams-support-role-do) below.</span></span>

## <a name="where-to-find-per-user-call-analytics"></a><span data-ttu-id="560f5-119">사용자당 호출 분석을 찾을 수 있는 위치</span><span class="sxs-lookup"><span data-stu-id="560f5-119">Where to find per-user call analytics</span></span>

<span data-ttu-id="560f5-120">사용자의 모든 통화 정보와 데이터를 표시하려면 Teams 관리 [센터로 이동하세요.](https://admin.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="560f5-120">To see all call information and data for a user, go to the [Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="560f5-121">사용자 **아래에서** 사용자를 선택한 다음  사용자의 프로필 페이지에서 통화 기록 탭을 니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-121">Under **Users**, select a user and then open the **Call History** tab on the user's profile page.</span></span> <span data-ttu-id="560f5-122">여기에서 지난 30일 동안 해당 사용자의 모든 통화 및 모임을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-122">Here you'll find all calls and meetings for that user for the last 30 days.</span></span>

![모든 분석 사용자 데이터의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="560f5-124">자세한 미디어 및 네트워킹 통계를 포함하여 특정 세션에 대한 추가 정보를 얻려면 세션을 클릭하여 세부 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-124">To get additional information about a given session, including detailed media and networking statistics, click a session to see the details.</span></span>

![호출 분석 사용자 세션 데이터의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a><span data-ttu-id="560f5-126">각 Teams 지원 역할은 무엇을 하나요?</span><span class="sxs-lookup"><span data-stu-id="560f5-126">What does each Teams Support role do?</span></span>

<span data-ttu-id="560f5-127">**Teams 통신 지원 전문가(계층** 1 지원)는 기본적인 통화 품질 문제를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-127">The **Teams communications support specialist** (Tier 1 support) handles basic call-quality problems.</span></span> <span data-ttu-id="560f5-128">모임 관련 문제는 조사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-128">They don't investigate issues with meetings.</span></span> <span data-ttu-id="560f5-129">대신 관련 정보를 수집한 다음 통신 지원 엔지니어에게 에스컬레이터합니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-129">Instead, they collect related information and then escalate to a communications support engineer.</span></span> 

<span data-ttu-id="560f5-130">**Teams 통신 지원** 엔지니어(계층 2 지원)는 Teams 통신 지원 전문가로부터 숨겨져 있는 자세한 통화 로그의 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-130">The **Teams communications support engineer** (Tier 2 support) sees information in detailed call logs that are hidden from the Teams communications support specialist.</span></span> <span data-ttu-id="560f5-131">아래 표에는 각 Teams 통신 지원 역할에 사용할 수 있는 정보가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-131">The table below lists the information available to each Teams communication support role.</span></span>

<span data-ttu-id="560f5-132">다음 표에서는 각 통신 지원 역할에 사용할 수 있는 사용자당 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-132">The following table tells you what per-user information is available for each communications support role.</span></span>

|<span data-ttu-id="560f5-133">**활동**</span><span class="sxs-lookup"><span data-stu-id="560f5-133">**Activity**</span></span>|<span data-ttu-id="560f5-134">**정보**</span><span class="sxs-lookup"><span data-stu-id="560f5-134">**Information**</span></span>|<span data-ttu-id="560f5-135">통신 지원 전문가가 **보는** 정보</span><span class="sxs-lookup"><span data-stu-id="560f5-135">What the communications support **specialist** sees</span></span>|<span data-ttu-id="560f5-136">통신 지원 엔지니어가 **보는** 정보</span><span class="sxs-lookup"><span data-stu-id="560f5-136">What the communications support **engineer** sees</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="560f5-137">**통화**</span><span class="sxs-lookup"><span data-stu-id="560f5-137">**Calls**</span></span> <br/> |<span data-ttu-id="560f5-138">호출자 이름</span><span class="sxs-lookup"><span data-stu-id="560f5-138">Caller name</span></span>  <br/> |<span data-ttu-id="560f5-139">에이전트가 검색한 사용자의 이름만</span><span class="sxs-lookup"><span data-stu-id="560f5-139">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="560f5-140">사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-140">User name.</span></span>  <br/> |
||<span data-ttu-id="560f5-141">받는 사람 이름</span><span class="sxs-lookup"><span data-stu-id="560f5-141">Recipient name</span></span>  <br/> |<span data-ttu-id="560f5-142">내부 사용자 또는 외부 사용자로 표시</span><span class="sxs-lookup"><span data-stu-id="560f5-142">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="560f5-143">받는 사람 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-143">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="560f5-144">호출자 전화 번호</span><span class="sxs-lookup"><span data-stu-id="560f5-144">Caller phone number</span></span>  <br/> |<span data-ttu-id="560f5-145">마지막 3자리를 제외한 전체 전화 번호는 불일치가 났습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-145">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="560f5-146">예를 들어 15552823\*\*\*입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-146">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="560f5-147">마지막 3자리를 제외한 전체 전화 번호는 불일치가 났습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-147">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="560f5-148">예를 들어 15552823\*\*\*입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-148">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="560f5-149">받는 사람 전화 번호</span><span class="sxs-lookup"><span data-stu-id="560f5-149">Recipient phone number</span></span>  <br/> |<span data-ttu-id="560f5-150">마지막 3자리를 제외한 전체 전화 번호는 불일치가 났습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-150">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="560f5-151">예를 들어 15552823\*\*\*입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-151">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="560f5-152">마지막 3자리를 제외한 전체 전화 번호는 불일치가 났습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-152">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="560f5-153">예를 들어 15552823\*\*\*입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-153">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="560f5-154">**통화 세부 정보**  >  **고급** 탭</span><span class="sxs-lookup"><span data-stu-id="560f5-154">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="560f5-155">정보가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-155">Information not shown.</span></span>  <br/> |<span data-ttu-id="560f5-156">디바이스 이름, IP 주소, 서브넷 매핑 등 표시되는 모든 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-156">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="560f5-157">**통화 세부 정보**  >  **고급**  >  **디버그** 탭</span><span class="sxs-lookup"><span data-stu-id="560f5-157">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="560f5-158">정보가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-158">Information not shown.</span></span>  <br/> |<span data-ttu-id="560f5-159">DNS 접미사 및 SSID와 같은 모든 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-159">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="560f5-160">**모임**</span><span class="sxs-lookup"><span data-stu-id="560f5-160">**Meetings**</span></span> <br/> |<span data-ttu-id="560f5-161">참가자 이름</span><span class="sxs-lookup"><span data-stu-id="560f5-161">Participant names</span></span>  <br/> |<span data-ttu-id="560f5-162">에이전트가 검색한 사용자의 이름만</span><span class="sxs-lookup"><span data-stu-id="560f5-162">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="560f5-163">내부 사용자 또는 외부 사용자로 식별된 다른 참가자.</span><span class="sxs-lookup"><span data-stu-id="560f5-163">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="560f5-164">표시된 모든 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-164">All names shown.</span></span>  <br/> |
||<span data-ttu-id="560f5-165">참가자 수</span><span class="sxs-lookup"><span data-stu-id="560f5-165">Participant count</span></span>  <br/> |<span data-ttu-id="560f5-166">참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-166">Number of participants.</span></span>  <br/> |<span data-ttu-id="560f5-167">참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-167">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="560f5-168">세션 세부 정보</span><span class="sxs-lookup"><span data-stu-id="560f5-168">Session details</span></span>  <br/> |<span data-ttu-id="560f5-169">예외와 함께 표시된 세션 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-169">Session details shown with exceptions.</span></span> <span data-ttu-id="560f5-170">에이전트가 검색된 사용자의 이름만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-170">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="560f5-171">내부 사용자 또는 외부 사용자로 식별된 다른 참가자.</span><span class="sxs-lookup"><span data-stu-id="560f5-171">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="560f5-172">마지막 3자리 전화 번호가 난수로 표시된 경우,</span><span class="sxs-lookup"><span data-stu-id="560f5-172">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="560f5-173">표시된 세션 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-173">Session details shown.</span></span> <span data-ttu-id="560f5-174">표시된 사용자 이름 및 세션 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-174">User names and session details shown.</span></span> <span data-ttu-id="560f5-175">마지막 3자리 전화 번호가 난수로 표시된 경우,</span><span class="sxs-lookup"><span data-stu-id="560f5-175">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a><span data-ttu-id="560f5-176">사용자 통화 품질 문제 해결</span><span class="sxs-lookup"><span data-stu-id="560f5-176">Troubleshoot user call quality problems</span></span> 

1. <span data-ttu-id="560f5-177">Teams 관리 센터를 열고 Teams 통신 지원 또는 Teams 관리자 자격 증명으로 https://admin.teams.microsoft.com) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-177">Open the Teams admin center (https://admin.teams.microsoft.com) and sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="560f5-178">대시보드의  **사용자** 검색에서 호출 문제를 해결하려는 사용자의 이름 또는 SIP 주소를 입력하거나 사용자  보기를 선택하여 사용자 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-178">On the **Dashboard**, in **User Search**, start typing either the name or SIP address of the user whose calls you want to troubleshoot, or select **View users** to see a list of users.</span></span>

3. <span data-ttu-id="560f5-179">목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-179">Select the user from the list.</span></span>

4. <span data-ttu-id="560f5-180">통화 **기록을** 선택한 다음 문제 해결을 위해 통화 또는 모임을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-180">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>
    
5. <span data-ttu-id="560f5-181">고급 **탭을** 선택한 다음 통화 품질 또는 연결 문제를 나타내는 노란색 및 빨간색 항목을 찾아 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-181">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="560f5-182">각 통화 또는 모임에 대한 세션 세부 정보에서 사소한 문제가 노란색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-182">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="560f5-183">노란색이면 정상 범위를 밖에 있으며 문제의 원인이 될 수 있지만 문제의 주요 원인일 가능성은 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-183">If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="560f5-184">빨간색이면 심각한 문제로, 이 세션의 통화 품질이 좋지 않은 주요 원인일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-184">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
      
<span data-ttu-id="560f5-185">드문 경우지만 오디오 세션에 대한 경험 품질 데이터는 수신되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-185">In rare cases, Quality of Experience data isn't received for audio sessions.</span></span> <span data-ttu-id="560f5-186">호출이 끊어지거나 클라이언트와의 연결이 종료되는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-186">Often this is caused by the a dropped call or when the connection with the client terminates.</span></span> <span data-ttu-id="560f5-187">이 경우 세션 등급을 사용할 **수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="560f5-187">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="560f5-188">QoE(경험 품질) 데이터가 있는 오디오 세션의 경우 다음 표에서는 세션을 불량으로 한정하는 주요 문제에 **대해 설명하고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="560f5-188">For audio sessions that do have Quality of Experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="560f5-189">**문제**</span><span class="sxs-lookup"><span data-stu-id="560f5-189">**Issue**</span></span>|<span data-ttu-id="560f5-190">**영역**</span><span class="sxs-lookup"><span data-stu-id="560f5-190">**Area**</span></span>|<span data-ttu-id="560f5-191">**설명**</span><span class="sxs-lookup"><span data-stu-id="560f5-191">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="560f5-192">통화 설정</span><span class="sxs-lookup"><span data-stu-id="560f5-192">Call setup</span></span>  <br/> |<span data-ttu-id="560f5-193">세션</span><span class="sxs-lookup"><span data-stu-id="560f5-193">Session</span></span>  <br/> |<span data-ttu-id="560f5-194">오류 코드 Ms-diag 20-29는 호출 설정이 실패했다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-194">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="560f5-195">사용자가 통화 또는 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-195">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="560f5-196">오디오 네트워크 분류 불량 통화</span><span class="sxs-lookup"><span data-stu-id="560f5-196">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="560f5-197">세션</span><span class="sxs-lookup"><span data-stu-id="560f5-197">Session</span></span>  <br/> |<span data-ttu-id="560f5-198">네트워크 품질 문제(예: 패킷 손실, 지터, NMOS 성능 저하, RTT 또는 은신 비율)가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-198">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span>  <br/> |
|<span data-ttu-id="560f5-199">디바이스가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-199">Device not functioning</span></span>  <br/> |<span data-ttu-id="560f5-200">장치</span><span class="sxs-lookup"><span data-stu-id="560f5-200">Device</span></span>  <br/> | <span data-ttu-id="560f5-201">디바이스가 올바르게 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="560f5-201">A device isn't functioning correctly.</span></span> <span data-ttu-id="560f5-202">디바이스가 작동하지 않는 비율은</span><span class="sxs-lookup"><span data-stu-id="560f5-202">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="560f5-203">DeviceRenderNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="560f5-203">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="560f5-204">DeviceCaptureNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="560f5-204">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="560f5-205">관련 항목</span><span class="sxs-lookup"><span data-stu-id="560f5-205">Related topics</span></span>

[<span data-ttu-id="560f5-206">사용자당 호출 분석 설정</span><span class="sxs-lookup"><span data-stu-id="560f5-206">Set up per-user call analytics</span></span>](set-up-call-analytics.md)



  
 
