---
title: Lync Server 2013:에 지 서버에 대 한 포트 범위 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1d1dc6c35cac0a375b9229a0a9e04664bfe868a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="d062a-102">Lync Server 2013에서에 지 서버에 대 한 포트 범위 구성</span><span class="sxs-lookup"><span data-stu-id="d062a-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d062a-103">_**마지막으로 수정 된 항목:** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="d062a-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="d062a-104">에 지 서버를 사용 하면 오디오, 비디오 및 응용 프로그램 공유에 대해 별도의 포트 범위를 구성할 필요가 없습니다. 마찬가지로에 지 서버에 사용 되는 포트 범위가 회의, 응용 프로그램 및 중재 서버에 사용 되는 포트 범위와 일치 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d062a-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="d062a-105">이 예를 계속 진행 하기 전에이 옵션을 사용 하는 것이 좋지만,이 경우에는 포트 범위를 변경 하지 않는 것이 좋으며,이는 5만 포트 범위의 외부로 이동할 경우 일부 시나리오에 부정적인 영향을 줄 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d062a-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="d062a-106">예를 들어 다음과 같은 포트 범위를 사용 하도록 회의, 응용 프로그램 및 중재 서버를 구성 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d062a-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d062a-107">패킷 종류</span><span class="sxs-lookup"><span data-stu-id="d062a-107">Packet Type</span></span></th>
<th><span data-ttu-id="d062a-108">시작 포트</span><span class="sxs-lookup"><span data-stu-id="d062a-108">Starting Port</span></span></th>
<th><span data-ttu-id="d062a-109">예약 된 포트 수</span><span class="sxs-lookup"><span data-stu-id="d062a-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d062a-110">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="d062a-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="d062a-111">40803</span><span class="sxs-lookup"><span data-stu-id="d062a-111">40803</span></span></p></td>
<td><p><span data-ttu-id="d062a-112">8348</span><span class="sxs-lookup"><span data-stu-id="d062a-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d062a-113">오디오만</span><span class="sxs-lookup"><span data-stu-id="d062a-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="d062a-114">49152</span><span class="sxs-lookup"><span data-stu-id="d062a-114">49152</span></span></p></td>
<td><p><span data-ttu-id="d062a-115">8348</span><span class="sxs-lookup"><span data-stu-id="d062a-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d062a-116">비디오</span><span class="sxs-lookup"><span data-stu-id="d062a-116">Video</span></span></p></td>
<td><p><span data-ttu-id="d062a-117">57500</span><span class="sxs-lookup"><span data-stu-id="d062a-117">57500</span></span></p></td>
<td><p><span data-ttu-id="d062a-118">8034</span><span class="sxs-lookup"><span data-stu-id="d062a-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d062a-119"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="d062a-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="d062a-120">24730</span><span class="sxs-lookup"><span data-stu-id="d062a-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d062a-121">여기에서 볼 수 있듯이 오디오, 비디오 및 응용 프로그램 공유를 위한 포트 범위는 포트 40803에서 시작 하 고 총 24732 포트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d062a-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="d062a-122">원하는 경우에는 Lync Server 관리 셸에서와 비슷한 명령을 실행 하 여 이러한 전체 포트 값을 사용 하도록 해당에 지 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d062a-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="d062a-123">또는 다음 명령을 사용 하 여 조직에 있는 모든에 지 서버를 동시에 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d062a-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="d062a-124">다음 Lync Server 관리 셸 명령을 사용 하 여에 지 서버에 대 한 현재 포트 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d062a-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="d062a-125">다시 말하지만, 이러한 옵션을 제공 하는 경우에는 포트 구성의 경우를 그대로 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d062a-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

