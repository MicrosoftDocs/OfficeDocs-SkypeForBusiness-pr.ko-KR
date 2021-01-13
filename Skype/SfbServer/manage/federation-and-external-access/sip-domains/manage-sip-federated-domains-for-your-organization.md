---
title: 조직의 SIP 페더레이션 도메인 관리
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
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
description: 페더타할 수 있는 SIP 도메인을 관리 및 구성하는 방법을 알아보고,
ms.openlocfilehash: 7b04225542387d52a36533c9639b02f773731e9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817218"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="22008-103">비즈니스용 Skype 서버에서 조직의 SIP 페더전 도메인 관리</span><span class="sxs-lookup"><span data-stu-id="22008-103">Manage SIP federated domains for your organization in Skype for Business Server</span></span>


<span data-ttu-id="22008-104">페더레이션할 수 있는 SIP 도메인을 관리하고 구성하려면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22008-104">To manage and configure SIP domains that you can federate with, you can do the following:</span></span>

  - <span data-ttu-id="22008-105">SIP 페더레이션 파트너 도메인의 허용 도메인 목록을 만들거나 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-105">Create or edit an allowed domain list of SIP federated partner domains.</span></span>

  - <span data-ttu-id="22008-106">SIP 페더레이션 도메인의 차단 도메인 목록을 만들거나 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-106">Create or edit a blocked domain list of SIP federated domains.</span></span>

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a><span data-ttu-id="22008-107">비즈니스용 Skype 서버에서 허용되는 외부 도메인에 대한 지원 구성</span><span class="sxs-lookup"><span data-stu-id="22008-107">Configure support for allowed external domains in Skype for Business Server</span></span>

<span data-ttu-id="22008-p101">페더레이션 파트너에 대한 지원을 구성한 경우 조직과 페더레이션할 수 있는 특정 도메인을 관리할 수 있습니다. 하나 이상의 특정 외부 도메인을 허용된 페더레이션 도메인으로 구성합니다. 이렇게 하려면 각 도메인을 허용된 도메인 목록에 추가합니다. 조직에서 파트너 검색을 사용하는 경우에도 해당 도메인이 1,000명 이상의 사용자와 통신해야 하거나 초당 20개가 넘는 메시지를 보내야 할 수 있는 페더레이션 파트너인 경우에는 이와 같이 구성합니다. 조직에서 파트너 검색을 사용하지 않는 경우에는 허용된 도메인 목록에 추가하는 외부 도메인의 사용자만 조직 사용자와의 IM 및 회의에 참가할 수 있습니다. 페더레이션 도메인에 대한 액세스를 페더레이션 파트너의 액세스 에지 서비스를 실행하는 특정 서버로 제한하려면 허용된 도메인 목록의 각 도메인에 대해 액세스 에지 서비스를 실행하는 서버의 도메인 이름을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22008-p101">If you have configured support for federated partners, you can manage which specific domains can federate with your organization. You configure one or more specific external domains as allowed federated domains. To do this, add each domain to the list of allowed domains. Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second. If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization. If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

> [!NOTE]  
> <span data-ttu-id="22008-114">이 절차에서는 특정 도메인에 대한 지원을 구성하는 방법에 대해 설명하지만 페더레이션 사용자에 대한 지원을 구현하려면 조직에서 페더레이션 사용자를 지원하도록 설정하고 페더레이션 사용자와 공동 작업할 수 있는 사용자를 제어하는 정책을 구성하고 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-114">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="22008-115">페더링 사용자에 대한 지원을 사용하도록 설정하는 데 대한 자세한 내용은 원격 사용자 액세스 사용 또는 사용 안 [을 참조합니다.](../access-edge/enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="22008-115">For details about enabling support for federated users, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="22008-116">페더링을 제어하는 정책을 구성하는 데 대한 자세한 내용은 페더링된 사용자 액세스를 제어하도록 정책 구성을 [참조합니다.](../external-access-policies/configure-policies-to-control-federated-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="22008-116">For details about configuring policies to control federation, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="22008-117">허용 도메인 목록에 외부 도메인을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="22008-117">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="22008-118">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="22008-119">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="22008-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="22008-120">왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭한 다음 **페더레이션 도메인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-120">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>
4.  <span data-ttu-id="22008-121">**페더레이션 도메인** 페이지에서 **새로 만들기** 를 클릭한 다음 **허용 도메인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-121">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>
5.  <span data-ttu-id="22008-122">**새 페더레이션 도메인** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-122">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="22008-123">**도메인 이름 또는 FQDN** 에 페더레이션 파트너 도메인의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-123">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>       

        > [!NOTE]  
        > <span data-ttu-id="22008-p103">이 이름은 고유해야 하며, 액세스 에지 서비스를 실행하는 이 서버의 기존 허용 도메인과 같을 수 없습니다. 이름은 256자까지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22008-p103">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service. The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="22008-p104">페더레이션 파트너 도메인 이름 검색에서는 일치하는 접미사를 찾습니다. 예를 들어 **contoso.com** 을 입력하면 **it.contoso.com** 도메인도 검색 결과에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="22008-p104">The search on the federated partner domain name performs a suffix match. For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="22008-128">페더레이션 파트너 도메인은 동시에 차단하고 허용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22008-128">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="22008-129">비즈니스용 Skype 서버는 목록을 동기화하지 않도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-129">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
    
      - <span data-ttu-id="22008-130">이 페더레이션 도메인에 대한 액세스를 액세스 에지 서비스를 실행하는 특정 서버의 사용자로 제한하려면 **액세스 에지 서비스(FQDN)** 에 액세스 에지 서비스를 실행하는 페더레이션 도메인 서버의 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-130">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>    
      - <span data-ttu-id="22008-131">추가 정보를 제공하려면 **설명** 에 다른 시스템 관리자와 이 구성에 대해 공유할 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-131">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="22008-132">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-132">Click **Commit**.</span></span>
7.  <span data-ttu-id="22008-133">허용할 각 페더레이션 파트너 도메인에 대해 4~6단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-133">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="22008-134">페더레이션 사용자 액세스를 허용하려면 조직에서 페더레이션 사용자 액세스를 지원하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-134">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="22008-135">자세한 내용은 원격 사용자 액세스 사용 또는 [사용 안 하도록 설정 을 참조 합니다.](../access-edge/enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="22008-135">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="22008-136">또한 페더레이션 사용자와 공동 작업을 수행할 수 있도록 하려는 사용자에 대한 정책을 구성하고 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-136">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="22008-137">자세한 내용은 페더타 사용자 액세스를 제어하는 정책 구성을 [참조합니다.](../external-access-policies/configure-policies-to-control-federated-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="22008-137">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a><span data-ttu-id="22008-138">비즈니스용 Skype 서버에서 차단된 외부 도메인에 대한 지원 구성</span><span class="sxs-lookup"><span data-stu-id="22008-138">Configure support for blocked external domains in Skype for Business Server</span></span> 

<span data-ttu-id="22008-139">페더레이션 파트너에 대한 지원을 구성한 경우 조직과 페더레이션할 수 없도록 차단되는 도메인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22008-139">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="22008-140">차단된 도메인 목록은 차단 목록(허용되지 않는 항목에 대한 목록)으로 작동하며 이 옵션을 설정한 경우 페더레이션 도메인 검색에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="22008-140">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="22008-141">자세한 내용은 페더ation 파트너 검색 사용 또는 사용 [안 하도록 설정 을 참조하세요.](../access-edge/enable-or-disable-discovery-of-federation-partners.md)</span><span class="sxs-lookup"><span data-stu-id="22008-141">For details, see [Enable or disable discovery of federation partners](../access-edge/enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="22008-p109">하나 이상의 외부 도메인에서 조직에 연결하는 것을 차단합니다. 이렇게 하려면 차단된 도메인 목록에 도메인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-p109">Block one or more external domains from connecting to your organization. To do this, add the domain to the list of blocked domains.</span></span>


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="22008-144">차단된 도메인 목록에 외부 도메인을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="22008-144">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="22008-145">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="22008-146">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="22008-146">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="22008-147">왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-147">In the left navigation bar, click **External User Access**.</span></span>
4.  <span data-ttu-id="22008-148">**페더레이션 도메인** 에서 **새로 만들기** 를 클릭한 다음 **차단된 도메인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-148">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>
5.  <span data-ttu-id="22008-149">**새 페더레이션 도메인** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-149">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="22008-150">**도메인 이름 또는 FQDN** 에 차단할 페더레이션 파트너 도메인의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-150">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>

        > [!NOTE]  
        > <span data-ttu-id="22008-151">이름은 256자까지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22008-151">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="22008-p110">페더레이션 파트너 도메인 이름 검색에서는 일치하는 접미사를 찾습니다. 예를 들어 **contoso.com** 을 입력하면 **it.contoso.com** 도메인도 검색 결과에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="22008-p110">The search on the federated partner domain name performs a suffix match. For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="22008-154">페더레이션 파트너 도메인은 동시에 차단하고 허용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22008-154">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="22008-155">비즈니스용 Skype 서버는 목록을 동기화하지 않도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-155">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
   
      - <span data-ttu-id="22008-156">(선택 사항) **설명** 에 다른 시스템 관리자와 이 구성에 대해 공유할 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-156">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="22008-157">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-157">Click **Commit**.</span></span>
7.  <span data-ttu-id="22008-158">차단할 각 페더레이션 파트너에 대해 4~6단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-158">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="22008-159">페더레이션 사용자 액세스를 허용하려면 조직에서 페더레이션 사용자 액세스를 지원하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-159">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="22008-160">자세한 내용은 원격 사용자 액세스 사용 또는 [사용 안 하도록 설정 을 참조 합니다.](../access-edge/enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="22008-160">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="22008-161">또한 페더레이션 사용자와 공동 작업을 수행할 수 있도록 하려는 사용자에 대한 정책을 구성하고 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22008-161">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="22008-162">자세한 내용은 페더타 사용자 액세스를 제어하는 정책 [구성을 참조합니다.](../external-access-policies/configure-policies-to-control-federated-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="22008-162">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="22008-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22008-163">See Also</span></span>

[<span data-ttu-id="22008-164">페더레이션 사용자 액세스를 컨트롤하는 정책 구성</span><span class="sxs-lookup"><span data-stu-id="22008-164">Configure policies to control federated user access</span></span>](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[<span data-ttu-id="22008-165">페더레이션 및 공개 IM 연결을 사용하도록 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="22008-165">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[<span data-ttu-id="22008-166">페더레이션 파트너 검색을 사용하도록 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="22008-166">Enable or disable discovery of federation partners</span></span>](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

