---
title: 'Lync Server 2013: Microsoft Lync 배포 방법 결정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aef6ac76b6c0e8a6fb3c0444ab219acf78119ecd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="1781a-102">Lync Server 2013 배포 방법 결정</span><span class="sxs-lookup"><span data-stu-id="1781a-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1781a-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="1781a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1781a-104">Lync에 대 한 계획을 수립할 때 첫 번째 주요 결정은 Lync Server 2013 온-프레미스로 또는 Lync Online에서 microsoft Office 365을 사용 하 여 Microsoft Lync를 배포 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="1781a-105">**Lync Server 2013 온-프레미스** :이 선택은 전체 Lync 기능 집합을 제공 하 고 배포를 구성, 사용자 지정 및 운영 하는 데 최고의 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="1781a-106">모든 서버는 조직에서 온사이트 및 유지 관리를 위해 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="1781a-107">온-프레미스 배포는 모든 범위의 Lync 서버 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="1781a-108">**클라우드의 Lync Online** Lync Online은 Lync Server의 비즈니스 수업 기능을 희생 하지 않고 클라우드 기반 메신저, 현재 상태, 모임에 대 한 비용 및 민첩성을 향상 시킬 수 있는 조직을 위해 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="1781a-109">Lync Online을 사용 하면 Microsoft는 필요한 서버 인프라를 배포 및 유지 관리 하 고 지속적인 유지 관리, 패치 및 업그레이드를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="1781a-110">온-프레미스 배포에서 사용할 수 있는 일부 기능은 Lync Online에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="1781a-111">가장 적합 한 배포 유형은 배포 하려는 작업 부하와 조직의 지역 및 비즈니스 상태에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="1781a-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="1781a-112">Lync Server</span></span>

<span data-ttu-id="1781a-113">온-프레미스 Lync Server 배포는 다음 시나리오에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="1781a-114">**전체 엔터프라이즈 음성 기능**   PBX를 바꾸거나 고급 통화 기능을 사용 하는 전체 엔터프라이즈 음성 솔루션을 배포 하려는 경우 온-프레미스 Lync Server 배포가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="1781a-115">온-프레미스는 PBX 시스템 및 trunks에 대 한 직접 연결과 응답 그룹 및 통화 공원 등의 고급 전화 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="1781a-116">Lync Online은 현재 이러한 기능을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="1781a-117">**미디어 품질 컨트롤**   CAC (통화 허용 제어) 및 QoS (서비스 품질) 기능 등의 모든 미디어 품질 보증 기능을 원하는 경우 온-프레미스 배포를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="1781a-118">**영구 채팅**   조직에 대해 영구 채팅을 배포 해야 하는 경우 온-프레미스 배포를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="1781a-119">\*\*\*\*   온-프레미스 배포만 타사 서버 응용 프로그램을 사용 하 여 Microsoft 통합 커뮤니케이션 관리 API (다중 작업)를 통해 신뢰할 수 있는 타사 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="1781a-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="1781a-120">**지역 지원이**   필요한 여러 국가/지역 회사의 경우 여러 국가나 지역에 대 한 데이터 센터가 있고 서버를 지역별로 배포 하 고 관리 해야 하는 경우 이러한 유형의 지역 관리 기능을 제공 하는 데 온-프레미스 배포를 사용 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="1781a-121">\*\*\*\*   온-프레미스 Lync Server 배포를 사용 하 여 정책, 보고서, 업그레이드에 대 한 완벽 한 제어는 전체 서버 및 클라이언트 정책, 모니터링 및 기타 보고서 집합 및 업그레이드 타이밍에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="1781a-122">Lync Online은 정책 설정 및 보고서의 하위 집합을 제공 하 고 업그레이드를 허용 하는 데 제한 된 창 (중요 한)을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="1781a-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="1781a-123">Lync Online</span></span>

<span data-ttu-id="1781a-124">앞의 목록에 있는 어떠한 요소도 중요 하지 않은 경우 보다 간단한 배포 및 관리 효율성을 위해 Lync Online을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="1781a-125">Lync Online은 강력한 메신저 대화, 현재 상태 및 회의 기능 집합을 제공 하며 조직의 사용자 간 IP를 통해 음성 및 영상 통화를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1781a-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

