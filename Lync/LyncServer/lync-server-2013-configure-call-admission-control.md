---
title: 'Lync Server 2013: 통화 허용 제어 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e318ac448aa046f001022d40bc5680fd62d37378
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="e91dc-102">Lync Server 2013에서 통화 허용 제어 구성</span><span class="sxs-lookup"><span data-stu-id="e91dc-102">Configure call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e91dc-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e91dc-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e91dc-104">CAC (통화 허용 제어)는 사용 가능한 대역폭을 기반으로 실시간 세션을 설정할 수 있는지 여부를 결정 하는 솔루션으로, 혼잡 한 네트워크의 사용자에 게 오디오/비디오 품질이 저하 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e91dc-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="e91dc-105">CAC는 오디오 및 비디오에 대 한 실시간 트래픽만 제어 하며 데이터 트래픽에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e91dc-105">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="e91dc-106">기본 WAN 경로에 필요한 대역폭이 없으면 CAC가 인터넷 경로를 통해 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e91dc-106">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="e91dc-107">자세한 내용은 계획 설명서에서 [Lync Server 2013의 통화 허용 제어 계획](lync-server-2013-planning-for-call-admission-control.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e91dc-107">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="e91dc-108">이 섹션에서는 네트워크에서 CAC를 배포 하 고 관리 하는 방법을 보여 주는 예제 절차 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e91dc-108">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e91dc-109">CAC를 배포 하기 전에 계획 설명서에서 <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 수집</A> 을 참조 하 여 엔터프라이즈 네트워크 토폴로지에 대 한 필요한 모든 정보를 수집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e91dc-109">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="e91dc-110">또한 배포 설명서의 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성</A> 에 설명 된 대로 CAC 구성 요소를 설치 및 활성화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e91dc-110">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e91dc-111">이 섹션의 모든 CAC 배포 및 관리 예제는 Lync Server 관리 셸을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e91dc-111">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="e91dc-112">대신 Lync Server 제어판의 <STRONG>네트워크 구성</STRONG> 섹션을 사용 하 여 CAC를 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e91dc-112">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e91dc-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e91dc-113">In This Section</span></span>

  - [<span data-ttu-id="e91dc-114">Lync Server 2013에서 CAC에 대 한 네트워크 지역 구성</span><span class="sxs-lookup"><span data-stu-id="e91dc-114">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="e91dc-115">Lync Server 2013에서 대역폭 정책 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="e91dc-115">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="e91dc-116">Lync Server 2013에서 CAC에 대 한 네트워크 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="e91dc-116">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="e91dc-117">Lync Server 2013에서 CAC에 대 한 네트워크 사이트와 서브넷 연결</span><span class="sxs-lookup"><span data-stu-id="e91dc-117">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="e91dc-118">Lync Server 2013에서 네트워크 지역 링크 만들기</span><span class="sxs-lookup"><span data-stu-id="e91dc-118">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="e91dc-119">Lync Server 2013에서 네트워크 간 지역 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="e91dc-119">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="e91dc-120">Lync Server 2013에서 네트워크 사이트 간 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="e91dc-120">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="e91dc-121">Lync Server 2013에서 통화 허용 제어 사용</span><span class="sxs-lookup"><span data-stu-id="e91dc-121">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="e91dc-122">Lync Server 2013에 대 한 통화 허용 제어 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="e91dc-122">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

