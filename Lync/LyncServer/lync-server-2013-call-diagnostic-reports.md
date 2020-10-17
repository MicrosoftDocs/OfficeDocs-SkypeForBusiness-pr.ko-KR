---
title: 'Lync Server 2013: 통화 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Reports
ms:assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615013(v=OCS.15)
ms:contentKeyID: 48184794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46073c5540b0b4cd48f6c5a13c17d4a4d3f12a46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526335"
---
# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="3b723-102">Lync Server 2013의 통화 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="3b723-102">Call Diagnostic Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b723-103">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="3b723-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="3b723-104">통화 진단 보고서는 피어 투 피어 및 회의 세션에 대해 요약 정보 및 진단 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3b723-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3b723-105">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="3b723-105">In This Section</span></span>

  - <span data-ttu-id="3b723-106">[Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)     의 통화 진단 요약 보고서 실패 한 피어 투 피어 세션 및 회의 세션에 대 한 전체 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b723-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="3b723-107">피어 투 피어 세션은 두 명의 참가자만 포함 하는 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="3b723-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="3b723-108">회의 세션에는 세 명 이상의 참가자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b723-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="3b723-109">[Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)     의 피어 투 피어 활동 진단 보고서 실패 한 피어 투 피어 세션에 대 한 전체 추세 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b723-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="3b723-110">피어 투 피어 세션에는 두 명의 참가자만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b723-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="3b723-111">[Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)     의 전화 회의 진단 보고서 각 회의 모달에 대 한 실패 한 회의 세션 및 추세 보기의 전체적인 추세 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b723-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="3b723-112">회의 세션에는 참가자가 세 명 이상 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b723-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="3b723-113">[Lync Server 2013](lync-server-2013-top-failures-report.md)     의 상위 실패 보고서 가장 자주 발생 하는 오류의 목록과 시간에 따른 추세를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b723-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="3b723-114">[Lync Server 2013](lync-server-2013-failure-distribution-report.md)     의 실패 분포 보고서 실패 한 세션에 대 한 분석을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b723-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="3b723-115">[Lync Server 2013](lync-server-2013-failure-list-report.md)     의 오류 목록 보고서 실패 한 회의에 포함 된 개별 참가자에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b723-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="3b723-116">[Lync Server 2013](lync-server-2013-diagnostic-report.md)     의 진단 보고서 실패 한 세션에 대 한 진단 및 문제 해결 정보 (SIP 응답 코드 및 진단 헤더와 Id 포함)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b723-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

