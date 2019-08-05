---
title: 비즈니스용 Skype 서버에서 전화 접속 회의 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: '요약: 비즈니스용 Skype 서버에서 전화 접속 회의를 테스트 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: cd1192950ff7c8b609655d78bbc57dfdbc4c1710
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188922"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="20096-103">비즈니스용 Skype 서버에서 전화 접속 회의 테스트</span><span class="sxs-lookup"><span data-stu-id="20096-103">Test dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="20096-104">**요약:** 비즈니스용 Skype 서버에서 전화 접속 회의를 테스트 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="20096-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="20096-105">전화 접속 회의 구성을 최종적으로 확인 하면 전화 접속 회의 영역을 사용 하 여 액세스 번호와 전화 접속 회의 영역을 지정 하지 않은 액세스 번호를 검색 하는 다이얼 플랜을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20096-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="20096-106">또한 전화 접속 회의 설정 웹 페이지와 전화 접속 액세스 번호가 올바르게 작동 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="20096-107">액세스 번호에서 사용 하지 않는 전화 접속 회의 영역을 사용 하 여 다이얼 플랜 찾기</span><span class="sxs-lookup"><span data-stu-id="20096-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="20096-108">RTCUniversalServerAdmins 그룹의 구성원 또는 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="20096-109">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="20096-110">명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-110">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    <span data-ttu-id="20096-111">이 cmdlet은 액세스 번호에 사용 되지 않는 전화 접속 회의 영역이 있는 모든 다이얼 플랜을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="20096-112">자세한 내용은 [get-help를 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="20096-112">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="20096-113">할당 된 영역이 없는 액세스 번호 찾기</span><span class="sxs-lookup"><span data-stu-id="20096-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="20096-114">RTCUniversalServerAdmins 그룹의 구성원 또는 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="20096-115">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="20096-116">명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-116">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    <span data-ttu-id="20096-117">이 cmdlet은 지역과 연결 되지 않은 모든 전화 접속 회의 액세스 번호를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="20096-118">자세한 내용은 [get-help를 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="20096-118">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="20096-119">웹 페이지 테스트 및 번호 액세스</span><span class="sxs-lookup"><span data-stu-id="20096-119">Test webpage and access numbers</span></span>

<span data-ttu-id="20096-120">전화 접속 회의 설정 웹 페이지와 전화 접속 액세스 번호가 올바르게 작동 하는지 확인 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="20096-121">간단한 URL에 로그인 하 여 전화 접속 회의 설정 웹 페이지를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="20096-122">이 항목의 뒷부분에 나오는 스크립트를 실행 하 여 액세스 번호가 특정 풀에 대해 올바르게 작동 하는지 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-122">Test that access numbers work correctly for a specific pool by running the script later in this topic.</span></span> <span data-ttu-id="20096-123">이 스크립트는 access 번호에 대 한 통화를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-123">This script simulates calls to access numbers.</span></span> <span data-ttu-id="20096-124">이 스크립트를 사용 하기 위해 특정 풀에 호스팅되는 하나의 통합 커뮤니케이션 (UC) 클라이언트의 SIP 주소와 자격 증명이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-124">You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="20096-125">특정 풀에 대 한 액세스 번호를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="20096-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="20096-126">RTCUniversalServerAdmins 그룹의 구성원 또는 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="20096-127">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="20096-128">명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-128">Run the following at the command prompt:</span></span>
    
   ```
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    <span data-ttu-id="20096-129">결과 보고서에는 특정 진단 정보와 함께 성공 또는 실패가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20096-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="20096-130">-Verbose 플래그는 찾을 수 있는 액세스 번호 및 세부 정보에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="20096-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="20096-131">자세한 내용은 [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="20096-131">For more information, see [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
  

