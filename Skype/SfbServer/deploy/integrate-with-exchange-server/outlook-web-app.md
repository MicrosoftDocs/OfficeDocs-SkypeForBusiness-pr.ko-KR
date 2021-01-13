---
title: 비즈니스용 Skype 서버와 비즈니스용 Skype 서버 간의 Outlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: '요약: 비즈니스용 Skype 서버와 비즈니스용 Skype Outlook Web App.'
ms.openlocfilehash: 0a6358c93356bd059aeed34033b07916d856bf10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833968"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="deb44-103">비즈니스용 Skype 서버와 비즈니스용 Skype 서버 간의 Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="deb44-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="deb44-104">**요약:** 비즈니스용 Skype 서버와 비즈니스용 Skype Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="deb44-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="deb44-105">비즈니스용 Skype 서버 배포를 사용하는 고객은 하이브리드 배포 모드에서 Microsoft Outlook Web App 서버와의 Microsoft Exchange Online 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="deb44-106">상호 운용성 기능에는 Outlook Web App 인터페이스와 통합된 Single Sign-On, 메신저, 현재 상태 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="deb44-107">이 통합을 사용하도록 설정하려면 다음 작업을 완료하여 비즈니스용 Skype 서버 배포에서 에지 서버를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="deb44-108">공유 SIP 주소 공간 구성</span><span class="sxs-lookup"><span data-stu-id="deb44-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="deb44-109">에지 서버에서 호스팅 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="deb44-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="deb44-110">업데이트된 중앙 관리 저장소 복제 확인</span><span class="sxs-lookup"><span data-stu-id="deb44-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="deb44-111">공유 SIP 주소 공간 구성</span><span class="sxs-lookup"><span data-stu-id="deb44-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="deb44-112">Exchange Online과 비즈니스용 Skype 서버를 통합하려면 공유 SIP 주소 공간을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="deb44-113">동일한 SIP 도메인 주소 공간은 비즈니스용 Skype 서버와 Exchange Online 서비스에서 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="deb44-114">비즈니스용 Skype 서버 관리 셸을 사용하여 다음 예에 표시된 매개 변수를 사용하여 **Set-CSAccessEdgeConfiguration** cmdlet을 실행하여 페더에 대한 에지 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="deb44-115">**AllowFederatedUsers** 매개 변수는 내부 사용자가 페더레이션 도메인의 사용자와 통신하도록 허용되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="deb44-116">이 속성은 내부 사용자가 비즈니스용 Skype 서버 및 Exchange Online을 사용하여 공유 SIP 주소 공간 시나리오의 사용자와 통신할 수 있는지 여부도 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="deb44-117">비즈니스용 Skype 서버 관리 셸 사용에 대한 자세한 내용은 [비즈니스용 Skype 서버 관리 셸을 참조하세요.](../../manage/management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="deb44-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="deb44-118">에지 서버에서 호스팅 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="deb44-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="deb44-119">비즈니스용 Skype 서버 관리 셸을 사용하여 다음 예의 매개 변수를 사용하여 **New-CsHostingProvider** cmdlet을 실행하여 에지 서버에서 호스팅 공급자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="deb44-120">중국의 21Vianet에서 운영하는 Microsoft 365 또는 Office 365를 사용하는 경우 이 예의 ProxyFqdn 매개 변수 값("exap.um.outlook.com")을 21Vianet에서 운영하는 서비스의 FQDN인 "exap.um.partner.outlook.cn"로 바랜다.</span><span class="sxs-lookup"><span data-stu-id="deb44-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="deb44-121">Microsoft 365 또는 Office 365 GCC High를 사용하는 경우 이 예제의 ProxyFqdn 매개 변수 값("exap.um.outlook.com")을 GCC High에 대한 FQDN인 "exap.um.office365.us"로 바랜다.</span><span class="sxs-lookup"><span data-stu-id="deb44-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="deb44-122">**ID는** 만들 호스팅 공급자의 고유 문자열 값 식별자(예: "Exchange Online")를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="deb44-123">공백이 포함된 값은 큰따옴표로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="deb44-124">**Enabled** 는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="deb44-125">True로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-125">This must be set to True.</span></span>

- <span data-ttu-id="deb44-126">**EnabledSharedAddressSpace** 는 공유 SIP 주소 공간 시나리오에서 호스팅 공급자를 사용할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="deb44-127">True로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-127">This must be set to True.</span></span>

- <span data-ttu-id="deb44-128">**HostsOCSUsers는** 호스팅 공급자가 Office Communications Server 또는 비즈니스용 Skype 서버를 호스팅하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="deb44-129">False로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-129">This must be set to False.</span></span>

- <span data-ttu-id="deb44-130">**ProxyFQDN** 은 호스팅 공급자가 사용하는 프록시 서버의 FQDN(정규화된 도메인 이름)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="deb44-131">Exchange Online의 경우 FQDN은 exap.um.outlook.com입니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="deb44-132">**IsLocal은** 호스팅 공급자가 사용하는 프록시 서버가 비즈니스용 Skype 서버 토폴로지 내에 포함되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="deb44-133">False로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-133">This must be set to False.</span></span>

- <span data-ttu-id="deb44-134">**VerificationLevel** 호스팅된 공급자와 보내고 보낸 메시지에 허용되는 확인 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="deb44-135">호스팅 공급자에서 보낸 메시지에 포함된 확인 수준에 따라 **UseSourceVerification을** 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="deb44-136">이 수준을 지정하지 않으면 메시지가 확인되지 않는 것으로 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="deb44-137">업데이트된 중앙 관리 저장소의 복제 확인</span><span class="sxs-lookup"><span data-stu-id="deb44-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="deb44-138">이전 섹션의 cmdlet을 사용하여 변경한 내용은 에지 서버에 자동으로 적용되며 일반적으로 복제하는 데 1분 미만이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="deb44-139">복제 상태의 유효성을 검사한 다음 다음 cmdlet을 사용하여 변경 내용이 에지 서버에 적용된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="deb44-140">복제 업데이트를 확인하기 위해 비즈니스용 Skype 서버 배포의 내부 서버에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="deb44-141">UpToDate 값이 모든 복제본에 대해 TRUE를 표시하는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="deb44-142">변경 내용이 적용된지 확인을 위해 에지 서버에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="deb44-143">표시된 정보가 이전 단계에서 커밋된 변경 내용과 일치하는지 다시 한 번 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="deb44-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="deb44-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="deb44-144">See also</span></span>

[<span data-ttu-id="deb44-145">호스팅된 Exchange UM에서 비즈니스용 Skype 서버 사용자에게 음성 메일 제공</span><span class="sxs-lookup"><span data-stu-id="deb44-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="deb44-146">비즈니스용 Skype 서버에서 호스팅된 Exchange 통합 메시징 통합</span><span class="sxs-lookup"><span data-stu-id="deb44-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
