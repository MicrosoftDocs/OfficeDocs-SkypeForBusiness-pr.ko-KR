---
title: Exchange Online을 사용 하 여 온-프레미스 Lync Server 통합 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae1ba45ace830f33b239bf2f8ead1a75fcee3417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="a778e-102">Exchange Online과 온-프레미스 Lync Server 2013 통합 구성</span><span class="sxs-lookup"><span data-stu-id="a778e-102">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a778e-103">_**마지막으로 수정한 주제:** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="a778e-103">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="a778e-104">온-프레미스 Lync Server 2013 배포를 사용 하는 고객은 하이브리드 배포 모드에서 Microsoft Exchange Online의 Microsoft Outlook Web App을 통해 상호 운용성을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-104">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="a778e-105">상호 운용성 기능에는 Outlook Web App 인터페이스와의 단일 사인온 및 인스턴트 메시징 (IM) 및 현재 상태 통합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-105">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="a778e-106">이 통합을 사용 하려면 다음 작업을 완료 하 여 온-프레미스 Lync Server 배포에서 Edge 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-106">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="a778e-107">공유 SIP 주소 공간 구성</span><span class="sxs-lookup"><span data-stu-id="a778e-107">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="a778e-108">Edge 서버에서 호스팅 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="a778e-108">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="a778e-109">업데이트 된 중앙 관리 저장소의 복제 확인</span><span class="sxs-lookup"><span data-stu-id="a778e-109">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="a778e-110">Lync Server 2013이 Exchange Online과 통합 되는 경우 OWA에서 IM에 로그인 하려는 사용자는 원격 또는 외부 사용자로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-110">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="a778e-111">이 시나리오에서는이 사용자에 게 다음과 같은 옵션이 선택 된 외부 액세스 정책이 할당 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-111">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="a778e-112">**원격 사용자와의 통신 설정**</span><span class="sxs-lookup"><span data-stu-id="a778e-112">**Enable communications with remote users**</span></span>

<span data-ttu-id="a778e-113">회사 사용자 (예: 재택 근무 중인 사용자)와 인터넷을 통해 Lync Server에 연결할 수 있으려면이 옵션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-113">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="a778e-114">자세한 내용은 [Lync Server 2013에서 외부 액세스 정책 관리](lync-server-2013-manage-external-access-policy-for-your-organization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a778e-114">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="a778e-115">공유 SIP 주소 공간 구성</span><span class="sxs-lookup"><span data-stu-id="a778e-115">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="a778e-116">Exchange Online에서 온-프레미스 Lync Server 2013을 통합 하려면 공유 SIP 주소 공간을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-116">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="a778e-117">Lync Server와 Exchange Online 서비스에서 모두 동일한 SIP 도메인 주소 공간이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-117">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="a778e-118">Lync Server Management Shell을 사용 하 여 다음 예제에 표시 된 매개 변수를 사용 하 여 **Set-CSAccessEdgeConfiguration** cmdlet을 실행 하 여 페더레이션의 Edge 서버를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-118">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="a778e-119">\*\*AllowFederatedUsers \*\*는 내부 사용자가 페더레이션 도메인 사용자와 통신할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-119">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="a778e-120">이 속성은 내부 사용자가 Lync Server 및 Exchange Online을 사용 하 여 공유 SIP 주소 공간 시나리오에서 사용자와 통신할 수 있는지 여부도 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-120">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="a778e-121">Lync Server Management Shell을 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013 관리 셸을](lync-server-2013-lync-server-management-shell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a778e-121">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="a778e-122">Edge 서버에서 호스팅 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="a778e-122">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="a778e-123">Lync Server Management Shell을 사용 하 여 Edge 서버에서 호스팅 공급자를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-123">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="a778e-124">이렇게 하려면 다음 예제의 매개 변수를 사용 하 여 **새-CsHostingProvider** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-124">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="a778e-125">중국에서 21Vianet에서 운영 하는 Office 365를 사용 하는 경우이 예제 ("exap.um.outlook.com")의 <STRONG>Proxyfqdn</STRONG> 매개 변수 값을 21vianet이 운영 하는 서비스의 FQDN으로 바꿉니다. "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="a778e-125">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="a778e-126">**Id** 는 만들려는 호스팅 공급자에 대 한 고유한 문자열 값 식별자를 지정 합니다 (예: "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="a778e-126">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="a778e-127">공백이 포함 된 값은 큰따옴표로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-127">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="a778e-128">\*\*Enabled \*\*는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-128">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="a778e-129">이를 **True**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-129">This must be set to **True**.</span></span>

  - <span data-ttu-id="a778e-130">**EnabledSharedAddressSpace** 는 호스팅 공급자가 공유 SIP 주소 공간 시나리오에 사용 되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-130">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="a778e-131">이를 **True**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-131">This must be set to **True**.</span></span>

  - <span data-ttu-id="a778e-132">**HostsOCSUsers** 는 호스팅 공급자를 사용 하 여 Office Communications Server 또는 Lync server를 호스트 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="a778e-133">이를 **False**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-133">This must be set to **False**.</span></span>

  - <span data-ttu-id="a778e-134">**Proxyfqdn** 은 호스팅 공급자가 사용 하는 프록시 서버의 정규화 된 도메인 이름 (FQDN)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-134">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="a778e-135">Exchange Online의 FQDN은 exap.um.outlook.com입니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-135">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="a778e-136">**Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 Lync server 토폴로지 내에 포함 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-136">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="a778e-137">이를 **False**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-137">This must be set to **False**.</span></span>

  - <span data-ttu-id="a778e-138">**VerificationLevel** 는 호스트 된 공급자에 게 전송 되는 메시지에 허용 되는 확인 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-138">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="a778e-139"># **Ource확인**을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-139">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="a778e-140">이 옵션은 호스팅 공급자가 보낸 메시지에 포함 된 확인 수준에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-140">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="a778e-141">이 수준을 지정 하지 않으면 메시지가 비안정형로 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-141">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="a778e-142">업데이트 된 중앙 관리 저장소의 복제 확인</span><span class="sxs-lookup"><span data-stu-id="a778e-142">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="a778e-143">앞의 섹션에서 cmdlet을 사용 하 여 변경한 내용은 Edge 서버에 자동으로 적용 되며, 일반적으로 복제 하는 데 1 분 미만이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-143">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="a778e-144">복제 상태를 확인 하 고 다음 cmdlet을 사용 하 여 변경 내용이 Edge 서버에 적용 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-144">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="a778e-145">Lync Server 배포의 서버 내부에서 복제 업데이트를 확인 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-145">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="a778e-146">변경 내용이 적용 되었는지 확인 하려면 Edge 서버에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a778e-146">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a778e-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a778e-147">See Also</span></span>


[<span data-ttu-id="a778e-148">호스팅된 Exchange UM에서 Lync Server 2013 사용자 음성 메일 제공</span><span class="sxs-lookup"><span data-stu-id="a778e-148">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="a778e-149">Lync Server 2013의 호스팅된 Exchange 통합 메시징 통합</span><span class="sxs-lookup"><span data-stu-id="a778e-149">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

