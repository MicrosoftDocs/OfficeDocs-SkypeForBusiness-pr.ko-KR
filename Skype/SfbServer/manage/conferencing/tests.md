---
title: 비즈니스용 Skype 서버에서 전화 접속 회의 테스트
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: '요약: 비즈니스용 Skype 서버에서 전화 접속 회의를 테스트하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 214ec05c49072825e6a8744cb92db66d864e3d34
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827938"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="dba8d-103">비즈니스용 Skype 서버에서 전화 접속 회의 테스트</span><span class="sxs-lookup"><span data-stu-id="dba8d-103">Test dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="dba8d-104">**요약:** 비즈니스용 Skype 서버에서 전화 접속 회의를 테스트하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="dba8d-105">전화 접속 회의 구성의 최종 확인 작업으로 액세스 번호에서 사용되지 않은 전화 접속 회의 지역이 포함된 다이얼 플랜 및 전화 접속 회의 지역이 할당되지 않은 액세스 번호를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="dba8d-106">또한 전화 접속 회의 설정 웹 페이지와 전화 접속 액세스 번호가 올바르게 작동하고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="dba8d-107">액세스 번호에서 사용되지 않는 전화 접속 회의 지역이 있는 다이얼 플랜 찾기</span><span class="sxs-lookup"><span data-stu-id="dba8d-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="dba8d-108">RTCUniversalServerAdmins 그룹의 구성원이나 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="dba8d-109">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dba8d-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dba8d-110">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-110">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    <span data-ttu-id="dba8d-111">이 cmdlet은 액세스 번호에서 사용되지 않은 전화 접속 회의 지역이 포함된 모든 다이얼 플랜을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="dba8d-112">자세한 내용은 [Get-CsDialInConferencingAccessNumber를](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dba8d-112">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="dba8d-113">할당된 지역이 없는 액세스 번호 찾기</span><span class="sxs-lookup"><span data-stu-id="dba8d-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="dba8d-114">RTCUniversalServerAdmins 그룹의 구성원이나 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="dba8d-115">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dba8d-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dba8d-116">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-116">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    <span data-ttu-id="dba8d-117">이 cmdlet은 지역과 연관되지 않은 모든 전화 접속 회의 액세스 번호를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="dba8d-118">자세한 내용은 [Get-CsDialInConferencingAccessNumber를](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dba8d-118">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="dba8d-119">테스트 웹 페이지 및 액세스 번호</span><span class="sxs-lookup"><span data-stu-id="dba8d-119">Test webpage and access numbers</span></span>

<span data-ttu-id="dba8d-120">전화 접속 회의 설정 웹 페이지와 전화 접속 액세스 번호가 올바르게 작동하는지 확인하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="dba8d-121">단순 URL에 로그인하여 전화 접속 회의 설정 웹 페이지를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="dba8d-p102">이 항목 뒷부분에 나와 있는 스크립트를 실행하여 특정 풀에 대해 액세스 번호가 올바르게 작동하는지 테스트합니다. 이 스크립트는 액세스 번호에 대한 호출을 시뮬레이트합니다. 이 스크립트를 사용하려면 특정 풀에서 호스팅되는 단일 UC(통합 통신) 클라이언트의 SIP 주소 및 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-p102">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="dba8d-125">특정 풀에 대한 액세스 번호를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="dba8d-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="dba8d-126">RTCUniversalServerAdmins 그룹의 구성원이나 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="dba8d-127">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dba8d-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dba8d-128">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-128">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    <span data-ttu-id="dba8d-129">결과 보고서에는 성공 또는 실패와 특정 진단 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="dba8d-130">-Verbose 플래그는 발견된 액세스 번호 수와 해당 번호에 대한 세부 정보에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dba8d-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="dba8d-131">자세한 내용은 [Test-CsDialInConferencing을 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="dba8d-131">For more information, see [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
  

