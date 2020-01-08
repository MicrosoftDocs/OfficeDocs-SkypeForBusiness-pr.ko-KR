---
title: 'Lync Server 2013: 사이트 또는 사용자 그룹에 대한 전화 접속 회의 PIN 설정 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2af1dc8e3f9bde06e799c758b711f94b7c0e6411
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a><span data-ttu-id="f8758-102">Lync Server 2013에서 사이트 또는 사용자 그룹에 대한 전화 접속 회의 PIN 설정 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="f8758-102">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8758-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f8758-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f8758-104">다음 단계에 따라 사용자 수준 또는 사이트 수준의 전화 접속 회의 PIN (개인 식별 번호) 정책을 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-104">Follow these steps to create or modify a user-level or a site-level dial-in conferencing personal identification number (PIN) policy.</span></span> <span data-ttu-id="f8758-105">글로벌 PIN 정책을 변경 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 기본 전화 접속 회의 PIN 설정 수정을](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8758-105">For details about how to change the global PIN policy, see [Modify the default dial-in conferencing PIN settings in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="f8758-106">사용자 또는 사이트 PIN 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="f8758-106">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="f8758-107">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="f8758-108">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8758-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8758-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8758-110">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="f8758-111">**고정 정책** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-111">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="f8758-112">사용자 수준 정책을 만들려면 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-112">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="f8758-113">**새 PIN 정책의** **이름**에 정책을 설명 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-113">In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="f8758-114">사이트 수준 정책을 만들려면 **사이트 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-114">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="f8758-115">사이트 검색 **선택** 필드에 정책을 만들려는 사이트 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-115">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="f8758-116">사이트 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-116">In the list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="f8758-117">**설명** 필드에 고정 정책에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-117">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="f8758-118">**최소 pin 길이** 필드에 허용 하려는 최소 pin 길이를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-118">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="f8758-119">기본 최소 길이는 다섯 자리입니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-119">The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="f8758-120">사용자가 잠길 때까지 허용 되는 최대 로그온 시도 횟수를 지정할 수 있으려면 **최대 로그온 시도 수 지정** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-120">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="f8758-121">이 옵션을 선택 하지 않으면 허용 되는 최대 시도 수는 PIN 길이에 따라 자동으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-121">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="f8758-122">기본적으로 최대 시도 횟수는 자동으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-122">By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="f8758-123">최대 로그온 시도 **횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도**에서 허용 하려는 최대 로그온 시도 횟수를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-123">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="f8758-124">핀이 만료 되 게 하려면 **PIN 만료 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-124">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="f8758-125">이 옵션을 선택 하지 않으면 Pin이 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-125">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="f8758-126">기본적으로 Pin은 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-126">By default, PINs never expire.</span></span>

10. <span data-ttu-id="f8758-127">**Pin 만료 사용** 확인란을 선택한 경우 **pin이 (일) 후에 만료**되는 경우 해당 pin이 만료 되는 일 수를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-127">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="f8758-128">**Pin 기록 개수**에 사용자가 PIN을 다시 사용할 수 있으려면 먼저 사용자가 만들어야 하는 pin의 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-128">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="f8758-129">기본적으로 사용자는 Pin을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-129">By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="f8758-130">일련 번호와 반복 되는 숫자 집합 등의 일반 숫자 패턴을 허용 하려면 **일반 패턴 허용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-130">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="f8758-131">이 옵션을 선택 하지 않으면 복잡 한 자릿수의 숫자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-131">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="f8758-132">기본적으로 복잡 한 자릿수 패턴만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-132">By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="f8758-133">공통 패턴을 허용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-133">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="f8758-134">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a><span data-ttu-id="f8758-135">사용자 또는 사이트 PIN 정책을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="f8758-135">To change a user or site PIN policy</span></span>

1.  <span data-ttu-id="f8758-136">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="f8758-137">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8758-138">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8758-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8758-139">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-139">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="f8758-140">**고정 정책** 페이지에서 변경 하려는 pin 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-140">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f8758-141">**PIN 정책 편집**에서 정책 설정을 수정 합니다 (수정할 수 없는 정책 이름을 제외한).</span><span class="sxs-lookup"><span data-stu-id="f8758-141">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>

6.  <span data-ttu-id="f8758-142">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f8758-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

