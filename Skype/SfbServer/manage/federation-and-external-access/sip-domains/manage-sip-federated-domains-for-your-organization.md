---
title: 조직의 SIP 페더레이션된 도메인 관리
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 페더레이션 할 수 있는 SIP 도메인을 관리 하 고 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 1a2f76f7f465401bae04b4defa2e0a1f5300ab0f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197489"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="5b8a5-103">비즈니스용 Skype 서버에서 조직의 SIP 페더레이션 도메인 관리</span><span class="sxs-lookup"><span data-stu-id="5b8a5-103">Manage SIP federated domains for your organization in Skype for Business Server</span></span>


<span data-ttu-id="5b8a5-104">페더레이션 할 수 있는 SIP 도메인을 관리 하 고 구성 하려면 다음을 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-104">To manage and configure SIP domains that you can federate with, you can do the following:</span></span>

  - <span data-ttu-id="5b8a5-105">SIP 페더레이션 파트너 도메인의 허용 된 도메인 목록을 만들거나 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-105">Create or edit an allowed domain list of SIP federated partner domains.</span></span>

  - <span data-ttu-id="5b8a5-106">SIP 페더레이션 도메인의 차단 된 도메인 목록을 만들거나 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-106">Create or edit a blocked domain list of SIP federated domains.</span></span>

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a><span data-ttu-id="5b8a5-107">비즈니스용 Skype 서버에서 허용 된 외부 도메인에 대 한 지원 구성</span><span class="sxs-lookup"><span data-stu-id="5b8a5-107">Configure support for allowed external domains in Skype for Business Server</span></span>

<span data-ttu-id="5b8a5-108">페더레이션 파트너에 대 한 지원을 구성한 경우 조직과 페더레이션 할 수 있는 특정 도메인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-108">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="5b8a5-109">하나 이상의 특정 외부 도메인을 허용 된 페더레이션 도메인으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-109">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="5b8a5-110">이렇게 하려면 허용 된 도메인 목록에 각 도메인을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-110">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="5b8a5-111">조직에서 파트너 검색을 사용할 수 있는 경우에도 사용자의 1000 이상 통신 해야 하는 페더레이션 파트너인 경우와 초당 20 개 이상의 메시지를 보내야 하는 경우이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-111">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="5b8a5-112">조직에서 파트너 검색을 사용할 수 없는 경우 허용 된 도메인 목록에 추가 되는 외부 도메인의 사용자만이 조직의 사용자와 IM 및 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-112">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="5b8a5-113">페더레이션 도메인에 대 한 액세스를 페더레이션 파트너의 액세스에 지 서비스를 실행 하는 특정 서버로 제한 하려는 경우 허용 된 도메인 목록에 있는 각 도메인에 대 한 액세스 경계 서비스를 실행 하는 서버의 도메인 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-113">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

> [!NOTE]  
> <span data-ttu-id="5b8a5-114">이 절차는 특정 도메인에 대 한 지원을 구성 하는 방법에 대해 설명 하지만, 페더레이션 사용자에 대 한 지원을 구현 하려면 조직의 페더레이션 사용자에 대 한 지원을 사용 하도록 설정 하 고 정책을 구성 및 적용 하 여 사용자가 수행할 수 있는 작업 제어 페더레이션 사용자와 공동 작업</span><span class="sxs-lookup"><span data-stu-id="5b8a5-114">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="5b8a5-115">페더레이션 사용자에 대 한 지원을 설정 하는 방법에 대 한 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안 함을](../access-edge/enable-or-disable-remote-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-115">For details about enabling support for federated users, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="5b8a5-116">정책 구성에 대 한 자세한 내용은 페더레이션 [사용자 액세스를 제어 하는 정책 구성을](../external-access-policies/configure-policies-to-control-federated-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-116">For details about configuring policies to control federation, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="5b8a5-117">허용 된 도메인 목록에 외부 도메인을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="5b8a5-117">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="5b8a5-118">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="5b8a5-119">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="5b8a5-120">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **페더레이션 도메인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-120">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>
4.  <span data-ttu-id="5b8a5-121">**페더레이션 도메인** 페이지에서 **새로 만들기**를 클릭 한 다음 허용 된 **도메인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-121">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>
5.  <span data-ttu-id="5b8a5-122">**새 페더레이션 도메인**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-122">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="5b8a5-123">**도메인 이름 (또는 FQDN)** 에 페더레이션 파트너 도메인의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-123">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>       

        > [!NOTE]  
        > <span data-ttu-id="5b8a5-124">이 이름은 고유 해야 하며 액세스에 지 서비스를 실행 하는이 서버에 허용 되는 도메인으로 이미 존재 하는 것이 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-124">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="5b8a5-125">이름 길이가 256 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-125">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="5b8a5-126">페더레이션 파트너 도메인 이름에서 검색 하면 접미사 일치가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-126">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="5b8a5-127">예를 들어 **contoso.com**를 입력 하는 경우 검색 에서도 도메인 **it.contoso.com**반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-127">For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="5b8a5-128">페더레이션 파트너 도메인은 동시에 차단 및 허용 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-128">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="5b8a5-129">비즈니스용 Skype 서버는이 문제가 발생 하지 않도록 하 여 목록을 동기화 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-129">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
    
      - <span data-ttu-id="5b8a5-130">이 페더레이션 도메인에 대 한 액세스를 액세스에 지 서비스를 실행 하는 특정 서버의 사용자에 게 제한 하려면 액세스 edge 서비스 **(FQDN)** 에 액세스에 지 서비스를 실행 하는 페더레이션 도메인 서버의 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-130">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>    
      - <span data-ttu-id="5b8a5-131">추가 정보를 제공 하려는 경우 **설명**에이 구성에 대 한 다른 시스템 관리자와 공유 하려는 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-131">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="5b8a5-132">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-132">Click **Commit**.</span></span>
7.  <span data-ttu-id="5b8a5-133">허용 하려는 각 페더레이션 파트너 도메인에 대해 4 ~ 6 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-133">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="5b8a5-134">페더레이션 사용자 액세스를 사용 하도록 설정 하려면 조직에서 페더레이션된 사용자 액세스에 대 한 지원도 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-134">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="5b8a5-135">자세한 내용은 [원격 사용자 액세스 설정 또는 해제](../access-edge/enable-or-disable-remote-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-135">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="5b8a5-136">또한 페더레이션 사용자와 공동 작업을 수행할 수 있는 사용자에 게 정책을 구성 하 고 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-136">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="5b8a5-137">자세한 내용은 [페더레이션 사용자 액세스를 제어 하도록 정책 구성을](../external-access-policies/configure-policies-to-control-federated-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-137">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a><span data-ttu-id="5b8a5-138">비즈니스용 Skype 서버에서 차단 된 외부 도메인에 대 한 지원 구성</span><span class="sxs-lookup"><span data-stu-id="5b8a5-138">Configure support for blocked external domains in Skype for Business Server</span></span> 

<span data-ttu-id="5b8a5-139">페더레이션 파트너에 대 한 지원을 구성한 경우 조직과 페더레이션 할 때 차단 될 도메인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-139">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="5b8a5-140">차단 된 도메인 목록은 차단 목록 (허용 되지 않는 명시적인 항목이 나열 됨)으로 작동 하며,이 옵션을 사용 하도록 설정한 경우 페더레이션 도메인 검색에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-140">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="5b8a5-141">자세한 내용은 [페더레이션 파트너 검색 사용 또는 사용 안 함을](../access-edge/enable-or-disable-discovery-of-federation-partners.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-141">For details, see [Enable or disable discovery of federation partners](../access-edge/enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="5b8a5-142">하나 이상의 외부 도메인이 조직에 연결 되지 않도록 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-142">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="5b8a5-143">이렇게 하려면 도메인을 차단 된 도메인 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-143">To do this, add the domain to the list of blocked domains.</span></span>


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="5b8a5-144">차단 된 도메인 목록에 외부 도메인을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="5b8a5-144">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="5b8a5-145">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="5b8a5-146">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-146">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="5b8a5-147">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-147">In the left navigation bar, click **External User Access**.</span></span>
4.  <span data-ttu-id="5b8a5-148">**페더레이션 도메인**을 클릭 하 고 **새로 만들기**를 클릭 한 다음 **차단 된 도메인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-148">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>
5.  <span data-ttu-id="5b8a5-149">**새 페더레이션 도메인**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-149">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="5b8a5-150">**도메인 이름 (또는 FQDN)** 에 차단 하려는 페더레이션 파트너 도메인의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-150">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>

        > [!NOTE]  
        > <span data-ttu-id="5b8a5-151">이름 길이가 256 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-151">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="5b8a5-152">페더레이션 파트너 도메인 이름에서 검색 하면 접미사 일치가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-152">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="5b8a5-153">예를 들어 **contoso.com**를 입력 하는 경우 검색 에서도 도메인 **it.contoso.com**반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-153">For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="5b8a5-154">페더레이션 파트너 도메인은 동시에 차단 및 허용 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-154">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="5b8a5-155">비즈니스용 Skype 서버는이 문제가 발생 하지 않도록 하 여 목록을 동기화 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-155">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
   
      - <span data-ttu-id="5b8a5-156">) **메모**에이 구성에 대해 다른 시스템 관리자와 공유 하려는 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-156">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="5b8a5-157">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-157">Click **Commit**.</span></span>
7.  <span data-ttu-id="5b8a5-158">차단 하려는 각 페더레이션 파트너에 대해 4 ~ 6 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-158">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="5b8a5-159">페더레이션 사용자 액세스를 사용 하도록 설정 하려면 조직에서 페더레이션된 사용자 액세스에 대 한 지원도 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-159">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="5b8a5-160">자세한 내용은 [원격 사용자 액세스 설정 또는 해제](../access-edge/enable-or-disable-remote-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-160">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="5b8a5-161">또한 페더레이션 사용자와 공동 작업을 수행할 수 있는 사용자에 게 정책을 구성 하 고 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-161">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="5b8a5-162">자세한 내용은 [페더레이션 사용자 액세스를 제어 하도록 정책 구성을](../external-access-policies/configure-policies-to-control-federated-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b8a5-162">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="5b8a5-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b8a5-163">See Also</span></span>

[<span data-ttu-id="5b8a5-164">페더레이션 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5b8a5-164">Configure policies to control federated user access</span></span>](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[<span data-ttu-id="5b8a5-165">페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5b8a5-165">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[<span data-ttu-id="5b8a5-166">페더레이션 파트너 검색 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5b8a5-166">Enable or disable discovery of federation partners</span></span>](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

