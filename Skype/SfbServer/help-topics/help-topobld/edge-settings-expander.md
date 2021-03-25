---
title: 에지 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 다음 섹션에서 기존 단일/다중 서버 에지 풀의 설정을 편집할 수 있습니다.
ms.openlocfilehash: 5b4bbb302f76a38a5a485d17ad6df5c0d1db1c6b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119657"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="977c7-103">에지 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="977c7-103">Edge Settings Expander</span></span>

<span data-ttu-id="977c7-104">다음 섹션에서 기존 단일/다중 서버 에지 풀의 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="977c7-105">일반 설정</span><span class="sxs-lookup"><span data-stu-id="977c7-105">General settings</span></span>

- <span data-ttu-id="977c7-106">다음 홉 선택 설정</span><span class="sxs-lookup"><span data-stu-id="977c7-106">Next hop selection settings</span></span>

- <span data-ttu-id="977c7-107">에지 서버 구성</span><span class="sxs-lookup"><span data-stu-id="977c7-107">Edge Server configuration</span></span>



## <a name="general-settings"></a><span data-ttu-id="977c7-108">일반 설정</span><span class="sxs-lookup"><span data-stu-id="977c7-108">General settings</span></span>

<span data-ttu-id="977c7-p101">에지 서버 풀의 내부 풀 FQDN(정규화된 도메인 이름) 이 설정을 변경하려면 풀의 FQDN을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="977c7-111">Lync Server 2013, Microsoft Lync Server 2010 또는 Microsoft Office Communications Server 2007 R2 트러스트된 파트너와의 페더미스를 설정하려면 이 에지 풀에 페더전 사용(포트 **5061)** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Lync Server 2013, Microsoft Lync Server 2010 or Microsoft Office Communications Server 2007 R2 trusted partner.</span></span>

<span data-ttu-id="977c7-112">XMPP 페더레이션을 사용하도록 설정하려면 **이 에지 풀에 XMPP 페더레이션 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-112">Select **Enable XMPP federation for this Edge pool** to enable XMPP federation.</span></span>

<span data-ttu-id="977c7-113">**내부 구성 복제 포트(HTTPS)** 의 포트 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-113">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="977c7-114">다음 홉 선택 설정</span><span class="sxs-lookup"><span data-stu-id="977c7-114">Next hop selection settings</span></span>

<span data-ttu-id="977c7-115">에지 서버에서  내부 인프라와 통신하는 데 사용할 다음 홉 풀을 설정하거나 수정하려면 드롭다운 목록 상자에서 Director, Director 풀, 프런트 엔드 서버 또는 프런트 엔드 서버 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-115">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="977c7-116">토폴로지 작성기에서 구성된 Director 또는 프런트 엔드만 선택에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-116">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="977c7-117">에지 서버 구성</span><span class="sxs-lookup"><span data-stu-id="977c7-117">Edge Server configuration</span></span>

<span data-ttu-id="977c7-118">에지 서버의 **외부 설정** 에 대한 설정을 편집하거나 지정하려면 먼저 SIP 액세스, 웹 회의 및 오디오/비디오 서비스에 서로 다른 IP 주소를 사용할지를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-118">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="977c7-p103">각각에 대해 서로 다른 IP 주소를 사용하려는 경우 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 확인란을 선택합니다. 각 서비스에는 각 서비스에 대해 만들어진 해당 DNS 호스트(A) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="977c7-p104">각 외부 연결 서비스에 대해 FQDN 및 연결된 포트를 지정합니다. 예를 들어 **SIP 액세스** 에서 sip.contoso.com과 연결된 포트 5061을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="977c7-123">각 외부 연결 서비스에 대해 서로 다른 FQDN을 선택하는 경우 각 서비스에 각 서비스와 연결된 고유한 포트 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-123">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it.</span></span> <span data-ttu-id="977c7-124">기본적으로 SIP는 포트 5061/TLS에 있으며, 웹 회의 에지 서비스는 포트 444/TLS에 있으며, A/V 회의 서버는 포트 443/TLS에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-124">By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS.</span></span> <span data-ttu-id="977c7-125">서로 다른 FQDN 및 IP 주소 또는 포트 사용을 비롯한 이러한 설정을 변경하는 경우 처음 구성된 값을 사용하는 다른 서비스를 모두 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-125">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="977c7-p106">조직에서 외부 연결 서비스에 단일 FQDN 및 IP 주소를 사용하기로 결정한 경우 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 확인란을 선택 취소합니다. 그러면 필요한 경우 **SIP 액세스** 풀 FQDN 및 포트 값을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="977c7-128">서로 다른 FQDN 및 IP 주소 또는 포트 사용을 비롯한 이러한 설정을 변경하는 경우 처음 구성된 값을 사용하는 다른 서비스를 모두 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="977c7-128">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="977c7-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="977c7-129">See also</span></span>

<span data-ttu-id="977c7-130">에지 서비스의 설정을 정의 및 구성하는 방법에 대한 자세한 내용은 [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="977c7-130">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span></span>