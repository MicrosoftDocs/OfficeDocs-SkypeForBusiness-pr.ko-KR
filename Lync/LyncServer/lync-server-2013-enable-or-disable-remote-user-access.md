---
title: 'Lync Server 2013: 원격 사용자 액세스 사용 또는 사용 안 함'
description: 'Lync Server 2013: 원격 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dea2d58c1978ac2d52365a4a453c40b38dd89c44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547894"
---
# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="5f82a-103">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5f82a-103">Enable or disable remote user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f82a-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5f82a-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5f82a-105">원격 사용자는 조직 내에 영구 Active Directory id가 있는 조직의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-105">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="5f82a-106">원격 사용자는 조직의 네트워크에 연결 되어 있지 않을 때 VPN (가상 사설망)을 사용 하 여 네트워크 외부에서 Lync Server에 로그인 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-106">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="5f82a-107">원격 사용자는 가정에서 근무 하는 직원 및 신뢰할 수 있는 공급 업체와 같은 다른 원격 작업자에 게 엔터프라이즈 자격 증명을 부여 받은 직원이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-107">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="5f82a-108">원격 사용자에 대해 원격 사용자 액세스를 사용 하도록 설정 하면 지원 되는 원격 사용자가 인터넷을 통해 연결 되며 Lync Server를 사용 하 여 내부 사용자와 공동 작업 하기 위해 VPN을 사용 하 여 연결할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-108">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="5f82a-109">원격 사용자 액세스를 지원 하려면 원격 사용자 액세스를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-109">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="5f82a-110">원격 사용자 액세스를 사용 하도록 설정 하면 전체 조직에 대해이를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-110">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="5f82a-111">나중에 일시적으로 또는 영구적으로 원격 사용자 액세스를 차단 하려는 경우 조직에서이를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-111">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="5f82a-112">이 섹션의 절차를 사용 하 여 조직에 대해 원격 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-112">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f82a-113">원격 사용자 액세스를 사용 하도록 설정 하면 액세스에 지 서비스를 실행 하는 서버가 원격 사용자와의 통신을 지원 하도록 지정 되지만 원격 사용자 액세스를 관리 하기 위한 정책을 하나 이상 구성 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-113">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="5f82a-114">한 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-114">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="5f82a-115">Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 미칩니다)이 사이트 정책에 우선 하며, 사이트 정책이 글로벌 정책 (최소 영향)을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-115">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="5f82a-116">즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-116">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="5f82a-117">원격 사용자 액세스 사용에 대 한 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스를 제어 하도록 정책 구성을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f82a-117">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="5f82a-118">조직에 대해 원격 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5f82a-118">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="5f82a-119">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5f82a-120">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5f82a-121">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f82a-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5f82a-122">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 하 고 **액세스에 지 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-122">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="5f82a-123">**액세스 에지 구성** 페이지에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-123">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5f82a-124">**액세스 에지 구성 편집**에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-124">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="5f82a-125">조직에 대해 원격 사용자 액세스를 사용 하도록 설정 하려면 **원격 사용자 액세스 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-125">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="5f82a-126">조직에 대해 원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **원격 사용자 액세스 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-126">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="5f82a-127">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-127">Click **Commit**.</span></span>

<span data-ttu-id="5f82a-128">원격 사용자가 Lync Server를 실행 하는 서버에 로그인 할 수 있도록 하려면 원격 사용자 액세스를 지원 하도록 하나 이상의 외부 액세스 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-128">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="5f82a-129">자세한 내용은 배포 설명서 또는 작업 설명서에서 [Lync Server 2013의 원격 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-remote-user-access.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f82a-129">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5f82a-130">Windows PowerShell Cmdlet을 사용 하 여 원격 사용자 액세스 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5f82a-130">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5f82a-131">원격 사용자 액세스는 Windows PowerShell 및 Set-CsAccessEdgeConfiguration cmdlet을 사용 하 여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-131">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="5f82a-132">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-132">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5f82a-133">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f82a-133">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="5f82a-134">원격 사용자 액세스를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5f82a-134">To enable remote user access</span></span>

  - <span data-ttu-id="5f82a-135">원격 사용자 액세스를 사용 하도록 설정 하려면 **Allowoutsideusers** 속성 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-135">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="5f82a-136">원격 사용자 액세스를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5f82a-136">To disable remote user access</span></span>

  - <span data-ttu-id="5f82a-137">원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **Allowoutsideusers** 속성 값을 False ($False)로 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82a-137">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

