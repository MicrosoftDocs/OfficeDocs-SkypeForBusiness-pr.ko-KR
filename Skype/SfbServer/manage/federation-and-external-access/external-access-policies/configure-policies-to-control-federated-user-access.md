---
title: 페더레이션 사용자 액세스를 컨트롤하는 정책 구성
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '페더레이션 파트너와의 통신을 지원할 정책을 구성할 경우 정책이 페더레이션 도메인의 사용자에 적용됩니다. '
ms.openlocfilehash: 2b7976492fe4f789c2f3130fb51deaaef44af701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817308"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="9fa2b-103">비즈니스용 Skype 서버에서 페더전된 사용자 액세스를 제어하는 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9fa2b-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="9fa2b-104">페더레이션 파트너와의 통신을 지원할 정책을 구성할 경우 정책이 페더레이션 도메인의 사용자에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="9fa2b-105">하나 이상의 외부 사용자 액세스 정책을 구성하여 페더타 도메인 사용자가 비즈니스용 Skype 서버 사용자와 공동 작업을 할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="9fa2b-106">페더레이션 사용자 액세스를 제어하려면 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="9fa2b-107">한 정책 수준에서 적용되는 비즈니스용 Skype 서버 정책 설정은 다른 정책 수준에서 적용되는 설정을 다시 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="9fa2b-108">비즈니스용 Skype 서버 정책 우선 순위는 다음과 같습니다. 사용자 정책(가장 큰 영향)이 사이트 정책을 재정의한 다음 사이트 정책이 글로벌 정책 (가장 큰 영향)을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="9fa2b-109">즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="9fa2b-110">조직에 대해 페더레이션을 사용하도록 설정하지 않았더라도 페더레이션 사용자 액세스를 제어하는 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="9fa2b-111">그러나 구성하는 정책은 조직에 대해 페더레이션을 사용하도록 설정하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="9fa2b-112">페더링을 사용하도록 설정하는 데 대한 자세한 내용은 원격 사용자 액세스 사용 또는 사용 [안 을 참조합니다.](../access-edge/enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="9fa2b-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="9fa2b-113">또한 페더전된 사용자 액세스를 제어하기 위한 사용자 정책을 지정하는 경우 해당 정책은 비즈니스용 Skype 서버에 대해 사용하도록 설정되어 있으며 정책을 사용하도록 구성된 사용자에게만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="9fa2b-114">페더레이션 도메인 사용자의 액세스를 지원하기 위한 정책을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="9fa2b-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="9fa2b-115">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9fa2b-116">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="9fa2b-117">왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭하고 **외부 액세스 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="9fa2b-118">**외부 액세스 정책** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9fa2b-119">페더레이션 사용자 액세스를 지원하기 위한 글로벌 정책을 구성하려면 글로벌 정책을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="9fa2b-p103">새 사이트 정책을 만들려면 **새로 만들기** 를 클릭하고 **사이트 정책** 을 클릭합니다. **사이트 선택** 의 목록에서 적절한 사이트를 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-p103">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="9fa2b-p104">새 사용자 정책을 만들려면 **새로 만들기** 를 클릭하고 **사용자 정책** 을 클릭합니다. **새 외부 액세스 정책** 의 **이름** 필드에서 사용자 정책이 다루는 내용을 나타내는 고유한 이름을 만듭니다(예: 페더레이션 도메인 사용자에 대한 통신을 사용하도록 설정하는 사용자 정책의 경우 **EnableFederatedUsers**).</span><span class="sxs-lookup"><span data-stu-id="9fa2b-p104">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="9fa2b-124">기존 정책을 변경하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집**, **세부 정보 표시** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9fa2b-125">(선택 사항) 설명을 추가하거나 편집하려면 정책에 대한 정보를 **설명** 에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="9fa2b-126">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="9fa2b-127">정책에 대한 페더레이션 사용자 액세스를 사용하도록 설정하려면 **페더레이션 사용자와의 통신 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="9fa2b-128">정책에 대한 페더레이션 사용자 액세스를 사용하지 않도록 설정하려면 **페더레이션 사용자와의 통신 사용** 확인란 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="9fa2b-129">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-129">Click **Commit**.</span></span>

<span data-ttu-id="9fa2b-130">페더레이션 사용자 액세스를 허용하려면 조직에서 페더레이션을 지원하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="9fa2b-131">자세한 내용은 페더ation 및 공용 IM 연결 사용 또는 사용 안 [하도록 설정 을 참조 합니다.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="9fa2b-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="9fa2b-132">사용자 정책의 경우에는 페더레이션 사용자와 공동 작업하도록 할 사용자에게도 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="9fa2b-133">자세한 내용은 외부 사용자 액세스 [정책 할당을 참조합니다.](assign-an-external-user-access-policy.md)</span><span class="sxs-lookup"><span data-stu-id="9fa2b-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="9fa2b-134">페더화 도메인의 Windows PowerShell 액세스를 지원하기 위해 기존 정책을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="9fa2b-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="9fa2b-135">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9fa2b-136">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 서버,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa2b-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="9fa2b-137">비즈니스용 Skype 서버 관리 셸에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="9fa2b-138">"EnablePublicCloudAudioVideoAccess" 매개 변수에 비즈니스용 Skype 서버 제어판에서 해당 선택이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="9fa2b-139">페더화 도메인의 Windows PowerShell 액세스를 지원하기 위해 새 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="9fa2b-140">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9fa2b-141">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** Microsoft 비즈니스용 **Skype 서버,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fa2b-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="9fa2b-142">비즈니스용 Skype 서버 관리 셸에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="9fa2b-143">새 사이트 정책을 만드는 예:</span><span class="sxs-lookup"><span data-stu-id="9fa2b-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="9fa2b-144">페더화 도메인의 Windows PowerShell 액세스를 지원하기 위해 정책을 삭제하거나 다시 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9fa2b-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="9fa2b-145">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9fa2b-146">비즈니스용 Skype 서버 관리 셸에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="9fa2b-p107">글로벌 정책을 다시 설정하는 예(글로벌 정책은 해당 설정만 제거할 수 있으며, 정책 자체를 삭제할 수 없습니다.):</span><span class="sxs-lookup"><span data-stu-id="9fa2b-p107">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="9fa2b-149">사이트 정책을 제거하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="9fa2b-150">사이트 정책 Redmond를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="9fa2b-151">이름이 UserEAPPolicy인 사용자 정책을 삭제하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa2b-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="9fa2b-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fa2b-152">See Also</span></span>


[<span data-ttu-id="9fa2b-153">페더레이션 및 공개 IM 연결을 사용하도록 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="9fa2b-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="9fa2b-154">외부 사용자 액세스 정책 할당</span><span class="sxs-lookup"><span data-stu-id="9fa2b-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="9fa2b-155">조직의 SIP 페더레이션 도메인 관리</span><span class="sxs-lookup"><span data-stu-id="9fa2b-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="9fa2b-156">조직의 SIP 페더레이션 제공자 관리</span><span class="sxs-lookup"><span data-stu-id="9fa2b-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="9fa2b-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9fa2b-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="9fa2b-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9fa2b-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="9fa2b-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9fa2b-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="9fa2b-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9fa2b-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="9fa2b-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9fa2b-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

