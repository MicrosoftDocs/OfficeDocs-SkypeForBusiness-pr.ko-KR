---
title: 'Lync Server 2013: 페더레이션 사용자 액세스를 제어할 정책 구성'
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
ms.openlocfilehash: e1aeb1b29637fd3f4a8add770470069e8b4a6eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="c8f35-102">Lync Server 2013에서 페더레이션 사용자 액세스를 제어할 정책 구성</span><span class="sxs-lookup"><span data-stu-id="c8f35-102">Configure policies to control federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8f35-103">_**마지막으로 수정한 주제:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="c8f35-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="c8f35-104">페더레이션 파트너와의 통신을 지원 하도록 정책을 구성 하는 경우 페더레이션 도메인의 사용자에 게 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="c8f35-105">페더레이션 도메인 사용자가 Lync Server 2013 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="c8f35-106">페더레이션 사용자 액세스를 제어 하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="c8f35-107">하나의 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 된 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c8f35-108">Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 글로벌 정책에 우선 합니다 (최소 영향).</span><span class="sxs-lookup"><span data-stu-id="c8f35-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c8f35-109">즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8f35-110">조직을 위한 페더레이션을 설정 하지 않은 경우에도 정책을 구성 하 여 페더레이션된 사용자 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="c8f35-111">그러나 구성 하는 정책은 조직에 페더레이션이 설정 되어 있는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="c8f35-112">페더레이션 사용에 대 한 자세한 내용은 배포 설명서 또는 운영 설명서의 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8f35-112">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="c8f35-113">또한 페더레이션 사용자 액세스를 제어 하는 사용자 정책을 지정 하는 경우 Lync Server 2013에서 사용 하도록 설정 하 고 정책을 사용 하도록 구성 된 사용자 에게만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c8f35-114">페더레이션 도메인의 사용자가 액세스를 지원 하도록 정책을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="c8f35-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c8f35-115">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8f35-116">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c8f35-117">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8f35-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c8f35-118">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-118">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="c8f35-119">**외부 액세스 정책** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-119">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="c8f35-120">페더레이션 사용자 액세스를 지원 하도록 전역 정책을 구성 하려면 전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-120">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="c8f35-121">새 사이트 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사이트 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-121">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="c8f35-122">**사이트 선택**의 목록에서 해당 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-122">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="c8f35-123">새 사용자 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-123">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="c8f35-124">**새 외부 액세스 정책**에서 사용자 정책에 대 한 정보 (예: 페더레이션 도메인 사용자에 게 통신을 사용 하도록 설정 하는 사용자 정책에 대 한 **EnableFederatedUsers** )를 나타내는 고유한 이름을 **이름** 필드에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-124">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="c8f35-125">기존 정책을 변경 하려면 표에 나열 된 적절 한 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-125">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c8f35-126">) 설명을 추가 하거나 편집 하려면 **설명**에서 정책에 대 한 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-126">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="c8f35-127">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-127">Do one of the following:</span></span>
    
      - <span data-ttu-id="c8f35-128">정책에 대해 페더레이션 사용자 액세스를 사용 하도록 설정 하려면 **페더레이션 사용자와 통신 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-128">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="c8f35-129">정책에 대해 페더레이션 사용자 액세스를 사용 하지 않도록 설정 하려면 **페더레이션 사용자와 통신 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-129">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="c8f35-130">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-130">Click **Commit**.</span></span>

<span data-ttu-id="c8f35-131">페더레이션 사용자 액세스를 사용 하도록 설정 하려면 조직의 페더레이션에 대 한 지원도 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-131">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="c8f35-132">자세한 내용은 [Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8f35-132">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="c8f35-133">사용자 정책 인 경우 페더레이션 사용자와 공동 작업을 할 수 있도록 하는 사용자에 게도 정책을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-133">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="c8f35-134">자세한 내용은 [Lync Server 2013에서 lync를 사용 하는 사용자에 게 외부 사용자 액세스 정책 할당](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8f35-134">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c8f35-135">페더레이션 도메인 사용자의 액세스를 지원 하기 위해 Windows PowerShell을 사용 하 여 기존 정책을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="c8f35-135">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c8f35-136">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8f35-137">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c8f35-138">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-138">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="c8f35-139">페더레이션 사용자 액세스에 대 한 전역 정책을 사용 가능으로 설정 하 고 XMPP 도메인 액세스를 사용 하 고 원격 사용자 액세스를 사용 하 고 공용 공급자 액세스를 사용 가능 하 게 설정한 다음이를 지 원하는 공용 공급자에 오디오 및 비디오를 사용할 수 있는 기능을 부여 하는 예제 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-139">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c8f35-140">"Enablepubliccloudvideoaccess" 매개 변수는 Lync Server 제어판에서 해당 하는 항목을 선택 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-140">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c8f35-141">페더레이션 도메인 사용자의 액세스를 지원 하기 위해 Windows PowerShell을 사용 하 여 새 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="c8f35-141">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c8f35-142">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8f35-143">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c8f35-144">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-144">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="c8f35-145">새 사이트 정책을 만드는 예:</span><span class="sxs-lookup"><span data-stu-id="c8f35-145">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c8f35-146">페더레이션 도메인 사용자의 액세스를 지원 하기 위해 Windows PowerShell을 사용 하 여 정책을 삭제 하거나 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="c8f35-146">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c8f35-147">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8f35-148">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-148">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="c8f35-149">전역 정책 다시 설정의 예 (전역 정책에는 해당 설정만 제거할 수 있음)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-149">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="c8f35-150">정책을 삭제할 수 없음):</span><span class="sxs-lookup"><span data-stu-id="c8f35-150">The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="c8f35-151">사이트 정책을 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-151">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="c8f35-152">사이트 정책 Redmond를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-152">Deletes the site policy Redmond.</span></span> <span data-ttu-id="c8f35-153">UserEAPPolicy 라는 사용자 정책을 삭제 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f35-153">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8f35-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8f35-154">See Also</span></span>


[<span data-ttu-id="c8f35-155">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c8f35-155">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="c8f35-156">Lync Server 2013에서 Lync 사용이 가능한 사용자에게 외부 사용자 액세스 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c8f35-156">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="c8f35-157">Lync Server 2013에서 조직의 SIP 페더레이션된 도메인 관리</span><span class="sxs-lookup"><span data-stu-id="c8f35-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="c8f35-158">Lync Server 2013에서 조직에 대한 SIP 페더레이션 공급자 관리</span><span class="sxs-lookup"><span data-stu-id="c8f35-158">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="c8f35-159">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c8f35-159">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="c8f35-160">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c8f35-160">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="c8f35-161">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c8f35-161">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="c8f35-162">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c8f35-162">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="c8f35-163">부여-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c8f35-163">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

