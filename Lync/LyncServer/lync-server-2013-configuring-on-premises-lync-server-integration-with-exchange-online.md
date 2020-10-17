---
title: Exchange Online과 온-프레미스 Lync Server의 통합 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e65e5a97a73f7170820f24778a74c8a1ffac04b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532535"
---
# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="ba141-102">Exchange Online과 온-프레미스 Lync Server 2013의 통합 구성</span><span class="sxs-lookup"><span data-stu-id="ba141-102">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba141-103">_**마지막으로 수정 된 항목:** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="ba141-103">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="ba141-104">온-프레미스 Lync Server 2013 배포를 사용 하는 고객은 하이브리드 배포 모드에서 Microsoft Exchange Online의 Microsoft Outlook Web App과의 상호 운용성을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-104">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="ba141-105">상호 운용성 기능에는 Outlook Web App 인터페이스와 통합된 Single Sign-On, 메신저, 현재 상태 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-105">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="ba141-106">이 통합을 사용 하려면 다음 작업을 완료 하 여 온-프레미스 Lync Server 배포에서에 지 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-106">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="ba141-107">공유 SIP 주소 공간 구성</span><span class="sxs-lookup"><span data-stu-id="ba141-107">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="ba141-108">에 지 서버에서 호스팅 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="ba141-108">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="ba141-109">업데이트 된 중앙 관리 저장소의 복제 확인</span><span class="sxs-lookup"><span data-stu-id="ba141-109">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="ba141-110">Lync Server 2013이 Exchange Online과 통합 된 경우 OWA에서 IM에 로그인을 시도 하는 사용자는 원격 또는 외부 사용자로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-110">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="ba141-111">이 시나리오에서는이 사용자에 게 다음 옵션을 선택 하는 외부 액세스 정책이 할당 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-111">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="ba141-112">**원격 사용자와의 통신 사용**</span><span class="sxs-lookup"><span data-stu-id="ba141-112">**Enable communications with remote users**</span></span>

<span data-ttu-id="ba141-113">조직의 사용자 (예: 재택 근무자, 출장 중인 사용자)가 인터넷을 통해 Lync Server에 연결할 수 있게 하려면이 옵션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-113">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="ba141-114">자세한 내용은 [Lync Server 2013에서 외부 액세스 정책 관리](lync-server-2013-manage-external-access-policy-for-your-organization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ba141-114">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="ba141-115">공유 SIP 주소 공간 구성</span><span class="sxs-lookup"><span data-stu-id="ba141-115">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="ba141-116">Exchange Online과 온-프레미스 Lync Server 2013을 통합 하려면 공유 SIP 주소 공간을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-116">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="ba141-117">Lync Server와 Exchange Online 서비스 둘 다에서 동일한 SIP 도메인 주소 공간이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-117">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="ba141-118">Lync Server 관리 셸을 사용 하 여 다음 예에 표시 된 매개 변수를 사용 하 여 **set-csaccessedgeconfiguration** cmdlet을 실행 하 여 페더레이션을 위한에 지 서버를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-118">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="ba141-119">**AllowFederatedUsers**는 내부 사용자가 페더레이션 도메인 사용자와 통신할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-119">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="ba141-120">또한이 속성은 내부 사용자가 Lync Server 및 Exchange Online을 사용 하는 공유 SIP 주소 공간 시나리오에서 사용자와 통신할 수 있는지 여부도 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-120">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="ba141-121">Lync Server 관리 셸을 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013 관리 셸을](lync-server-2013-lync-server-management-shell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ba141-121">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="ba141-122">에지 서버에서 호스팅 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="ba141-122">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="ba141-123">Lync Server 관리 셸을 사용 하 여에 지 서버에서 호스팅 공급자를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-123">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="ba141-124">이 작업을 수행 하려면 다음 예제의 매개 변수를 사용 하 여 **새-CsHostingProvider** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-124">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="ba141-125">중국에서 21Vianet에서 운영 하는 Office 365을 사용 하는 경우이 예의 <STRONG>proxyfqdn</STRONG> 매개 변수 값 ("exap.um.outlook.com")을 21vianet에서 운영 하는 서비스에 대 한 FQDN으로 바꿉니다. "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="ba141-125">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="ba141-126">**Identity** 는 만들려는 호스팅 공급자에 대 한 고유 문자열 값 식별자를 지정 합니다 (예: "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="ba141-126">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="ba141-127">공백이 포함 된 값은 큰따옴표로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-127">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="ba141-128">**Enabled**는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-128">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="ba141-129">이를 **True**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-129">This must be set to **True**.</span></span>

  - <span data-ttu-id="ba141-130">**EnabledSharedAddressSpace**는 공유 SIP 주소 공간 시나리오에서 호스팅 공급자를 사용할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-130">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="ba141-131">이를 **True**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-131">This must be set to **True**.</span></span>

  - <span data-ttu-id="ba141-132">**HostsOCSUsers** 는 호스팅 공급자가 Office Communications Server 또는 Lync Server를 호스트 하는 데 사용 되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="ba141-133">이를 **False**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-133">This must be set to **False**.</span></span>

  - <span data-ttu-id="ba141-134">**ProxyFQDN**은 호스팅 공급자가 사용하는 프록시 서버의 FQDN(정규화된 도메인 이름)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-134">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="ba141-135">Exchange Online의 경우 FQDN은 exap.um.outlook.com입니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-135">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="ba141-136">**Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 Lync server 토폴로지 내에 포함 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-136">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="ba141-137">이를 **False**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-137">This must be set to **False**.</span></span>

  - <span data-ttu-id="ba141-138">**Verificationlevel은** 은 호스팅된 공급자에 게 전송 되는 메시지에 허용 되는 확인 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-138">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="ba141-139"># # **인증**을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-139">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="ba141-140">이 옵션은 호스팅 공급자가 보낸 메시지에 포함 된 확인 수준에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-140">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="ba141-141">이 수준을 지정 하지 않으면 메시지가 확인할 수 없는 것으로 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-141">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="ba141-142">업데이트된 중앙 관리 저장소의 복제 확인</span><span class="sxs-lookup"><span data-stu-id="ba141-142">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="ba141-143">이전 섹션의 cmdlet을 사용 하 여 변경한 내용은에 지 서버에 자동으로 적용 되며, 일반적으로 복제 하는 데 1 분이 걸리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-143">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="ba141-144">다음 cmdlet을 사용 하 여 복제 상태를 확인 하 고 변경 내용이에 지 서버에 적용 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-144">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="ba141-145">Lync Server 배포의 내부 서버에서 복제 업데이트를 확인 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-145">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="ba141-146">변경 내용이 적용 되었는지 확인 하려면에 지 서버에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba141-146">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ba141-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba141-147">See Also</span></span>


[<span data-ttu-id="ba141-148">Lync Server 2013 users 사용자에 게 호스팅된 Exchange UM에 대 한 음성 메일 제공</span><span class="sxs-lookup"><span data-stu-id="ba141-148">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="ba141-149">Lync Server 2013의 호스팅된 Exchange 통합 메시징 통합</span><span class="sxs-lookup"><span data-stu-id="ba141-149">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
