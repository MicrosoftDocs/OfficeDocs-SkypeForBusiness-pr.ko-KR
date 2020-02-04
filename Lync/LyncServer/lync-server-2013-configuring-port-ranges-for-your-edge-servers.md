---
title: 'Lync Server 2013: Edge 서버의 포트 범위 구성'
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
ms.openlocfilehash: b6eddf59f6fe4b2575e0e7d70adddb2e94c90e05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="3bb06-102">Lync Server 2013에서 Edge 서버의 포트 범위 구성</span><span class="sxs-lookup"><span data-stu-id="3bb06-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bb06-103">_**마지막으로 수정한 주제:** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="3bb06-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="3bb06-104">Edge 서버에서 오디오, 비디오, 응용 프로그램 공유에 대 한 별도의 포트 범위를 구성할 필요는 없습니다. 마찬가지로, Edge 서버에 사용 되는 포트 범위는 회의, 응용 프로그램 및 중재 서버와 함께 사용 되는 포트 범위와 일치 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb06-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="3bb06-105">이 예제를 진행 하기 전에이 옵션이 있는 동안에는 포트 범위를 변경 하지 않는 것이 좋으며,이는 5만 포트 범위 밖으로 이동 하는 일부 시나리오에 악영향을 미칠 수 있으므로이 방법을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb06-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="3bb06-106">예를 들어 다음 포트 범위를 사용 하도록 회의, 응용 프로그램 및 중재 서버를 구성 했다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb06-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3bb06-107">패킷 종류</span><span class="sxs-lookup"><span data-stu-id="3bb06-107">Packet Type</span></span></th>
<th><span data-ttu-id="3bb06-108">시작 포트</span><span class="sxs-lookup"><span data-stu-id="3bb06-108">Starting Port</span></span></th>
<th><span data-ttu-id="3bb06-109">예약 된 포트 수</span><span class="sxs-lookup"><span data-stu-id="3bb06-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3bb06-110">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="3bb06-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="3bb06-111">40803</span><span class="sxs-lookup"><span data-stu-id="3bb06-111">40803</span></span></p></td>
<td><p><span data-ttu-id="3bb06-112">8348</span><span class="sxs-lookup"><span data-stu-id="3bb06-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bb06-113">오디오</span><span class="sxs-lookup"><span data-stu-id="3bb06-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="3bb06-114">49152</span><span class="sxs-lookup"><span data-stu-id="3bb06-114">49152</span></span></p></td>
<td><p><span data-ttu-id="3bb06-115">8348</span><span class="sxs-lookup"><span data-stu-id="3bb06-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bb06-116">비디오만</span><span class="sxs-lookup"><span data-stu-id="3bb06-116">Video</span></span></p></td>
<td><p><span data-ttu-id="3bb06-117">57500</span><span class="sxs-lookup"><span data-stu-id="3bb06-117">57500</span></span></p></td>
<td><p><span data-ttu-id="3bb06-118">8034</span><span class="sxs-lookup"><span data-stu-id="3bb06-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bb06-119"><strong>합계가</strong></span><span class="sxs-lookup"><span data-stu-id="3bb06-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="3bb06-120">24730</span><span class="sxs-lookup"><span data-stu-id="3bb06-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3bb06-121">여기에서 알 수 있듯이 오디오, 비디오, 응용 프로그램 공유의 포트 범위는 포트 40803에서 시작 하 여 총 24732 포트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb06-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="3bb06-122">원하는 경우 Lync Server 관리 셸에서와 유사한 명령을 실행 하 여 해당 Edge 서버에서 이러한 전체 포트 값을 사용 하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb06-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="3bb06-123">또는 다음 명령을 사용 하 여 조직의 모든 Edge 서버를 동시에 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb06-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="3bb06-124">다음 Lync Server Management Shell 명령을 사용 하 여 Edge 서버의 현재 포트 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb06-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="3bb06-125">이러한 옵션을 제공 하는 동시에 포트 구성에 대 한 작업을 그대로 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb06-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

