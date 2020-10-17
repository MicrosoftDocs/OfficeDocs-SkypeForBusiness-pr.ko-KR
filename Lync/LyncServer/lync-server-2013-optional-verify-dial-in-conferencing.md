---
title: 'Lync Server 2013: (선택 사항) 전화 접속 회의 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebfebd5dceff50d7d4b7647c7709bb88b7c1fa8e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530775"
---
# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="5ac0e-102">반드시 Lync Server 2013에서 전화 접속 회의 확인</span><span class="sxs-lookup"><span data-stu-id="5ac0e-102">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ac0e-103">_**마지막으로 수정 된 항목:** 2011-01-21_</span><span class="sxs-lookup"><span data-stu-id="5ac0e-103">_**Topic Last Modified:** 2011-01-21_</span></span>

<span data-ttu-id="5ac0e-104">전화 접속 회의 설정 웹 페이지와 전화 접속 액세스 번호가 올바르게 작동하는지 확인하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac0e-104">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>

  - <span data-ttu-id="5ac0e-105">단순 URL에 로그인하여 전화 접속 회의 설정 웹 페이지를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac0e-105">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>

  - <span data-ttu-id="5ac0e-p101">이 항목 뒷부분에 나와 있는 스크립트를 실행하여 특정 풀에 대해 액세스 번호가 올바르게 작동하는지 테스트합니다. 이 스크립트는 액세스 번호에 대한 호출을 시뮬레이트합니다. 이 스크립트를 사용하려면 특정 풀에서 호스팅되는 단일 UC(통합 통신) 클라이언트의 SIP 주소 및 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac0e-p101">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>

<span data-ttu-id="5ac0e-109">이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5ac0e-109">This step is optional.</span></span>

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="5ac0e-110">특정 풀에 대한 액세스 번호를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="5ac0e-110">To test access numbers for a specific pool</span></span>

1.  <span data-ttu-id="5ac0e-111">RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac0e-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="5ac0e-112">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac0e-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5ac0e-113">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac0e-113">Run the following at the command prompt:</span></span>
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    <span data-ttu-id="5ac0e-p102">결과 보고서에는 성공 또는 실패와 특정 진단 정보가 표시됩니다. –Verbose 플래그는 발견된 액세스 번호의 수와 각 번호의 세부 사항에 대해 더욱 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac0e-p102">The resulting report shows either Success or Failure, along with specific diagnostic information. The –Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

