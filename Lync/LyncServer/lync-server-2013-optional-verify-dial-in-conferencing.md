---
title: 'Lync Server 2013: (선택 사항) 전화 접속 회의 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70a0b18ce596e4799c82a2843b5f3a008b5cb285
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="3b006-102">(선택 사항) Lync Server 2013에서 전화 접속 회의 확인</span><span class="sxs-lookup"><span data-stu-id="3b006-102">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b006-103">_**마지막으로 수정한 주제:** 2011-01-21_</span><span class="sxs-lookup"><span data-stu-id="3b006-103">_**Topic Last Modified:** 2011-01-21_</span></span>

<span data-ttu-id="3b006-104">전화 접속 회의 설정 웹 페이지와 전화 접속 액세스 번호가 올바르게 작동 하는지 확인 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b006-104">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>

  - <span data-ttu-id="3b006-105">간단한 URL에 로그인 하 여 전화 접속 회의 설정 웹 페이지를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b006-105">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>

  - <span data-ttu-id="3b006-106">이 항목의 뒷부분에 나오는 스크립트를 실행 하 여 액세스 번호가 특정 풀에 대해 올바르게 작동 하는지 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b006-106">Test that access numbers work correctly for a specific pool by running the script later in this topic.</span></span> <span data-ttu-id="3b006-107">이 스크립트는 access 번호에 대 한 통화를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3b006-107">This script simulates calls to access numbers.</span></span> <span data-ttu-id="3b006-108">이 스크립트를 사용 하기 위해 특정 풀에 호스팅되는 하나의 통합 커뮤니케이션 (UC) 클라이언트의 SIP 주소와 자격 증명이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b006-108">You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>

<span data-ttu-id="3b006-109">이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3b006-109">This step is optional.</span></span>

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="3b006-110">특정 풀에 대 한 액세스 번호를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="3b006-110">To test access numbers for a specific pool</span></span>

1.  <span data-ttu-id="3b006-111">RTCUniversalServerAdmins 그룹의 구성원 또는 **Cs-serveradministrator** 또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b006-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="3b006-112">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b006-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3b006-113">명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b006-113">Run the following at the command prompt:</span></span>
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    <span data-ttu-id="3b006-114">결과 보고서에는 특정 진단 정보와 함께 성공 또는 실패가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b006-114">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="3b006-115">– Verbose 플래그는 찾을 수 있는 액세스 번호 및 세부 정보에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b006-115">The –Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

