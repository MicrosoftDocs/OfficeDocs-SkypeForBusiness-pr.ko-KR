---
title: 'Lync Server 2013: 익명 사용자 지원을 위한 회의 정책 할당'
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
ms.openlocfilehash: bab1c3da15bd72bb03233ca05d86e355eebbb233
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="39817-102">Lync Server 2013에서 익명 사용자 지원을 위한 회의 정책 할당</span><span class="sxs-lookup"><span data-stu-id="39817-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39817-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="39817-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="39817-104">기본적으로 모든 사용자는 익명 사용자를 초대 하 여 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39817-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="39817-105">익명 사용자를 지원 하도록 회의 정책을 구성 하 고 특정 사용자에 게 해당 회의 정책을 적용 하 여 익명 사용자를 초대할 수 있는 사용자를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="39817-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="39817-106">익명 사용자를 지원 하도록 회의 정책을 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 회의 정책 만들기 또는 수정을](lync-server-2013-create-or-modify-a-conferencing-policy.md) 참조 하 고 [페더레이션 및 lync server 2013에 대 한 외부 액세스를 관리](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="39817-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="39817-107">이 섹션의 절차를 사용 하 여 이미 만든 회의 정책을 하나 이상의 사용자 또는 사용자 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39817-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39817-108">사용자가 익명 사용자를 초대할 수 있도록 하는 정책을 구성 하 고 적용 하는 것 외에도 조직의 익명 사용자에 대 한 지원을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39817-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="39817-109">자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013에서 공용 사용자 액세스를 제어 하는 정책 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39817-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="39817-110">모임에서 익명 참가에 대 한 사용자 정책을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="39817-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="39817-111">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="39817-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="39817-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="39817-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="39817-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39817-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="39817-114">왼쪽 탐색 모음에서 **회의**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="39817-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="39817-115">새 사용자 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39817-115">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="39817-116">사용자 정책이 어떤 역할을 하는지 나타내는 **이름** 필드에 고유한 이름을 만듭니다 (예: 익명 사용자와의 통신을 가능 하 게 하는 사용자 정책에 **익명** 허용).</span><span class="sxs-lookup"><span data-stu-id="39817-116">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="39817-117">기존 사용자 정책을 구성 하려면 표에 나열 된 적절 한 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39817-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="39817-118">**회의 정책** 대화 상자에서 **참가자가 익명 사용자 초대를 허용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39817-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="39817-119">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39817-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="39817-120">왼쪽 탐색 모음에서 **사용자**를 클릭 하 고 구성 하려는 사용자 계정에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="39817-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="39817-121">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39817-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="39817-122">**회의 정책**에서 **Lync Server 사용자 편집** 에서이 사용자에 게 적용 하려는 익명 사용자 액세스 구성이 있는 사용자 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39817-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39817-123">자동 설정은 기본 서버 설치 설정을 적용 하 고 서버에 의해 자동으로 적용 됩니다. <STRONG> &lt;&gt; </STRONG></span><span class="sxs-lookup"><span data-stu-id="39817-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="39817-124">사용자가 회의에 익명 사용자를 초대할 수 있도록 하려면 조직의 익명 사용자에 대 한 지원도 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39817-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="39817-125">자세한 내용은 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 공용 사용자 액세스를 제어 하는 정책 구성을](lync-server-2013-configure-policies-to-control-public-user-access.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39817-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

