---
title: 'Lync Server 2013: 사이트 또는 사용자 그룹에 대 한 전화 접속 회의 PIN 설정 만들기 또는 수정'
description: 'Lync Server 2013: 사이트 또는 사용자 그룹에 대 한 전화 접속 회의 PIN 설정을 만들거나 수정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9150daad55c7c18cbee25aedfccd3a5c100a2131
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546944"
---
# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a><span data-ttu-id="eaa27-103">Lync Server 2013에서 사이트 또는 사용자 그룹에 대 한 전화 접속 회의 PIN 설정 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="eaa27-103">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaa27-104">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="eaa27-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="eaa27-105">다음 단계에 따라 사용자 수준 또는 사이트 수준 전화 접속 회의의 PIN(개인 식별 번호) 정책을 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-105">Follow these steps to create or modify a user-level or a site-level dial-in conferencing personal identification number (PIN) policy.</span></span> <span data-ttu-id="eaa27-106">글로벌 PIN 정책을 변경 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 기본 전화 접속 회의 PIN 설정 수정을](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="eaa27-106">For details about how to change the global PIN policy, see [Modify the default dial-in conferencing PIN settings in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="eaa27-107">사용자 또는 사이트 PIN 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="eaa27-107">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="eaa27-108">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="eaa27-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eaa27-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="eaa27-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eaa27-111">왼쪽 탐색 모음에서 **회의**를 클릭하고 **PIN 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-111">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="eaa27-112">**PIN 정책** 페이지에서 **새로 만들기**를 클릭한 다음, 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="eaa27-p103">사용자 수준 정책을 만들려면 **사용자 정책**을 클릭합니다. **새 PIN 정책**의 **이름**에 정책에 대해 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-p103">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="eaa27-p104">사이트 수준 정책을 만들려면 **사이트 정책**을 클릭합니다. **사이트 선택** 검색 필드에 정책을 만들 사이트의 이름 전부 또는 일부를 입력합니다. 사이트 목록에서 원하는 사이트를 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="eaa27-118">**설명** 필드에 PIN 정책에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-118">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="eaa27-p105">**최소 PIN 길이** 필드에서 허용할 최소 PIN 길이를 입력하거나 선택합니다. 기본 최소 길이는 5자리입니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-p105">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="eaa27-p106">사용자가 잠길 때까지의 최대 로그온 시도 횟수를 지정하려면 **최대 로그온 시도 횟수 지정** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN 길이에 따라 최대 로그온 시도 횟수가 자동으로 결정됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="eaa27-124">**최대 로그온 시도 횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도 횟수**에 허용할 최대 로그온 시도 횟수를 입력하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="eaa27-p107">PIN이 만료되도록 하려면 **PIN 만료 사용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN이 만료되지 않습니다. 기본적으로 PIN은 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

10. <span data-ttu-id="eaa27-128">**PIN 만료 사용** 확인란을 선택한 경우 **다음 이후 PIN 만료(일)** 에 PIN이 만료될 때까지의 기간(일)을 입력하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="eaa27-p108">**PIN 기록 카운트**에 사용자가 PIN을 다시 사용할 수 있을 때까지 만들어야 하는 PIN의 개수를 입력합니다. 기본적으로 사용자는 PIN을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="eaa27-p109">PIN에서 연속하는 숫자, 반복되는 숫자 집합 등의 공통 숫자 패턴을 허용하려면 **공통 패턴 허용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 복잡한 숫자 패턴만 허용됩니다. 기본적으로는 복잡한 숫자 패턴만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="eaa27-134">공통 패턴은 허용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-134">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="eaa27-135">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a><span data-ttu-id="eaa27-136">사용자 또는 사이트 PIN 정책을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="eaa27-136">To change a user or site PIN policy</span></span>

1.  <span data-ttu-id="eaa27-137">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="eaa27-138">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eaa27-139">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="eaa27-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eaa27-140">왼쪽 탐색 모음에서 **회의**를 클릭하고 **PIN 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-140">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="eaa27-141">**PIN 정책** 페이지에서 변경할 PIN 정책을 클릭한 다음 **편집**, **자세한 정보 표시**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-141">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="eaa27-142">**PIN 정책 편집**에서 원하는 정책 설정을 수정합니다(이름은 수정할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="eaa27-142">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>

6.  <span data-ttu-id="eaa27-143">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa27-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

