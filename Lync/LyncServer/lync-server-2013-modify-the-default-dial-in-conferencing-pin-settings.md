---
title: 'Lync Server 2013: 기본 전화 접속 회의 PIN 설정 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default dial-in conferencing PIN settings
ms:assetid: 2d110e94-ad29-4755-b17f-d8c2da9b78a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425780(v=OCS.15)
ms:contentKeyID: 48183712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee196fae24ba4a6b7bf8e0ede0bbc0b35a7b3fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-dial-in-conferencing-pin-settings-in-lync-server-2013"></a><span data-ttu-id="0e0dd-102">Lync Server 2013에서 기본 전화 접속 회의 PIN 설정 수정</span><span class="sxs-lookup"><span data-stu-id="0e0dd-102">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e0dd-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="0e0dd-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="0e0dd-104">글로벌 PIN 정책은 포리스트 수준의 전화 접속 회의 핀에 대 한 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-104">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="0e0dd-105">전역 전화 접속 회의 PIN 정책을 수정 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-105">Follow these steps to modify the global dial-in conferencing PIN policy.</span></span> <span data-ttu-id="0e0dd-106">사이트 또는 사용자 수준에서 전화 접속 회의 PIN 정책을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [사이트 또는 사용자 그룹에 대 한 Lync Server 2013에서 전화 접속 회의 pin 설정 만들기 또는 수정을](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-106">For details about creating or modifying a dial-in conferencing PIN policy at the site or user level, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

<div>

## <a name="to-modify-the-global-pin-policy"></a><span data-ttu-id="0e0dd-107">글로벌 PIN 정책 수정</span><span class="sxs-lookup"><span data-stu-id="0e0dd-107">To modify the global PIN policy</span></span>

1.  <span data-ttu-id="0e0dd-108">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="0e0dd-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0e0dd-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0e0dd-111">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-111">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="0e0dd-112">**고정 정책** 페이지에서 **전역** 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-112">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0e0dd-113">**Pin 편집 정책**에서 **최소 pin 길이**에 허용 하려는 최소 pin 길이를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-113">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="0e0dd-114">기본 최소 길이는 다섯 자리입니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-114">The default minimum length is five digits.</span></span>

6.  <span data-ttu-id="0e0dd-115">사용자가 잠길 때까지 허용 되는 최대 로그온 시도 횟수를 지정할 수 있으려면 **최대 로그온 시도 수 지정** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-115">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="0e0dd-116">이 옵션을 선택 하지 않으면 허용 되는 최대 시도 수는 PIN 길이에 따라 자동으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-116">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="0e0dd-117">기본적으로 최대 시도 횟수는 자동으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-117">By default, the maximum number of attempts is automatically determined.</span></span>

7.  <span data-ttu-id="0e0dd-118">최대 로그온 시도 **횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도**에서 허용 하려는 최대 로그온 시도 횟수를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

8.  <span data-ttu-id="0e0dd-119">핀이 만료 되 게 하려면 **PIN 만료 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-119">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="0e0dd-120">이 옵션을 선택 하지 않으면 Pin이 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-120">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="0e0dd-121">기본적으로 Pin은 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-121">By default, PINs never expire.</span></span>

9.  <span data-ttu-id="0e0dd-122">**Pin 만료 사용** 확인란을 선택한 경우 **pin이 (일) 후에 만료**되는 경우 해당 pin이 만료 되는 일 수를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

10. <span data-ttu-id="0e0dd-123">**Pin 기록 개수**에 사용자가 PIN을 다시 사용할 수 있으려면 먼저 사용자가 만들어야 하는 pin의 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-123">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="0e0dd-124">기본적으로 사용자는 Pin을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-124">By default, users can reuse their PINs.</span></span>

11. <span data-ttu-id="0e0dd-125">일련 번호와 반복 되는 숫자 집합 등의 일반 숫자 패턴을 허용 하려면 **일반 패턴 허용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-125">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="0e0dd-126">이 옵션을 선택 하지 않으면 복잡 한 자릿수의 숫자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-126">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="0e0dd-127">기본적으로 복잡 한 자릿수 패턴만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-127">By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0e0dd-128">공통 패턴을 허용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-128">We recommend that you do not allow common patterns.</span></span>

    
    </div>

12. <span data-ttu-id="0e0dd-129">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0e0dd-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

