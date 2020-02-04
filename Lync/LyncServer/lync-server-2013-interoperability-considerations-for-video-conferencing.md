---
title: 'Lync Server 2013: 비디오 회의를 위한 상호 운용성 고려 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8cdfa88cf6d6f58478ff3c6b44210545e24a765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="60b7c-102">Lync Server 2013에서 비디오 회의에 대 한 상호 운용성 고려 사항</span><span class="sxs-lookup"><span data-stu-id="60b7c-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60b7c-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="60b7c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="60b7c-104">이 섹션에서는 레거시 클라이언트와 Lync Server 2013 풀 또는 Lync Server 2013 클라이언트와 레거시 풀 간의 상호 운영성이 있는 경우 마이그레이션 작업 단계 중 사용자 환경에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="60b7c-105">Lync Server 2013 풀</span><span class="sxs-lookup"><span data-stu-id="60b7c-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="60b7c-106">사용자는 레거시 클라이언트가 Lync Server 2013 풀에서 사용 될 때 다음과 같은 동작을 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="60b7c-107">2-타사 통화의 경우 비디오 해상도가 레거시 풀의 경우와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="60b7c-108">단체 컨퍼런스의 경우 비디오 해상도 및 비디오 회의 기능은 레거시 풀의 경우와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-108">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool.</span></span> <span data-ttu-id="60b7c-109">갤러리 보기 및 고해상도를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-109">Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="60b7c-110">레거시 풀</span><span class="sxs-lookup"><span data-stu-id="60b7c-110">Legacy Pools</span></span>

<span data-ttu-id="60b7c-111">사용자는 Lync Server 2013 클라이언트를 레거시 풀에서 사용할 때 다음과 같은 동작이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="60b7c-112">2-타사 통화의 경우 Lync Server 2013 클라이언트는 다음과 같이 새로운 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="60b7c-113">두 참가자가 모두 Lync Server 2013 클라이언트를 사용 하는 경우에는 H. a 264를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="60b7c-114">Lync Server 2013 클라이언트는 레거시 서버가 대역내 프로비저닝으로이 정보를 보내지 않으므로 TotalReceiveVideoBitRateKb에 대 한 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="60b7c-115">단체 컨퍼런스의 경우 비디오 해상도 및 비디오 회의 기능은 레거시 풀의 레거시 클라이언트에서 경험 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60b7c-116">레거시 서버에서 Lync Server 2013 클라이언트를 호스트 하는 경우에는 풀의 모든 사용자가 저해상도 비디오만 받도록 비디오 회의 대역폭을 구성할 수 있지만 고해상도 비디오를 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="60b7c-117">예를 들어 미디어 구성에서 MaxVideoRateAllowed가 CIF-250K로 설정 되 고 VideoBitRateKb가 회의 정책에서 2000 kbps로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="60b7c-118">이 경우에는 풀의 사용자에 게 높은 해상도를 사용할 수 없기 때문에 발생 하는 순 효과입니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="60b7c-119">MaxVideoRateAllowed는 Lync Server 2013 클라이언트에 더 이상 사용 되지 않으므로 Lync Server 2013 클라이언트가 고해상도 비디오를 요청 하는 것을 막을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60b7c-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="60b7c-120">대신 풀의 모든 사용자에 대 한 회의 정책의 VideoBitRateKb을 MaxVideoRateAllowed와 같은 값으로 설정 하거나 (즉, CIF를 250 kbps로 설정 하거나 VGA를 600 kbps로 설정 하거나 HD를 1500 kbps로 설정 합니다.)</span><span class="sxs-lookup"><span data-stu-id="60b7c-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

