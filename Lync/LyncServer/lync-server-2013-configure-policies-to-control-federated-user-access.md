---
title: 'Lync Server 2013: 페더레이션 사용자 액세스를 제어 하도록 정책 구성'
description: 'Lync Server 2013: 페더레이션 사용자 액세스를 제어 하도록 정책을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d69f35baa16086b0c4e93a2a015474f87e08b736
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548744"
---
# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="4d36b-103">Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="4d36b-103">Configure policies to control federated user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d36b-104">_**마지막으로 수정 된 항목:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="4d36b-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="4d36b-105">페더레이션 파트너와의 통신을 지원할 정책을 구성할 경우 정책이 페더레이션 도메인의 사용자에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-105">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="4d36b-106">하나 이상의 외부 사용자 액세스 정책을 구성 하 여 페더레이션 도메인 사용자가 Lync Server 2013 사용자와 공동 작업을 수행할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-106">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="4d36b-107">페더레이션 사용자 액세스를 제어하려면 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-107">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="4d36b-108">한 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="4d36b-109">Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 미칩니다)이 사이트 정책에 우선 하며, 사이트 정책이 글로벌 정책 (최소 영향)을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="4d36b-110">즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d36b-111">조직에 대해 페더레이션을 사용하도록 설정하지 않았더라도 페더레이션 사용자 액세스를 제어하는 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-111">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="4d36b-112">그러나 구성하는 정책은 조직에 대해 페더레이션을 사용하도록 설정하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-112">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="4d36b-113">페더레이션을 사용 하는 방법에 대 한 자세한 내용은 배포 설명서 또는 작업 설명서에서 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013의 원격 사용자 액세스 사용 또는 사용 안 함을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d36b-113">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="4d36b-114">또한 페더레이션 사용자 액세스를 제어 하는 사용자 정책을 지정 하는 경우에는 Lync Server 2013을 사용 하도록 설정 되 고 정책을 사용 하도록 구성 된 사용자 에게만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-114">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="4d36b-115">페더레이션 도메인 사용자의 액세스를 지원하기 위한 정책을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="4d36b-115">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="4d36b-116">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-116">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d36b-117">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4d36b-118">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4d36b-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4d36b-119">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭하고 **외부 액세스 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-119">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="4d36b-120">**외부 액세스 정책** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-120">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="4d36b-121">페더레이션 사용자 액세스를 지원하기 위한 글로벌 정책을 구성하려면 글로벌 정책을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-121">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="4d36b-p104">새 사이트 정책을 만들려면 **새로 만들기**를 클릭하고 **사이트 정책**을 클릭합니다. **사이트 선택**의 목록에서 적절한 사이트를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-p104">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="4d36b-p105">새 사용자 정책을 만들려면 **새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다. **새 외부 액세스 정책**의 **이름** 필드에서 사용자 정책이 다루는 내용을 나타내는 고유한 이름을 만듭니다(예: 페더레이션 도메인 사용자에 대한 통신을 사용하도록 설정하는 사용자 정책의 경우 **EnableFederatedUsers**).</span><span class="sxs-lookup"><span data-stu-id="4d36b-p105">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="4d36b-126">기존 정책을 변경하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집**, **세부 정보 표시**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-126">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4d36b-127">(선택 사항) 설명을 추가하거나 편집하려면 정책에 대한 정보를 **설명**에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-127">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="4d36b-128">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-128">Do one of the following:</span></span>
    
      - <span data-ttu-id="4d36b-129">정책에 대한 페더레이션 사용자 액세스를 사용하도록 설정하려면 **페더레이션 사용자와의 통신 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-129">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="4d36b-130">정책에 대한 페더레이션 사용자 액세스를 사용하지 않도록 설정하려면 **페더레이션 사용자와의 통신 사용** 확인란 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-130">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="4d36b-131">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-131">Click **Commit**.</span></span>

<span data-ttu-id="4d36b-132">페더레이션 사용자 액세스를 허용하려면 조직에서 페더레이션을 지원하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-132">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="4d36b-133">자세한 내용은 [Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d36b-133">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="4d36b-134">사용자 정책의 경우에는 페더레이션 사용자와 공동 작업하도록 할 사용자에게도 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-134">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="4d36b-135">자세한 내용은 [Lync Server 2013의 lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4d36b-135">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="4d36b-136">페더레이션 도메인 사용자의 액세스를 지원 하기 위해 Windows PowerShell을 사용 하 여 기존 정책을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="4d36b-136">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="4d36b-137">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d36b-138">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4d36b-139">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-139">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="4d36b-140">페더레이션 사용자 액세스, XMPP 도메인 액세스, 원격 사용자 액세스, 공용 공급자 액세스를 사용하도록 글로벌 정책을 설정하고 이를 지원하는 공용 공급자에 대해 오디오 및 비디오 사용 기능을 부여하는 예제 명령:</span><span class="sxs-lookup"><span data-stu-id="4d36b-140">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="4d36b-141">Lync Server 제어판에서 "Enablepubliccloudvideoaccess" 매개 변수에 해당 하는 선택 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-141">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="4d36b-142">페더레이션 도메인 사용자의 액세스를 지원 하기 위해 Windows PowerShell을 사용 하 여 새 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4d36b-142">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="4d36b-143">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-143">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d36b-144">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4d36b-145">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-145">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="4d36b-146">새 사이트 정책을 만드는 예:</span><span class="sxs-lookup"><span data-stu-id="4d36b-146">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="4d36b-147">페더레이션 도메인 사용자의 액세스를 지원 하기 위해 Windows PowerShell을 사용 하 여 정책을 삭제 하거나 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="4d36b-147">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="4d36b-148">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d36b-149">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-149">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="4d36b-p108">글로벌 정책을 다시 설정하는 예(글로벌 정책은 해당 설정만 제거할 수 있으며, 정책 자체를 삭제할 수 없습니다.):</span><span class="sxs-lookup"><span data-stu-id="4d36b-p108">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="4d36b-152">사이트 정책을 제거하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-152">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="4d36b-153">사이트 정책 Redmond를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-153">Deletes the site policy Redmond.</span></span> <span data-ttu-id="4d36b-154">이름이 UserEAPPolicy인 사용자 정책을 삭제하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-154">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d36b-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d36b-155">See Also</span></span>


[<span data-ttu-id="4d36b-156">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4d36b-156">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="4d36b-157">Lync Server 2013의 Lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4d36b-157">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="4d36b-158">Lync Server 2013에서 조직에 대 한 SIP 페더레이션 도메인 관리</span><span class="sxs-lookup"><span data-stu-id="4d36b-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="4d36b-159">Lync Server 2013에서 조직에 대 한 SIP 페더레이션 공급자 관리</span><span class="sxs-lookup"><span data-stu-id="4d36b-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="4d36b-160">Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="4d36b-160">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="4d36b-161">Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="4d36b-161">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="4d36b-162">Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="4d36b-162">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="4d36b-163">Get-csexternalaccesspolicy을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d36b-163">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="4d36b-164">Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="4d36b-164">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

