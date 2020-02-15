---
title: 'Lync Server 2013: 비디오 회의에 대 한 상호 운용성 고려 사항'
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
ms.openlocfilehash: 885768cc461b7b59c37cf83b0b422bfca6c950a2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="d572c-102">Lync Server 2013에서 비디오 회의에 대 한 상호 운용성 고려 사항</span><span class="sxs-lookup"><span data-stu-id="d572c-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d572c-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d572c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d572c-104">이 섹션에서는 레거시 클라이언트와 Lync Server 2013 풀 또는 Lync Server 2013 클라이언트와 레거시 풀 간의 상호 운용성이 있을 때 마이그레이션 동시 사용 단계 중 사용자 환경에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="d572c-105">Lync Server 2013 풀</span><span class="sxs-lookup"><span data-stu-id="d572c-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="d572c-106">Lync Server 2013 풀에서 레거시 클라이언트를 사용 하는 경우 사용자에 게 다음과 같은 동작이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="d572c-107">두 사용자 간의 통화에서는 비디오 해상도가 레거시 풀과 동일하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="d572c-p101">단체 전화 회의에서는 비디오 해상도 및 비디오 회의 기능이 레거시 풀과 동일하게 설정됩니다. 갤러리 보기 및 고해상도는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-p101">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool. Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="d572c-110">레거시 풀</span><span class="sxs-lookup"><span data-stu-id="d572c-110">Legacy Pools</span></span>

<span data-ttu-id="d572c-111">레거시 풀에서 Lync Server 2013 클라이언트를 사용 하면 사용자에 게 다음과 같은 동작이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="d572c-112">두 사용자 간의 통화에서 Lync Server 2013 클라이언트는 다음과 같은 새 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="d572c-113">두 참가자가 모두 Lync Server 2013 클라이언트를 사용 하는 경우에는 .h를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="d572c-114">레거시 서버가 대역내 프로 비전을 사용 하 여이 정보를 보내지 않으므로 Lync Server 2013 클라이언트는 TotalReceiveVideoBitRateKb의 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="d572c-115">단체 전화 회의에서는 비디오 해상도 및 비디오 회의 기능이 레거시 풀의 레거시 클라이언트에 사용되는 것과 동일하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d572c-116">레거시 서버가 Lync Server 2013 클라이언트를 호스트 하는 경우에는 해당 풀의 모든 사용자가 저해상도 비디오만 수신 하 고 고해상도 동영상을 보낼 수 있도록 비디오 회의 대역폭을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="d572c-117">미디어 구성에서는 MaxVideoRateAllowed를 CIF-250K로 설정하고 회의 정책에서는 VideoBitRateKb를 2000kbps로 설정하는 경우를 한 가지 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="d572c-118">이러한 상황에서는 풀의 사용자에 대해 고해상도를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="d572c-119">Lync Server 2013 클라이언트에는 더 이상 MaxVideoRateAllowed가 사용 되지 않으므로 Lync Server 2013 클라이언트에서 고해상도 비디오를 요청 하는 것을 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d572c-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="d572c-120">대신 풀의 모든 사용자에 대해 회의 정책의 VideoBitRateKb를 MaxVideoRateAllowed와 같은 값으로 설정하십시오(CIF를 250kbps로 설정하거나, VGA를 600kbps로 설정하거나, HD를 1500kbps로 설정함).</span><span class="sxs-lookup"><span data-stu-id="d572c-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

