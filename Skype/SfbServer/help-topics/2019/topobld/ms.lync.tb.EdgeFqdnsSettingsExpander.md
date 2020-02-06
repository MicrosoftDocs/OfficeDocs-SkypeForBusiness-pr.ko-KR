---
title: 에지 서버 FQDN 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
ROBOTS: NOINDEX, NOFOLLOW
description: 에지 서버의 외부 설정을 편집하거나 지정하려면 먼저 SIP(Session Initiation Protocol) 액세스, 웹 회의 에지 서비스, 오디오/비디오 에지 서비스에 대해 서로 다른 IP 주소를 사용할지 여부를 결정해야 합니다.
ms.openlocfilehash: 4cf7d04ed94a867dcf1e351868cc205aac2439b0
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793816"
---
# <a name="edge-server-fqdns-settings-expander"></a><span data-ttu-id="3ac9b-103">에지 서버 FQDN 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="3ac9b-103">Edge Server FQDNs Settings Expander</span></span>

<span data-ttu-id="3ac9b-104">에지 서버의 **외부 설정**을 편집하거나 지정하려면 먼저 SIP(Session Initiation Protocol) 액세스, 웹 회의 에지 서비스, 오디오/비디오 에지 서비스에 대해 서로 다른 IP 주소를 사용할지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ac9b-104">To edit or specify **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for Session Initiation Protocol (SIP) access, the Web Conferencing Edge service, and the Audio/Video Edge service.</span></span>

<span data-ttu-id="3ac9b-p101">각각에 대해 서로 다른 IP 주소를 사용하려는 경우 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 확인란을 선택합니다. 각 서비스에는 각 서비스에 대해 만들어진 해당 DNS(Domain Name System) 호스트(A) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ac9b-p101">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding Domain Name System (DNS) host (A) record created for it.</span></span>

<span data-ttu-id="3ac9b-p102">각 외부 연결 서비스에 대해 FQDN(정규화된 도메인 이름) 및 연결된 포트를 지정합니다. 예를 들어 **SIP 액세스**에 sip.contoso.com과 연결된 포트 5061을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ac9b-p102">For each of the external-facing services, specify a fully qualified domain name (FQDN) and an associated port. For example, for **SIP Access**, you might use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ac9b-p103">각 외부 연결 서비스에 대해 서로 다른 FQDN을 선택하는 경우 각 서비스에 각 서비스와 연결된 고유한 포트 값이 있어야 합니다. 기본적으로 SIP는 포트 5061/TLS에 있고, 웹 회의 에지 서비스는 포트 444/TLS에 있으며, A/V 회의 에지 서비스는 포트 443/TLS에 있습니다. 서로 다른 FQDN 및 IP 주소 또는 포트 사용을 비롯한 이러한 설정을 변경하는 경우 처음 구성된 값을 사용하는 다른 서비스를 모두 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ac9b-p103">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, SIP is on port 5061/TLS, the Web Conferencing Edge service is on port 444/TLS, and the A/V Conferencing Edge service is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="3ac9b-p104">조직에서 외부 연결 서비스에 단일 FQDN 및 IP 주소를 사용하기로 결정한 경우 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 확인란을 선택 취소합니다. 그러면 필요한 경우 **SIP 액세스** 풀 FQDN 및 포트 값을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ac9b-p104">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ac9b-114">서로 다른 FQDN 및 IP 주소 또는 포트 사용을 비롯한 이러한 설정을 변경하는 경우 처음 구성된 값을 사용하는 다른 서비스를 모두 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ac9b-114">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="3ac9b-115">에지 서비스의 설정을 정의 및 구성하는 방법에 대한 자세한 내용은 [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ac9b-115">For details about defining and configuring the settings for the Edge services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


