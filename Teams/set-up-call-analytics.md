---
title: 통화 분석 설정
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
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
f1keywords: None
ms.custom:
- Reporting
description: 통화 분석을 설정 하 고 사용 하 여 비즈니스용 Skype 및 Microsoft 팀 통화 품질 문제를 식별 하 고 해결 합니다.
ms.openlocfilehash: 7a91bc0d8503d313ae3b3dfa7ddd32b6a8c5207a
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571252"
---
# <a name="set-up-call-analytics"></a><span data-ttu-id="25542-103">통화 분석 설정</span><span class="sxs-lookup"><span data-stu-id="25542-103">Set up Call Analytics</span></span>

<span data-ttu-id="25542-104">팀 또는 비즈니스용 Skype Online 관리자는 통화 분석을 사용 하 여 비즈니스용 Skype 및 Microsoft 팀 통화 품질 및 연결 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-104">As a Teams or Skype for Business Online admin, you can use Call Analytics to troubleshoot Skype for Business and Microsoft Teams call quality and connection problems.</span></span> <span data-ttu-id="25542-105">통화 분석에서 다음 기능을 설정 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-105">You may find it useful to set up the following capabilities in Call Analytics:</span></span>
  
- <span data-ttu-id="25542-106">헬프 데스크 지원 상담원 등의 다른 담당자가 통화 분석을 사용할 수 있도록 하는 권한을 설정 하 되, 나머지 Microsoft 팀 관리 센터에는 액세스 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-106">Set permissions that let other personnel, such as helpdesk agents, use Call Analytics, but prevent them from accessing the rest of the Microsoft Teams admin center.</span></span> 
    
- <span data-ttu-id="25542-107">Tsv 또는 .csv 데이터 파일을 업로드 하 여 분석을 호출 하는 데 빌드, 사이트 및 테 넌 트 정보를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-107">Add building, site, and tenant information to Call Analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="25542-108">**이제 Microsoft 팀 관리 센터에서 통화 분석을 사용할 수**있습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-108">**Call Analytics is now available in the Microsoft Teams admin center**.</span></span> <span data-ttu-id="25542-109">사용자의 모든 통화 정보 및 데이터를 보려면 **통화 기록** 탭을 사용 합니다. 이 작업을 수행 하려면 다음 중 하나를 수행 하 여 사용자의 프로필 페이지를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="25542-109">To see all the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by doing one of the following:</span></span>

- <span data-ttu-id="25542-110">대시보드에서 사용자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-110">Search for the user from the dashboard.</span></span>
  
   ![대시보드의 사용자 검색 스크린샷](media/set-up-call-analytics-image-1.png)

-  <span data-ttu-id="25542-112">왼쪽 탐색 모음에서 **사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-112">Select **Users** in the left navigation.</span></span>

   ![왼쪽 탐색의 스크린샷](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a><span data-ttu-id="25542-114">통화 분석 권한 설정</span><span class="sxs-lookup"><span data-stu-id="25542-114">Set Call Analytics permissions</span></span>
<a name="BKMK_SetCAPerms"></a>

<span data-ttu-id="25542-115">관리자는 통화 분석의 모든 기능에 대 한 모든 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-115">As the admin, you have full access to all the features of Call Analytics.</span></span> <span data-ttu-id="25542-116">또한 지원 직원에 게 Azure Active Directory 역할을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="25542-117">통화 분석을 제한 된 보기를 사용 해야 하는 사용자에 게 팀 의사 소통 지원 전문가 역할을 배정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-117">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="25542-118">통화 분석의 전체 기능에 대 한 액세스 권한이 필요한 사용자에 게 팀 의사 소통 지원 엔지니어 역할을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-118">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="25542-119">두 사용 권한 수준 모두에서 나머지 Microsoft 팀 관리 센터에 대 한 액세스를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-119">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="25542-120">커뮤니케이션 지원 전문가 역할은 계층 1 지원과 같으며 통신 지원 엔지니어 역할은 계층 2 지원과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-120">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="25542-121">팀 관리자 역할에 대 한 자세한 내용은 [Microsoft 팀 관리자 역할을 사용 하 여 팀 관리](using-admin-roles.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25542-121">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> 
  
<span data-ttu-id="25542-122">통신 지원 전문가는 기본 통화 품질 문제를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-122">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="25542-123">모임 관련 문제를 조사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-123">They don't investigate issues with meetings.</span></span> <span data-ttu-id="25542-124">그 대신 관련 정보를 수집한 다음 통신 지원 엔지니어로 승격 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-124">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="25542-125">통신 지원 엔지니어가 통신 지원 전문가에 게 서 숨겨진 자세한 콜 로그의 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-125">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="25542-126">다음 표에서는 통화 분석을 사용할 때 통신 지원 엔지니어가 제공 하는 정보에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-126">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

|<span data-ttu-id="25542-127">**작동이**</span><span class="sxs-lookup"><span data-stu-id="25542-127">**Activity**</span></span>|<span data-ttu-id="25542-128">**통화 분석의 정보**</span><span class="sxs-lookup"><span data-stu-id="25542-128">**Information in Call Analytics**</span></span>|<span data-ttu-id="25542-129">**통신 지원 전문가가 볼 수 있는 기능**</span><span class="sxs-lookup"><span data-stu-id="25542-129">**What the communications support specialist sees**</span></span>|<span data-ttu-id="25542-130">**통신 지원 엔지니어가 볼 수 있는 기능**</span><span class="sxs-lookup"><span data-stu-id="25542-130">**What the communications support engineer sees**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="25542-131">**전화가**</span><span class="sxs-lookup"><span data-stu-id="25542-131">**Calls**</span></span> <br/> |<span data-ttu-id="25542-132">발신자 이름</span><span class="sxs-lookup"><span data-stu-id="25542-132">Caller name</span></span>  <br/> |<span data-ttu-id="25542-133">에이전트에서 검색 한 사용자의 이름만</span><span class="sxs-lookup"><span data-stu-id="25542-133">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="25542-134">사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="25542-134">User name.</span></span>  <br/> |
||<span data-ttu-id="25542-135">받는 사람 이름</span><span class="sxs-lookup"><span data-stu-id="25542-135">Recipient name</span></span>  <br/> |<span data-ttu-id="25542-136">내부 사용자 또는 외부 사용자로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25542-136">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="25542-137">받는 사람 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="25542-137">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="25542-138">발신자 전화 번호</span><span class="sxs-lookup"><span data-stu-id="25542-138">Caller phone number</span></span>  <br/> |<span data-ttu-id="25542-139">마지막 세 자리 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25542-139">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="25542-140">예를 들어 15552823 \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="25542-140">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="25542-141">마지막 세 자리 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25542-141">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="25542-142">예를 들어 15552823 \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="25542-142">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="25542-143">받는 사람 전화 번호</span><span class="sxs-lookup"><span data-stu-id="25542-143">Recipient phone number</span></span>  <br/> |<span data-ttu-id="25542-144">마지막 세 자리 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25542-144">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="25542-145">예를 들어 15552823 \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="25542-145">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="25542-146">마지막 세 자리 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25542-146">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="25542-147">예를 들어 15552823 \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="25542-147">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="25542-148">**통화 정보** > **고급** 탭</span><span class="sxs-lookup"><span data-stu-id="25542-148">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="25542-149">정보가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-149">Information not shown.</span></span>  <br/> |<span data-ttu-id="25542-150">표시 되는 모든 정보 (예: 장치 이름, IP 주소, 서브넷 매핑 등)</span><span class="sxs-lookup"><span data-stu-id="25542-150">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="25542-151">**통화 정보** > **고급** > **디버그** 탭</span><span class="sxs-lookup"><span data-stu-id="25542-151">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="25542-152">정보가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-152">Information not shown.</span></span>  <br/> |<span data-ttu-id="25542-153">DNS 접미사 및 SSID와 같이 표시 되는 모든 정보</span><span class="sxs-lookup"><span data-stu-id="25542-153">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="25542-154">**Meeting**</span><span class="sxs-lookup"><span data-stu-id="25542-154">**Meetings**</span></span> <br/> |<span data-ttu-id="25542-155">참가자 이름</span><span class="sxs-lookup"><span data-stu-id="25542-155">Participant names</span></span>  <br/> |<span data-ttu-id="25542-156">에이전트에서 검색 한 사용자의 이름만</span><span class="sxs-lookup"><span data-stu-id="25542-156">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="25542-157">다른 참가자가 내부 사용자 또는 외부 사용자로 식별 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-157">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="25542-158">모든 이름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25542-158">All names shown.</span></span>  <br/> |
||<span data-ttu-id="25542-159">참가자 수</span><span class="sxs-lookup"><span data-stu-id="25542-159">Participant count</span></span>  <br/> |<span data-ttu-id="25542-160">참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="25542-160">Number of participants.</span></span>  <br/> |<span data-ttu-id="25542-161">참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="25542-161">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="25542-162">세션 정보</span><span class="sxs-lookup"><span data-stu-id="25542-162">Session details</span></span>  <br/> |<span data-ttu-id="25542-163">세션 정보가 예외와 함께 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25542-163">Session details shown with exceptions.</span></span> <span data-ttu-id="25542-164">에이전트가 검색 한 사용자의 이름만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25542-164">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="25542-165">다른 참가자가 내부 사용자 또는 외부 사용자로 식별 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-165">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="25542-166">별표 기호로 난독 처리 된 전화 번호의 마지막 세 자리입니다.</span><span class="sxs-lookup"><span data-stu-id="25542-166">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="25542-167">세션 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25542-167">Session details shown.</span></span> <span data-ttu-id="25542-168">사용자 이름 및 세션 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25542-168">User names and session details shown.</span></span> <span data-ttu-id="25542-169">별표 기호로 난독 처리 된 전화 번호의 마지막 세 자리입니다.</span><span class="sxs-lookup"><span data-stu-id="25542-169">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a><span data-ttu-id="25542-170">관리자 역할을 할당 하 여 사용 권한 설정</span><span class="sxs-lookup"><span data-stu-id="25542-170">Set up permissions by assigning admin roles</span></span>
<span data-ttu-id="25542-171"><a name="BKMK_SetUpTier"> </a></span><span class="sxs-lookup"><span data-stu-id="25542-171"></span></span>

<span data-ttu-id="25542-172">Azure Active Directory에서 관리 역할을 할당 하는 방법에 대 한 자세한 내용은 [Azure Active directory에서 역할 보기 및 지정](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25542-172">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="25542-173">Tsv 또는 .csv 파일을 업로드 하 여 빌드, 사이트 및 테 넌 트 정보 추가</span><span class="sxs-lookup"><span data-stu-id="25542-173">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>
<span data-ttu-id="25542-174"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="25542-174"></span></span>

<span data-ttu-id="25542-175">.Csv 또는 tsv 파일을 업로드 하 여 호출 분석에 빌드, 사이트 및 테 넌 트 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-175">You can add building, site, and tenant information to Call Analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="25542-176">모든 정보를 포함 하 여, Call Analytics는 IP 주소를 실제 위치로 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-176">With all this information, Call Analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="25542-177">사용자 또는 헬프데스크 상담원은 통화 문제를 파악 하는 데 도움이 되는이 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-177">You or helpdesk agents might find this information useful to help spot trends in call problems.</span></span> <span data-ttu-id="25542-178">예를 들어 동일한 건물에 비슷한 통화 품질 문제가 있는 사용자가 많은 경우</span><span class="sxs-lookup"><span data-stu-id="25542-178">For example, why are many users in the same building having similar call quality issues?</span></span> 

<span data-ttu-id="25542-179">팀과 비즈니스용 Skype 관리자 인 경우 팀 & 비즈니스용 Skype 통화 품질 대시보드를 사용 하 여 기존 데이터 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25542-179">If you're a Teams and Skype for Business admin, you can use an existing data file from the Teams & Skype for Business Call Quality Dashboard.</span></span> <span data-ttu-id="25542-180">먼저 통화 품질 대시보드에서 파일을 다운로드 한 다음이를 통화 분석에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-180">First, you download the file from Call Quality Dashboard, and then you upload it to Call Analytics.</span></span> 

- <span data-ttu-id="25542-181">기존 데이터 파일을 다운로드 하려면 **Microsoft 팀 관리 센터** > 에서**지금 업로드\*\*\*\*대시보드로** > 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-181">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="25542-182">**내 업로드** 목록에서 원하는 파일 옆에 있는 **다운로드** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-182">In the **My uploads** list, click **Download** next to the file you want.</span></span>

- <span data-ttu-id="25542-183">새 파일을 업로드 하려면 **Microsoft 팀 관리 센터** > **위치로**이동한 다음 **위치 데이터 업로드** 또는 **위치 데이터 바꾸기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="25542-183">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="25542-184">Tsv 또는 .csv 파일을 처음부터 만드는 경우에는 [테 넌 트 데이터 파일 형식 및 빌드 데이터 파일 구조](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25542-184">If you're creating the .tsv or .csv file from scratch, see [Tenant data file format and Building data file structure](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="25542-185">관련 항목</span><span class="sxs-lookup"><span data-stu-id="25542-185">Related topics</span></span>
<span data-ttu-id="25542-186"><a name="BKMK_UploadFiles"> </a></span><span class="sxs-lookup"><span data-stu-id="25542-186"></span></span>

[<span data-ttu-id="25542-187">통화 분석을 사용 하 여 통화 품질 저하 문제 해결</span><span class="sxs-lookup"><span data-stu-id="25542-187">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="25542-188">통화 분석 및 통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="25542-188">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
