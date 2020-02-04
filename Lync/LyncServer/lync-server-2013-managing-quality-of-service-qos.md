---
title: 'Lync Server 2013: 서비스 품질 (QoS) 관리'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce88471361c63fde3ebf8a3ea716a140567e722e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="5893d-102">Lync Server 2013에서 QoS (서비스 품질) 관리</span><span class="sxs-lookup"><span data-stu-id="5893d-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5893d-103">_**마지막으로 수정한 주제:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="5893d-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="5893d-104">QoS (서비스 품질)는 일부 조직에서 오디오 및 비디오 통신을 위한 최적의 최종 사용자 환경을 제공 하는 데 사용 되는 네트워킹 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-104">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications.</span></span> <span data-ttu-id="5893d-105">QoS는 대역폭이 제한 되는 네트워크에서 가장 일반적으로 사용 됩니다. 사용 가능한 대역폭에 대해 많은 수의 네트워크 패킷이 경쟁 됨에 따라 관리자가 패킷에 더 높은 우선 순위를 지정할 수 있는 방법을 제공 하는 서비스 품질 오디오 또는 비디오 데이터 운반.</span><span class="sxs-lookup"><span data-stu-id="5893d-105">QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data.</span></span> <span data-ttu-id="5893d-106">이러한 패킷에 보다 높은 우선 순위를 부여 함으로써 오디오 및 비디오 통신은 파일 전송, 웹 검색 또는 데이터베이스 백업과 관련 된 네트워크 세션 보다 더 빠르게 완료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-106">By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups.</span></span> <span data-ttu-id="5893d-107">이는 파일 전송 또는 데이터베이스 백업에 사용 되는 네트워크 패킷에 "최상 작업량" 우선 순위를 할당 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-107">That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5893d-108">일반적인 규칙에 따라 서비스 품질은 내부 네트워크의 통신 세션에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-108">As a general rule, Quality of Service applies only to communication sessions on your internal network.</span></span> <span data-ttu-id="5893d-109">QoS를 구현할 때 패킷 표시를 지원 하도록 서버와 라우터를 구성 합니다. 그러나 이러한 장치를 구성 하 여 특정 방식으로 패킷 표시를 지원 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-109">When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner.</span></span> <span data-ttu-id="5893d-110">인터넷 이나 다른 네트워크에서 서비스 품질이 지원 되는 것으로 간주할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-110">You cannot assume that Quality of Service will be supported on the Internet or on other networks.</span></span> <span data-ttu-id="5893d-111">다른 네트워크에서 서비스를 지 원하는 경우에도 QoS는 네트워크에서 서비스를 구성한 방법과 동일 하 게 구성 된다는 보장이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-111">Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="5893d-112">Microsoft Lync Server 2013에는 서비스 품질이 필요 하지 않습니다. 현재 QoS를 사용 하지 않는 경우에는 Lync Server 2013을 설치 하기 전에 서비스를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="5893d-113">네트워크에서 상당한 양의 패킷 손실이 발생 하는 경우이 문제를 해결 하는 데 권장 되는 방법은 대역폭을 더 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="5893d-114">더 이상 대역폭을 추가할 수 없는 경우 서비스 품질을 대신 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="5893d-115">Lync Server 2013는 서비스 품질에 대 한 완전 한 지원을 제공 하며,이는 이미 QoS를 사용 하 고 있는 조직이 Lync Server를 기존 네트워크 인프라에 쉽게 통합할 수 있다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="5893d-116">이를 위해서는 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="5893d-117">[Windows를 기반으로 하지 않는 장치에 대해 Lync Server 2013에서 QoS를 사용 하도록 설정](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="5893d-118">기본적으로 다른 운영 체제를 실행 하는 컴퓨터 및 기타 장치 (예: Iphone)에 QoS를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="5893d-119">Lync Server를 사용 하 여 디바이스의 서비스 품질을 사용 하거나 사용 하지 않도록 설정할 수 있지만 일반적으로 제품을 사용 하 여 이러한 장치에서 사용 되는 DSCP 코드를 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="5893d-120">[Lync Server 2013에서 회의, 응용 프로그램, 중재 서버에 대 한 포트 범위를 구성](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="5893d-121">오디오 및 비디오 등의 다른 패킷 유형에 대해 고유한 포트 집합을 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="5893d-122">Lync Server 2013에서는 속성 값을 True 또는 False로 설정 하 여 서비스 품질을 사용 하거나 사용 하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="5893d-123">대신 포트 범위를 구성한 다음 그룹 정책 만들기 및 적용을 통해 서비스 품질을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="5893d-124">나중에 QoS를 사용 하지 않기로 결정 한 경우 적절 한 그룹 정책 개체를 제거 하 여 서비스 품질을 "사용 안 함"으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="5893d-125">[Lync Server 2013에서 Edge 서버의 포트 범위를 구성 하는 중](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="5893d-126">필요 하지는 않지만 다른 서버와 동일한 포트 범위를 사용 하도록 Edge 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="5893d-127">[Lync Server 2013에서 Microsoft lync 클라이언트의 포트 범위를 구성 하는 중](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="5893d-128">이러한 포트 범위는 클라이언트 컴퓨터에만 적용 되며 일반적으로 서버에 구성 된 포트 범위와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="5893d-129">[Lync Server 2013에서 회의, 응용 프로그램, 중재 서버에 대 한 서비스 품질 정책을 구성](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="5893d-130">이러한 정책은 다른 패킷 유형에 적용 되는 DSCP 코드를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="5893d-131">[Lync Server 2013에서 a/V Edge 서버의 서비스 품질 정책을 구성](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="5893d-132">이 작업은 Edge 서버의 내부 측면 에서만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="5893d-133">서비스 품질은 인터넷이 아닌 내부 네트워크에서 사용 하도록 설계 되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="5893d-134">[Windows 7 또는 windows 8에서 실행 되는 클라이언트에 대 한 Lync Server 2013의 서비스 품질 정책을 구성](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="5893d-135">Microsoft Lync Server 2013는 Windows Vista 또는 Windows XP와 같은 다른 Windows 운영 체제에 대 한 QoS를 지원 하지 않는다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="5893d-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="5893d-136">[Lync Server 2013에서 Microsoft Lync Phone Edition 장치에 대 한 서비스 품질을 구성](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="5893d-137">기본적으로 Lync Phone Edition 장치에 QoS가 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="5893d-138">그러나 조직의 모든 오디오 패킷이 동일한 DSCP 코드를 사용 하도록 하려면 기본 DSCP 값을 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5893d-139">Microsoft Windows Server 2012 또는 Windows Server 2012 R2를 사용 하는 경우 해당 플랫폼에서 서비스 품질을 관리 하는 데 사용할 수 있는 새 Windows PowerShell cmdlet 집합에 관심이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5893d-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="5893d-140">자세한 내용은 Windows PowerShell의 네트워크 품질 Cmdlet을 참조 [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)하세요.</span><span class="sxs-lookup"><span data-stu-id="5893d-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

