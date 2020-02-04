---
title: 'Lync Server 2013: E9-1 배포 범위 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96f5ac1fb747a3e64be6cc84c44b390de8ce821c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="10a49-102">Lync Server 2013에서 E9-1 배포의 범위 정의</span><span class="sxs-lookup"><span data-stu-id="10a49-102">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10a49-103">_**마지막으로 수정한 주제:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="10a49-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="10a49-104">Microsoft Lync Server 2013 for E9-1-1을 구성 하기 전에 E9-1-1 배포를 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-104">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="10a49-105">고려해 야 할 몇 가지 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-105">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="10a49-106">**E9-1-1과 관련 하 여 조직의 정책 및 법적 의무는 무엇 인가요?**</span><span class="sxs-lookup"><span data-stu-id="10a49-106">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="10a49-107">E9-1-Pbx에 대 한 법적 요구 사항 (여러 줄 전화 시스템) 또는 E9-1 parlance의 MLTS에는 state to state가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-107">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="10a49-108">해당 지역에서 Lync Server 배포에 적용 될 수 있는 의무를 이해 하려면 법률 팀과 상의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-108">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="10a49-109">**E9-1-1에 대해 enterprise 내에서 어떤 영역을 사용 해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="10a49-109">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="10a49-110">전체 enterprise 또는 선택한 위치에 대해 E9-1-1을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-110">You can enable E9-1-1 for the entire enterprise or for selected locations.</span></span> <span data-ttu-id="10a49-111">예를 들어 서로 다른 상태의 사무실에 대해 다양 한 E9-1-1 요구 사항이 있거나 미국 외의 사이트를 제외 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-111">For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="10a49-112">**E9-1-1을 지사 사이트에 어떻게 배포 하나요?**</span><span class="sxs-lookup"><span data-stu-id="10a49-112">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="10a49-113">음성 복구는 지점 사이트에서 E9-1을 구축할 때 이해 해야 하는 중요 한 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-113">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="10a49-114">중앙 집중화 된 전자 9-1-1 SIP trunks을 사용 중이 고 WAN 정지가 발생 하는 경우 로그인 하는 클라이언트가 위치 정보 서비스에서 위치를 가져오지 못하거나 비상 서비스 서비스 공급자에 연결 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-114">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="10a49-115">Lync Server는 복구 데이터 네트워크를 보유 하거나, 각 지점에서 SIP 트렁크를 배포 하거나, 중단 시 로컬 게이트웨이로 긴급 통화를 푸시하는 등 지점에서 음성 복원을 처리 하기 위한 몇 가지 전략을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-115">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="10a49-116">자세한 내용은 [Lync Server 2013의 지점 사이트 음성 복구 계획](lync-server-2013-planning-for-branch-site-voice-resiliency.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="10a49-116">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="10a49-117">**네트워크 외부에서 작업 하는 사용자에 대해 E9-1-1을 사용 하도록 설정 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="10a49-117">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="10a49-118">자동 위치 취득은 조직의 네트워크 내에 있는 클라이언트에만 사용할 수 있으므로 조직에서 오프 라인 상태에서 Lync 클라이언트의 E9-1 통화를 지원 하는지 여부를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-118">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises.</span></span> <span data-ttu-id="10a49-119">예를 들어 집 이나 고객 사이트에서 작업 하는 경우 사용자가 비상 전화를 걸 수 있도록 할 것인가?</span><span class="sxs-lookup"><span data-stu-id="10a49-119">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="10a49-120">클라이언트가 엔터프라이즈 네트워크 외부에 있는 경우 사용자에 게 위치를 묻는 메시지를 표시 하도록 클라이언트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-120">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="10a49-121">그러나 이러한 사용자 제공 위치는 MSAG (마스터 주소란)에 대해 prevalidated 수 없기 때문에 응급 서비스 서비스 공급자 발송자는 라우팅 전에 호출자와의 위치 구두로의 유효성을 확인 해야 합니다. PSAP (공개 안전 응답 시점)에 대 한 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-121">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10a49-122">VPN을 사용 하 여 조직의 네트워크에 연결 하는 사용자의 Lync 클라이언트는 내부 IP 주소 정보를 선택할 수 있지만, 이러한 주소는 사용자의 실제 위치를 식별 하는 데 사용할 수 없기 때문에, VPN 서브넷을 다음에서 제외 해야 합니다. 위치 정보 서비스.</span><span class="sxs-lookup"><span data-stu-id="10a49-122">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="10a49-123">**미국 외의 사이트에 대 한 긴급 통화 라우팅을 제공 하 고 싶으세요?**</span><span class="sxs-lookup"><span data-stu-id="10a49-123">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="10a49-124">비상 서비스 서비스 제공 업체 (예: 국제 위치)가 제공 하지 않는 회사 영역으로 긴급 라우팅 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-124">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations).</span></span> <span data-ttu-id="10a49-125">이렇게 하려면 새 사이트를 만든 다음 로컬 PSTN 게이트웨이를 통해 통화를 라우팅하는 PSTN 사용을 참조 하는 사이트에 음성 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a49-125">To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

