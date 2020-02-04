---
title: 'Lync Server 2013: 네트워크 지역, 사이트 및 서브넷 정보'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f85d392f7d5f987bf14197fd5027c6568965ae8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="8aa12-102">Lync Server 2013의 네트워크 지역, 사이트 및 서브넷 정보</span><span class="sxs-lookup"><span data-stu-id="8aa12-102">About network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8aa12-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="8aa12-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="8aa12-104">이 섹션에 설명 된 고급 엔터프라이즈 음성 기능은 네트워크 지역, 네트워크 사이트 및 서브넷에 대 한 특정 구성 요구 사항을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa12-104">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets.</span></span> <span data-ttu-id="8aa12-105">예를 들어 세 가지 고급 기능을 사용 하려면 토폴로지의 각 서브넷을 특정 *네트워크 사이트*와 연결 하 고 각 네트워크 사이트는 *네트워크 지역과*연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa12-105">For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8aa12-106">통화 허용 제어, E9-1-1 또는 미디어 바이패스에 대 한 네트워크 구성을 시작 하기 전에 계획 설명서의 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 항목에서 고급 Enterprise Voice 기능에 대 한 네트워크</A> 설정의 네트워크 설정에 대 한 추가 정보를 검토 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa12-106">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="8aa12-107">전화 허용 제어에 대 한 기본 네트워크 구성에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 정의</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8aa12-107">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="8aa12-108">통화 허용 제어 및 E9-1-1에는 네트워크 사이트에 대 한 추가 구성 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa12-108">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="8aa12-109">호출 허용 제어는 WAN 대역폭 제한에 의해 제한 된 각 사이트에 대해 *대역폭 정책 프로필* 을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa12-109">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="8aa12-110">통화 허용 제어를 배포 하려는 경우에는 네트워크 사이트를 구성 하기 전에 [Lync Server 2013에서 대역폭 정책 프로필을 만들어야](lync-server-2013-create-bandwidth-policy-profiles.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa12-110">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="8aa12-111">E9-1-1은 각 사이트에 대해 *위치 정책을* 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa12-111">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="8aa12-112">E9-1-1을 배포 하려는 경우 네트워크 사이트를 구성 하기 전에 [Lync Server 2013에서 위치 정책을 만들어야](lync-server-2013-create-location-policies.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa12-112">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="8aa12-113">네트워크 지역, 네트워크 사이트 및 서브넷 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8aa12-113">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="8aa12-114">다음 항목에서는 네트워크 지역 및 네트워크 사이트를 만들거나 수정 하 고 서브넷을 네트워크 사이트와 연결 하는 단계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa12-114">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites.</span></span> <span data-ttu-id="8aa12-115">이러한 항목은 특정 고급 엔터프라이즈 음성 기능에 국한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa12-115">These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="8aa12-116">Lync Server 2013에서 네트워크 영역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8aa12-116">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="8aa12-117">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="8aa12-117">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="8aa12-118">Lync Server 2013 에서 네트워크 사이트에 서브넷 연결</span><span class="sxs-lookup"><span data-stu-id="8aa12-118">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

