---
title: 'Lync Server 2013: Lync 사용자가 원격 통화 제어를 사용 하도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4baa6f18e92eb284cce8610ba576b30dd6d2f320
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="59cda-102">Lync Server 2013에서 Lync 사용자가 원격 통화 제어를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="59cda-102">Enable Lync users for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59cda-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="59cda-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="59cda-104">서버 기반의 대역내 프로 비전 정책을 사용 하 여 원격 통화 제어에 대 한 Lync 사용자를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-104">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="59cda-105">Lync Server 제어판 또는 Lync Server 관리 셸 명령줄 인터페이스를 사용 하 여 대역내 프로 비전 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-105">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="59cda-106">이러한 도구는 이전 버전에서 그룹 정책 설정을 관리 하는 데 사용 된 WMI (Windows Management Instrumentation) 스냅인을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-106">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="59cda-107">사용자가 Lync에서 자체 원격 통화 제어 설정을 구성 하도록 하려면 **줄 서버 URI** 및 **줄 URI** 값을 지정 하지 않고 서버에서 사용자에 대 한 원격 통화 제어 설정을 구성 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-107">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="59cda-108">적절 한 **회선 서버 URI** 및 **줄 uri** 값을 사용자에 게 전달 하 고 사용자에 게 이러한 설정을 구성 하기 위한 지침을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-108">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="59cda-109">Lync Server에서 원격 통화 제어를 수동으로 구성 하는 절차는 Microsoft Office 웹 사이트의 Lync 클라이언트 설명서 <http://go.microsoft.com/fwlink/p/?linkid=210132> 에서 "전화 옵션 및 번호 설정"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="59cda-109">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <http://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="59cda-110">기존 Communications Server 2007 R2 또는 Communications Server 2007 배포가 있는 경우 Communicator 2007 R2 및 Communicator 2007 클라이언트는 병행 마이그레이션 중에 그룹 정책을 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-110">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="59cda-111">그러나 정책 설정을 Lync 클라이언트에 전달 하려면 해당 Lync Server 대역내 프로 비전 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-111">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59cda-112">사용자가 원격 통화 제어를 사용 하도록 설정 하려면 줄 URI와 줄 서버 URI를 모두 사용자에 게 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-112">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="59cda-113"><A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013의 원격 통화 제어에 대 한 배포 작업</A>에 설명 된 대로이 설정에 대해 게이트웨이에 필요한 구문을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-113">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="59cda-114">회선 서버 URI의 도메인이 게이트웨이에 대 한 고정 경로를 구성할 때 MatchUri 매개 변수에 지정한 대상 도메인과 같은지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-114">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="59cda-115">줄 URI는 전자 프로그램에서 사용자에 게 할당 되는 전화 번호를 "TEL:" 접두사를 사용 하 여 지정 합니다 (예: tel-+ 14255550150).</span><span class="sxs-lookup"><span data-stu-id="59cda-115">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150).</span></span> <span data-ttu-id="59cda-116">내선 번호를 구성 하려면 다음을 수행 합니다. + 14255550150; ext = 111.</span><span class="sxs-lookup"><span data-stu-id="59cda-116">If you want to configure an extension number, then the format is tel:+14255550150;ext=111.</span></span> <span data-ttu-id="59cda-117">이전에 사용자의 줄 URI를 구성 했지만 값이 변경 되지 않은 경우 원격 통화 제어에 대해 사용자를 사용 하도록 설정 하면 줄 URI를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-117">If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="59cda-118">관리 셸을 사용하여 Lync 사용자가 원격 통화 제어를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="59cda-118">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="59cda-119">Lync Server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 된 컴퓨터나 **CsUser** cmdlet이 할당 된 역할 기반 액세스 제어 역할로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-119">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="59cda-120">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="59cda-121">**Set-CsUser** cmdlet를 사용하여 기존 Lync 사용자에 대한 원격 통화 제어를 구성하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-121">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="59cda-122">예:</span><span class="sxs-lookup"><span data-stu-id="59cda-122">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="59cda-123">Lync Server 제어판을 사용하여 원격 통화 제어에 대해 사용자를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="59cda-123">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="59cda-124">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-124">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="59cda-125">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="59cda-126">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="59cda-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="59cda-127">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-127">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="59cda-128">**사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 Uri (Uniform resource Identifier)를 모두 (또는 첫 부분)를 입력 하 고 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-128">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="59cda-129">표에서 수정할 사용자 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-129">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="59cda-130">**편집** 메뉴에서 **수정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-130">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="59cda-131">**전화 통신**에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-131">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="59cda-132">사용자가 Lync 2013에서 PBX (private branch exchange) 전화를 제어 하 여 pc 간 음성 통화 및 PC 간 통화를 제어할 수 있도록 하는 원격 통화 제어를 사용 하도록 설정 하려면 **원격 통화 제어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-132">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="59cda-133">**줄 URI**에 사용자의 전화 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-133">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="59cda-134">**회선 서버 URI**에 SIP/CSTA 게이트웨이의 SIP URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-134">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="59cda-135">원격 통화 제어를 사용 하도록 설정 하 되 PC 간 음성 통화를 사용 하지 않도록 설정 하 고 사용자만 Lync 2013에서 전화를 제어할 수 있도록 하 여 PC 간 통화를 설정 하려면 **원격 통화 제어만**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-135">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="59cda-136">**줄 URI**에 사용자의 전화 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-136">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="59cda-137">**회선 서버 URI**에 SIP/CSTA 게이트웨이의 SIP URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-137">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="59cda-138">작업을 마치면 **커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="59cda-138">When you are finished, click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

