---
title: Branch Office Appliance 일반 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 다음 섹션에서 기존 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 설정을 편집할 수 있습니다.
ms.openlocfilehash: 8f77a7b12800d9eba091218de92f4eec17bf2154
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119697"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="0b9ba-103">Branch Office Appliance 일반 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="0b9ba-103">Branch Office Appliance General Settings Expander</span></span>

<span data-ttu-id="0b9ba-104">다음 섹션에서 기존 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>

- <span data-ttu-id="0b9ba-105">일반 설정</span><span class="sxs-lookup"><span data-stu-id="0b9ba-105">General settings</span></span>

- <span data-ttu-id="0b9ba-106">복구 설정</span><span class="sxs-lookup"><span data-stu-id="0b9ba-106">Resiliency settings</span></span>

- <span data-ttu-id="0b9ba-107">중재 서버 설정</span><span class="sxs-lookup"><span data-stu-id="0b9ba-107">Mediation Server settings</span></span>



<span data-ttu-id="0b9ba-108">SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 다음 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>

## <a name="general-settings"></a><span data-ttu-id="0b9ba-109">일반 설정</span><span class="sxs-lookup"><span data-stu-id="0b9ba-109">General settings</span></span>

<span data-ttu-id="0b9ba-p101">SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 FQDN(정규화된 도메인 이름). 값을 변경하려면 서버의 FQDN을 편집합니다. 새 값과 일치하는 DNS(Domain Name System) 호스트(A) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-p101">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>

<span data-ttu-id="0b9ba-p102">**구성된 모든 IP 주소 사용** 또는 **선택한 IP 주소로 서비스 사용 제한** 을 선택할 수 있습니다. **서비스를 정의된 IP 주소로 제한** 하도록 선택하면 사용자는 서버에서 공중 전화망(PSTN) 게이트웨이를 제외한 모든 통신에 사용할 기본 IP 주소를 정의합니다. PSTN에 사용할 별도의 IP 주소를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-p102">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway. You define a separate IP address for PSTN usage.</span></span>

<span data-ttu-id="0b9ba-116">**연결** 에서는 다음을 편집하거나 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-116">In **Associations**, you can edit or specify the following:</span></span>

- <span data-ttu-id="0b9ba-117">보관 서버를 연결하면 보관 서버를 Survivable Branch Appliance 또는 Survivable Branch Server와 연결하기로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0b9ba-118">드롭다운 목록에서 이미 정의된 보관 서버에서 서버를 선택하거나 새로 고치를 클릭하여  새 보관 서버를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0b9ba-119">새로 정의된 토폴로지를 게시하려면 지정하는 서버가 존재하고 도메인에 가입되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span>

- <span data-ttu-id="0b9ba-120">모니터링 서버 연결에서는 모니터링 서버를 Survivable Branch Appliance 또는 Survivable Branch Server와 연결하기로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0b9ba-121">드롭다운 목록에서 이미 정의된 모니터링 서버에서 서버를 선택하거나 새로 추가를  클릭하여 새 모니터링 서버를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>

- <span data-ttu-id="0b9ba-122">에지 풀을 연결하면 에지 서버 또는 풀을 Survivable Branch Appliance 또는 Survivable Branch Server와 연결하기로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0b9ba-123">드롭다운 목록에 있는 이미 정의된 에지 서버 또는 풀에서 서버를 선택하거나 **새로 만들기** 를 클릭하여 새 에지 서버 또는 풀을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>

## <a name="resiliency"></a><span data-ttu-id="0b9ba-124">탄력성</span><span class="sxs-lookup"><span data-stu-id="0b9ba-124">Resiliency</span></span>

<span data-ttu-id="0b9ba-p106">탄성은 등록자 풀에 대해 고가용성을 제공합니다. 백업 등록자를 제공하는 경우 기본 등록자에 오류가 발생하면 백업 등록자가 실패한 등록자 대신 작업을 수행하므로 사용자가 로그온 및 통신할 수 있습니다. 기본 등록자와 함께 오류가 발생한 시스템에 따라서는 사용자의 기능이 축소될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-p106">Resiliency provides high availability for the Registrar pool. By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate. There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>

<span data-ttu-id="0b9ba-128">드롭다운 목록에서 Survivable Branch Appliance 또는 Survivable Branch Server의 백업 등록자 역할을 할 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0b9ba-129">장애 조치 및 대체 시간 간격을 설정하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="0b9ba-130">장애 조치 및 대체 시간 간격(초)을 설정하면 실패한 등록자를 자동으로 감지하고 대체 시간 동안 기본 등록자가 백업되는지 자동으로 확인하므로 등록자 프로세스를 계속 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b9ba-131">실패 검색 및 대체 간격을 정의할 경우, 등록자가 잠깐 동안 응답하지 않을 때 장애 조치(failover) 및 대체가 수행되지 않도록 충분한 간격을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="0b9ba-132">풀이나 서버를 로드하는 시간에 따라 기본 등록자가 잠깐 동안 응답하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="0b9ba-133">사이트의 Survivable Branch Appliance 또는 Survivable Branch Server에서 풀 또는 Standard Edition 프런트 엔드 서버로의 기본값은 장애 조치(failover)의 경우 120초, 폴백의 경우 240초입니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span>

## <a name="mediation-server"></a><span data-ttu-id="0b9ba-134">중재 서버</span><span class="sxs-lookup"><span data-stu-id="0b9ba-134">Mediation Server</span></span>

<span data-ttu-id="0b9ba-135">**중재 서버** 에 대해 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-135">For **Mediation Server** you can specify the following:</span></span>

<span data-ttu-id="0b9ba-136">중재 서버가 배치되어 있기 때문에 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버에서 **배치된 중재 서버 사용됨** 확인란은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>

<span data-ttu-id="0b9ba-p109">풀 서버에서 TLS(전송 계층 보안)에 대한 수신 대기 포트를 정의합니다. 기본적으로 이 포트는 5067입니다. **TCP 포트 사용** 을 선택하면 배치된 중재 서버의 TCP 포트를 정의해야 합니다. 이는 선택적 설정이며 이 설정이 필요한지 여부는 게이트웨이 또는 PSTN 요구 사항을 참조하여 확인해야 합니다. 기본적으로 TCP 포트 값은 5068입니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-p109">You define the listening port on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="0b9ba-p110">배치된 중재 서버와 연결된 PSTN 게이트웨이를 정의합니다. 이미 게이트웨이를 정의한 경우 해당 게이트웨이를 중재 서버와 연결할 수 있습니다. 게이트웨이를 정의하지 않았지만 정의할 수 있는 경우 **새로 만들기** 를 선택할 수 있습니다. 또한 이 중재 서버에 대해 이미 구성되어 있는 게이트웨이를 제거할 수 있습니다. 게이트웨이를 선택한 다음 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-p110">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you have not defined any gateways, but you have them available to define, you can select **New**. You can also remove gateways that are already configured for this Mediation Server. Select the gateway, and then click **Remove**.</span></span>

<span data-ttu-id="0b9ba-p111">중재 서버와 연결된 게이트웨이가 둘 이상인 경우 연결된 첫 번째 게이트웨이가 기본 게이트웨이가 됩니다. 기본 게이트웨이로 다른 게이트웨이를 선택해야 하는 경우 기본값으로 설정할 게이트웨이를 선택하고 **기본값으로 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-p111">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b9ba-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b9ba-149">See also</span></span>

<span data-ttu-id="0b9ba-150">SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 설정을 정의 및 구성하는 방법에 대한 자세한 내용은 [분기 사이트 복구 솔루션](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-solutions)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0b9ba-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-solutions).</span></span>