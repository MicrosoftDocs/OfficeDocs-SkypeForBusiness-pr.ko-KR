---
title: 온-프레미스 비즈니스용 Skype 서버 및 Outlook Web App 간 통합 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버 및 Outlook Web App을 통합 합니다.'
ms.openlocfilehash: ee5676c0dbe88568af78a1c278eea8a46457cb5c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221188"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="fe223-103">온-프레미스 비즈니스용 Skype 서버 및 Outlook Web App 간 통합 구성</span><span class="sxs-lookup"><span data-stu-id="fe223-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="fe223-104">**요약:** 비즈니스용 Skype 서버 및 Outlook Web App을 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="fe223-105">온-프레미스 비즈니스용 Skype 서버 배포를 사용 하는 고객은 하이브리드 배포 모드에서 Microsoft Exchange Online의 Microsoft Outlook Web App과의 상호 운용성을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="fe223-106">상호 운용성 기능에는 Outlook Web App 인터페이스와 통합된 Single Sign-On, 메신저, 현재 상태 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="fe223-107">이 통합을 사용 하려면 다음 작업을 완료 하 여 온-프레미스 비즈니스용 Skype 서버 배포에에 지 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="fe223-108">공유 SIP 주소 공간 구성</span><span class="sxs-lookup"><span data-stu-id="fe223-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="fe223-109">에 지 서버에서 호스팅 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="fe223-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="fe223-110">업데이트 된 중앙 관리 저장소의 복제 확인</span><span class="sxs-lookup"><span data-stu-id="fe223-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="fe223-111">공유 SIP 주소 공간 구성</span><span class="sxs-lookup"><span data-stu-id="fe223-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="fe223-112">Exchange Online을 사용 하 여 온-프레미스 비즈니스용 Skype 서버를 통합 하려면 공유 SIP 주소 공간을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="fe223-113">동일한 SIP 도메인 주소 공간은 비즈니스용 Skype 서버 및 Exchange Online 서비스에서 모두 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="fe223-114">비즈니스용 Skype 서버 관리 셸을 사용 하 여 다음 예에 표시 된 매개 변수를 사용 하 여 **set-csaccessedgeconfiguration** cmdlet을 실행 하 여 페더레이션을 위한에 지 서버를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="fe223-115">**AllowFederatedUsers** 매개 변수는 내부 사용자가 페더레이션 도메인의 사용자와 통신하도록 허용되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="fe223-116">또한이 속성은 내부 사용자가 비즈니스용 Skype 서버 및 Exchange Online을 사용 하는 공유 SIP 주소 공간 시나리오에서 사용자와 통신할 수 있는지 여부도 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="fe223-117">비즈니스용 Skype 서버 관리 셸을 사용 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype 서버 관리 셸을](../../manage/management-shell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe223-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="fe223-118">에지 서버에서 호스팅 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="fe223-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="fe223-119">비즈니스용 Skype 서버 관리 셸을 사용 하 여 다음 예제의 매개 변수를 사용 하 여 **새-CsHostingProvider** cmdlet을 실행 하 여에 지 서버에서 호스팅 공급자를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="fe223-120">중국의 21Vianet에서 운영 하는 Microsoft 365 또는 Office 365을 사용 하는 경우,이 예의 ProxyFqdn 매개 변수 값 ("exap.um.outlook.com")을 21Vianet에서 운영 하는 서비스의 FQDN으로 바꿉니다 ("exap.um.partner.outlook.cn").</span><span class="sxs-lookup"><span data-stu-id="fe223-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="fe223-121">Microsoft 365 또는 Office 365 GCC High를 사용 하는 경우이 예제 ("exap.um.outlook.com")에서 ProxyFqdn 매개 변수의 값을 GCC High: "exap.um.office365.us"에 대 한 FQDN으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="fe223-122">**Identity** 는 만들려는 호스팅 공급자에 대 한 고유 문자열 값 식별자를 지정 합니다 (예: "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="fe223-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="fe223-123">공백이 포함된 값은 큰따옴표로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="fe223-124">**Enabled**는 도메인과 호스팅 공급자 간의 네트워크 연결을 활성화할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="fe223-125">True로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-125">This must be set to True.</span></span>

- <span data-ttu-id="fe223-126">**EnabledSharedAddressSpace**는 공유 SIP 주소 공간 시나리오에서 호스팅 공급자를 사용할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="fe223-127">True로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-127">This must be set to True.</span></span>

- <span data-ttu-id="fe223-128">**HostsOCSUsers** 는 호스팅 공급자가 Office Communications Server 또는 비즈니스용 Skype 서버를 호스트 하는 데 사용 되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="fe223-129">False로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-129">This must be set to False.</span></span>

- <span data-ttu-id="fe223-130">**ProxyFQDN**은 호스팅 공급자가 사용하는 프록시 서버의 FQDN(정규화된 도메인 이름)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="fe223-131">Exchange Online의 경우 FQDN은 exap.um.outlook.com입니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="fe223-132">**Islocal** 은 호스팅 공급자가 사용 하는 프록시 서버가 비즈니스용 Skype 서버 토폴로지에 포함 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="fe223-133">False로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-133">This must be set to False.</span></span>

- <span data-ttu-id="fe223-134">**Verificationlevel은** 호스팅된 공급자에 게 전송 되는 메시지에 허용 되는 확인 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="fe223-135">호스팅 공급자가 보낸 메시지에 포함 된 확인 수준에 의존 하는 # # **인증**을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="fe223-136">이 수준을 지정 하지 않으면 메시지가 확인할 수 없는 것으로 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="fe223-137">업데이트된 중앙 관리 저장소의 복제 확인</span><span class="sxs-lookup"><span data-stu-id="fe223-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="fe223-138">이전 섹션의 cmdlet을 사용 하 여 변경한 내용은에 지 서버에 자동으로 적용 되며, 일반적으로 복제 하는 데 1 분이 걸리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="fe223-139">복제 상태를 확인 한 후 다음 cmdlet을 사용 하 여 변경 내용이에 지 서버에 적용 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="fe223-140">복제 업데이트를 확인 하려면 비즈니스용 Skype 서버 배포의 내부 서버에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="fe223-141">모든 복제본에 대해 UpToDate 값이 TRUE를 표시 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="fe223-142">변경 내용이 적용 되었는지 확인 하려면에 지 서버에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="fe223-143">표시 된 정보가 이전 단계에서 커밋된 변경 내용과 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe223-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe223-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe223-144">See also</span></span>

[<span data-ttu-id="fe223-145">호스팅된 Exchange UM에서 비즈니스용 Skype 서버 사용자에 게 음성 메일 제공</span><span class="sxs-lookup"><span data-stu-id="fe223-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="fe223-146">비즈니스용 Skype 서버의 호스팅된 Exchange 통합 메시징 통합</span><span class="sxs-lookup"><span data-stu-id="fe223-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
