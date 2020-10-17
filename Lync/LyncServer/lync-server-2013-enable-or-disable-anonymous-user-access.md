---
title: 'Lync Server 2013: 익명 사용자 액세스 사용 또는 사용 안 함'
description: 'Lync Server 2013: 익명 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ca36cffc25cd31d057b00c22cb299c56cfd7b3c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544774"
---
# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="36338-103">Lync Server 2013에서 익명 사용자 액세스 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="36338-103">Enable or disable anonymous user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36338-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="36338-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="36338-105">익명 사용자는 조직의 Active Directory 도메인 서비스 또는 지원 되는 페더레이션 도메인에 사용자 계정이 없지만 온-프레미스 회의에 원격으로 참여 하도록 초대할 수 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="36338-105">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="36338-106">모임에서 익명 참가를 허용 하면 익명 사용자 (즉, 모임 또는 회의 키만 통해 id를 확인 한 사용자)를 사용 하도록 설정 하 여 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36338-106">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="36338-107">익명 참가를 허용 하려면 조직에서이 기능을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36338-107">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="36338-108">나중에 익명 사용자의 액세스를 일시적으로 또는 영구적으로 차단 하려는 경우 조직에서이를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36338-108">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="36338-109">이 섹션의 절차를 사용 하 여 조직에 대해 익명 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36338-109">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36338-110">조직에 대해 익명 사용자 액세스를 사용 하도록 설정 하면 액세스에 지 서비스를 실행 하는 서버에서 익명 사용자의 액세스를 지원 하도록 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36338-110">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="36338-111">익명 사용자는 하나 이상의 회의 정책을 구성 하 고 하나 이상의 사용자 또는 사용자 그룹에 적용할 때까지 조직의 모든 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36338-111">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="36338-112">익명 사용자를 모임에 초대할 수 있는 사용자는 익명 사용자를 지원 하도록 구성 된 회의 정책이 할당 된 사용자 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="36338-112">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="36338-113">익명 사용자 초대를 지원 하도록 회의 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-conferencing-policies.md">Lync Server 2013의 회의 정책을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="36338-113">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="36338-114">조직에 대해 익명 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="36338-114">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="36338-115">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="36338-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="36338-116">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="36338-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="36338-117">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="36338-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="36338-118">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭하고 **액세스 에지 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="36338-118">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="36338-119">**액세스 에지 구성** 페이지에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="36338-119">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="36338-120">**액세스 에지 구성 편집**에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="36338-120">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="36338-121">조직에 대해 익명 사용자 액세스를 사용 하도록 설정 하려면 **익명 사용자와의 통신 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="36338-121">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="36338-122">조직에 대해 익명 사용자 액세스를 사용 하지 않도록 설정 하려면 **익명 사용자와의 통신 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="36338-122">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="36338-123">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="36338-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="36338-124">Windows PowerShell Cmdlet을 사용 하 여 익명 사용자 액세스 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="36338-124">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="36338-125">Windows PowerShell 및 **set-csaccessedgeconfiguration** cmdlet을 사용 하 여 익명 사용자 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36338-125">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="36338-126">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36338-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="36338-127">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="36338-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="36338-128">익명 사용자 액세스를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="36338-128">To enable anonymous user access</span></span>

  - <span data-ttu-id="36338-129">익명 사용자 액세스를 사용 하도록 설정 하려면 **AllowAnonymousUsers** 속성의 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36338-129">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="36338-130">익명 사용자 액세스를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="36338-130">To disable anonymous user access</span></span>

  - <span data-ttu-id="36338-131">익명 사용자 액세스를 사용 하지 않으려면 **AllowAnonymousUsers** 속성 값을 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36338-131">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36338-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36338-132">See Also</span></span>


[<span data-ttu-id="36338-133">Lync Server 2013에 대 한 회의 정책 설정 참조</span><span class="sxs-lookup"><span data-stu-id="36338-133">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

