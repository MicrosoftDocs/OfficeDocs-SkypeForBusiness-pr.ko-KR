---
title: 'Lync Server 2013: 익명 사용자를 지원 하기 위한 회의 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 167fe5c772e765c5f78ac2253c23d66550e0e712
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="55ad4-102">Lync Server 2013에서 익명 사용자를 지원 하기 위한 회의 정책 할당</span><span class="sxs-lookup"><span data-stu-id="55ad4-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55ad4-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="55ad4-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="55ad4-104">기본적으로 모든 사용자는 익명 사용자를 모임에 참여하도록 초대할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="55ad4-105">익명 사용자를 지원하도록 회의 정책을 구성하고 이 회의 정책을 특정 사용자에게 적용하여 익명 사용자를 초대할 수 있는 사용자를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="55ad4-106">익명 사용자를 지원 하도록 회의 정책을 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 회의 정책 만들기 또는 수정](lync-server-2013-create-or-modify-a-conferencing-policy.md) 및 [lync server 2013에 대 한 외부 액세스 및 페더레이션 관리](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55ad4-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="55ad4-107">이미 만든 회의 정책을 하나 이상의 사용자 또는 사용자 그룹에 적용하려면 이 섹션의 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55ad4-108">사용자가 익명 사용자를 초대할 수 있도록 정책을 구성하고 적용해야 할 뿐 아니라, 조직에서 익명 사용자를 지원하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="55ad4-109">자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013에서 공용 사용자 액세스를 제어 하도록 정책 구성을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55ad4-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="55ad4-110">모임의 익명 참가에 대한 사용자 정책을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="55ad4-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="55ad4-111">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="55ad4-112">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="55ad4-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55ad4-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="55ad4-114">왼쪽 탐색 모음에서 **회의**를 클릭하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="55ad4-p104">새 사용자 정책을 만들려면 **새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다. **이름** 필드에서 사용자 정책이 다루는 내용을 나타내는 고유한 이름을 만듭니다(예: 익명 사용자와 통신할 수 있도록 설정하는 사용자 정책의 경우 **EnableAnonymous**).</span><span class="sxs-lookup"><span data-stu-id="55ad4-p104">To create a new user policy, click **New**, and then click **User policy**. Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="55ad4-117">기존 사용자 정책을 구성하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집**, **세부 정보 표시**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="55ad4-118">**회의 정책** 대화 상자에서 **참가자가 익명 사용자를 초대할 수 있도록 허용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="55ad4-119">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="55ad4-120">왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성할 사용자 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="55ad4-121">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="55ad4-122">**Lync Server 사용자 편집**의 **회의 정책**에서 해당 사용자에게 적용할 익명 사용자 액세스 구성이 적용된 사용자 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55ad4-123">자동 설정은 기본 서버 설치 설정을 적용 하며 서버에 의해 자동으로 적용 됩니다. <STRONG> &lt;&gt; </STRONG></span><span class="sxs-lookup"><span data-stu-id="55ad4-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="55ad4-124">사용자가 회의에 익명 사용자를 초대할 수 있도록 하려면 조직에서 익명 사용자에 대한 지원을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ad4-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="55ad4-125">자세한 내용은 배포 설명서 또는 작업 설명서에서 [Lync Server 2013의 공용 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-public-user-access.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55ad4-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

