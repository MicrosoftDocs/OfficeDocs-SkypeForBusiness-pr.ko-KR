---
title: 'Lync Server 2013: XMPP 페더레이션 사용자 액세스를 제어하도록 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ec90a1b079935713ce6f13e7b74763e7004dedf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="e434f-102">Lync Server 2013에서 XMPP 페더레이션 사용자 액세스를 제어하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="e434f-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e434f-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e434f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e434f-104">이 문서는 예비 문서로, 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="e434f-105">빈 항목은 개체 틀로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="e434f-106">XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션 파트너 지원에 대 한 정책을 구성할 때 정책은 XMPP 페더레이션 도메인의 사용자에 게 적용 되지만 SIP (세션 초기화 프로토콜) 서비스 공급자의 사용자에 게는 적용 되지 않습니다. (예: Windows Live) 또는 SIP 페더레이션 도메인</span><span class="sxs-lookup"><span data-stu-id="e434f-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="e434f-107">사용자가 연락처를 추가 하 고 통신 하는 데 사용할 각 XMPP 페더레이션 도메인에 대해 **Xmpp 페더레이션 파트너** 를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="e434f-108">XMPP 페더레이션 파트너 정책은 글로벌 정책으로 정의 되지 않고 글로벌 정책 역할을 하는 단일 범위 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="e434f-109">XMPP 페더레이션 파트너에 대해 전역, 사이트 또는 사용자 정책을 정의 하려면 먼저 필요한 범위에 대해 외부 액세스 정책을 만들고 구성 하 여 정책 범위를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="e434f-110">외부 액세스 및 페더레이션에 대해 구성할 수 있는 정책의 유형에 대 한 자세한 내용은 운영 설명서의 [Lync Server 2013에 대 한 페더레이션 및 외부 액세스 관리](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e434f-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e434f-111">모든 <STRONG>페더레이션 및 외부 액세스</STRONG> 정책은 대역내 프로비저닝을 통해 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="e434f-112">사용자에 게 적용 되거나 사이트에 속해 있거나 범위에 전역 인 정책이 로그인 중에 클라이언트에 게 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="e434f-113">조직에 XMPP 페더레이션을 설정 하지 않은 경우에도 XMPP 페더레이션 파트너 액세스를 제어 하도록 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="e434f-114">그러나 구성 하는 정책은 조직에 대해 XMPP 파트너 페더레이션을 배포 하 고 사용 하도록 설정한 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="e434f-115">XMPP 파트너 페더레이션 배포 및 구성에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공용 인스턴트 메시지 구성을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e434f-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="e434f-116">또한 XMPP 페더레이션 파트너를 제어 하기 위해 외부 액세스 정책에서 사용자 정책을 지정 하는 경우 Lync Server 2013에서 사용 하도록 설정 하 고 정책을 사용 하도록 구성 된 사용자 에게만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="e434f-117">XMPP 페더레이션 파트너에 대 한 전역 정책을 편집 하려면</span><span class="sxs-lookup"><span data-stu-id="e434f-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="e434f-118">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e434f-119">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e434f-120">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e434f-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e434f-121">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="e434f-122">**외부 액세스 정책** 페이지에서 글로벌 정책에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="e434f-123">전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 세부 정보 표시를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="e434f-124">전역 정책에 대 한 설명을 입력 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="e434f-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="e434f-125">**페더레이션 사용자와의 통신 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="e434f-126">**XMPP 페더레이션 사용자와 통신 사용을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="e434f-127">**커밋을** 클릭 하 여 전역 정책에 대 한 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="e434f-128">XMPP 페더레이션 파트너에 대 한 사이트 또는 사용자 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e434f-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="e434f-129">**새로 만들기**를 클릭 한 다음 **사이트 정책** 또는 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-129">Click **New**, and then click **Site policy** or **User policy**.</span></span> <span data-ttu-id="e434f-130">**사이트 선택**의 목록에서 해당 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-130">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="e434f-131">사이트 정책에 대 한 설명을 입력 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="e434f-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="e434f-132">사이트 또는 사용자 정책에서 **페더레이션된 사용자와의 통신 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="e434f-133">**XMPP 페더레이션 사용자와 통신 사용을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="e434f-134">**커밋을** 클릭 하 여 사이트 또는 사용자 정책의 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="e434f-135">XMPP 페더레이션 파트너에 대 한 기존 정책 편집</span><span class="sxs-lookup"><span data-stu-id="e434f-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="e434f-136">기존 정책을 변경 하려면 목록에서 해당 정책을 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="e434f-137">정책에 대 한 설명을 변경 하거나 업데이트 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="e434f-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="e434f-138">**페더레이션 사용자와의 통신 사용**을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="e434f-139">**XMPP 페더레이션 사용자와의 통신 사용을**선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="e434f-140">**커밋을** 클릭 하 여 정책에 대 한 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="e434f-141">Windows PowerShell을 사용 하 여 XMPP 페더레이션 파트너에 대 한 기존 정책 편집</span><span class="sxs-lookup"><span data-stu-id="e434f-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="e434f-142">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e434f-143">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e434f-144">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="e434f-145">페더레이션 사용자 액세스에 대 한 글로벌 정책을 True (enabled) 및 XMPP 도메인 액세스 (사용)로 설정 하는 예제 명령:</span><span class="sxs-lookup"><span data-stu-id="e434f-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="e434f-146">Windows PowerShell을 사용 하 여 XMPP 페더레이션 파트너에 대 한 사이트 또는 사용자 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e434f-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="e434f-147">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e434f-148">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e434f-149">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="e434f-150">페더레이션 사용자 액세스를 위해 Redmond 사이트에 대 한 사이트 정책을 사용할 수 있도록 설정 하 고 XMPP 도메인 액세스를 사용 하는 경우의 예제 명령:</span><span class="sxs-lookup"><span data-stu-id="e434f-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="e434f-151">Windows PowerShell을 사용 하 여 XMPP 페더레이션 파트너에 대 한 기존 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="e434f-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="e434f-152">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e434f-153">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e434f-154">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e434f-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="e434f-155">사용자 정책을 삭제 하는 명령 예:</span><span class="sxs-lookup"><span data-stu-id="e434f-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="e434f-156">전역 정책을 기본값으로 다시 설정 하는 예제 명령:</span><span class="sxs-lookup"><span data-stu-id="e434f-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e434f-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e434f-157">See Also</span></span>


[<span data-ttu-id="e434f-158">Lync Server 2013에서 Lync 사용이 가능한 사용자에게 외부 사용자 액세스 정책 할당</span><span class="sxs-lookup"><span data-stu-id="e434f-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="e434f-159">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="e434f-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="e434f-160">Lync Server 2013에서 XMPP 페더레이션 파트너 관리</span><span class="sxs-lookup"><span data-stu-id="e434f-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="e434f-161">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e434f-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="e434f-162">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e434f-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="e434f-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e434f-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="e434f-164">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e434f-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="e434f-165">부여-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e434f-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

