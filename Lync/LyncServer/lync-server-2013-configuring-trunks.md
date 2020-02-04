---
title: 'Lync Server 2013: 트렁크 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1021295b375e4f28294ffb1ca5738d651f9ced2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="4f541-102">Lync Server 2013에서 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="4f541-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f541-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4f541-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4f541-104">엔터프라이즈 음성 배포의 일부로, 중재 서버와 다음 피어 중 하나 이상을 구성할 수 있으므로 조직의 엔터프라이즈 음성 클라이언트 및 장치에 대 한 PSTN (공개 통신 네트워크) 연결을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f541-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="4f541-105">인터넷 전화 통신 서비스 공급자 (ITSP)에 대 한 SIP 트렁크 연결</span><span class="sxs-lookup"><span data-stu-id="4f541-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="4f541-106">PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="4f541-106">PSTN gateway</span></span>

  - <span data-ttu-id="4f541-107">PBX (사설 분기 교환)</span><span class="sxs-lookup"><span data-stu-id="4f541-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="4f541-108">자세한 내용은 계획 설명서의 [Lync Server 2013에서 PSTN 연결 계획](lync-server-2013-planning-for-pstn-connectivity.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f541-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4f541-109">트렁크 구성을 시작 하기 전에 토폴로지가 만들어졌는지, 중재 서버와 해당 피어가 서로 구성 되어 연결 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f541-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="4f541-110">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013의 토폴로지 작성기에서 게이트웨이 정의</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f541-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="4f541-111">트렁크 구성의 일부로 서, Lync Server 2013 미디어 건너뛰기 기능을 사용 하도록 설정 하 여 미디어에서 중재 서버를 우회할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f541-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="4f541-112">미디어 바이패스를 사용 하도록 설정 하거나 포함 하지 않고 Trunks를 구성할 수 있지만, 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f541-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="4f541-113">자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013에서 미디어 바이패스 계획</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f541-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4f541-114">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="4f541-114">In This Section</span></span>

  - [<span data-ttu-id="4f541-115">Lync Server 2013의 여러 트렁크 지원</span><span class="sxs-lookup"><span data-stu-id="4f541-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="4f541-116">Lync Server 2013의 트렁크 간 라우팅</span><span class="sxs-lookup"><span data-stu-id="4f541-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="4f541-117">Lync Server 2013에서 트렁크 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="4f541-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="4f541-118">Lync Server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="4f541-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="4f541-119">Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="4f541-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="4f541-120">Lync Server 2013에서 새 트렁크 구성 설정 모음 만들기</span><span class="sxs-lookup"><span data-stu-id="4f541-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="4f541-121">Lync Server 2013에서 기존 SIP 트렁크 구성 설정 모음 삭제</span><span class="sxs-lookup"><span data-stu-id="4f541-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="4f541-122">Lync Server 2013에서 SIP 트렁크 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="4f541-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="4f541-123">Lync Server 2013에서 SIP 트렁크 구성 설정 테스트</span><span class="sxs-lookup"><span data-stu-id="4f541-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="4f541-124">Lync Server 2013의 개별 SIP trunks에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="4f541-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f541-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f541-125">See Also</span></span>


[<span data-ttu-id="4f541-126">Lync Server 2013의 토폴로지 작성기에서 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="4f541-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="4f541-127">Lync Server 2013의 PSTN 연결 계획</span><span class="sxs-lookup"><span data-stu-id="4f541-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="4f541-128">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="4f541-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

