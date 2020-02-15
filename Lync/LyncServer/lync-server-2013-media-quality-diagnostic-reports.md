---
title: 'Lync Server 2013: 미디어 품질 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 257346792c7f1e3d815942c7eecacd16cba9194e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="21877-102">Lync Server 2013의 미디어 품질 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="21877-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21877-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="21877-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="21877-104">미디어 품질 진단 보고서에서는 통화 품질에 대 한 정보 및 실패 한 통화에 대 한 진단 및 문제 해결 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21877-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="21877-105">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="21877-105">In This Section</span></span>

  - <span data-ttu-id="21877-106">[Media Quality Summary Report in the Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   에서는 공중 전화망 (PSTN)에 대 한 enterprise voice 피어 투 피어 통화, enterprise voice 전화 회의 통화 및 최소한의 부분에 의존 하는 통화를 포함 하 여 다양 한 끝점 유형에 대 한 전체 품질 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21877-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="21877-107">[Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   의 미디어 품질 비교 보고서는 여러 유형의 오디오 통화 (예: 무선 네트워크를 통한 통화와 유선 연결을 통한 통화 간의 통화 품질 값 비교)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21877-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="21877-108">[Lync server 2013](lync-server-2013-server-performance-report.md)   의 서버 성능 보고서에는 성능 저하, 패킷 손실, 지터 등 주요 품질 메트릭 측정값을 기준으로 가장 많은 문제가 발생 한 서버가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21877-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="21877-109">[Lync Server 2013](lync-server-2013-location-report.md)   의 위치 보고서에서는 네트워크 위치 목록과 각 위치에서 발생 하는 호출의 미디어 품질에 대 한 요약 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21877-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="21877-110">이 보고서의 목적을 위해 위치는 IP 서브넷을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="21877-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="21877-111">[Lync Server 2013](lync-server-2013-device-report.md)   의 장치 보고서는 Enterprise Voice 통화에 사용 되는 장치에 대 한 요약을 제공 하며 장치에의 한 통화의 평균 미디어 품질을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="21877-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="21877-112">[Lync Server 2013](lync-server-2013-call-list-report.md)   의 통화 목록 보고서에서는 조직 내에서 수행 하거나 받은 전화 통화에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21877-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="21877-113">[Lync Server 2013](lync-server-2013-call-detail-report.md)   의 통화 정보 보고서에서는 조직 내에서 보내거나 받는 전화 통화에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21877-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="21877-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   에서는 통화 량, 불량 통화 율, 패킷 손실 및 지터와 같은 경험 치를 통해 최대 5 대의 서버를 그래픽으로 비교할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21877-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="21877-115">[Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   의 미디어 품질 메트릭 분포 보고서에서는 지터 나 패킷 손실 같은 경험 치 메트릭의 분포 값을 보여 주는 그래프를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21877-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="21877-116">[Lync Server 2013](lync-server-2013-location-trend-report.md)   의 위치 추세 보고서는 네트워크 위치에 대 한 통화 품질 추세 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21877-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

