---
title: 'Lync Server 2013: 모니터링 데이터에 액세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45f6033c927a0d0c27b139d889c5fb0b0d9d4825
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a><span data-ttu-id="9050f-102">Lync Server 2013에서 모니터링 데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="9050f-102">Accessing monitoring data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9050f-103">_**마지막으로 수정한 주제:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="9050f-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="9050f-104">모니터링 데이터는 SQL Server 데이터베이스 쌍 (LcsCdr)에 저장 되며, 통화 세부 정보를 기록 하 고 QoEMetrics 데이터에 대 한 품질을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9050f-104">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data.</span></span> <span data-ttu-id="9050f-105">이러한 두 데이터베이스에 대 한 특별 한 것이 없습니다. 즉, SQL Server 데이터에 액세스 하 고 분석 하는 데 일반적으로 사용 하는 도구를 사용 하 여 해당 데이터베이스에 저장 된 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9050f-105">There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>

<span data-ttu-id="9050f-106">모니터링 데이터에 액세스 하 고 분석 하기 위해 고려해 야 하는 도구는 Lync Server 모니터링 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="9050f-106">One tool you should consider for accessing and analyzing monitoring data is the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="9050f-107">모니터링 보고서는 Microsoft SQL Server Reporting 서비스에 의해 게시 되는 표준 보고서 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="9050f-107">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="9050f-108">웹 브라우저를 사용 하 여 액세스할 수 있는 이러한 보고서에는 CDR 및 체감 품질 데이터베이스에 저장 된 CDR (통화 정보 기록) 및 체감 품질 (사용 품질) 레코드를 기준으로 하는 사용량, 호출 진단 정보 및 미디어 품질 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9050f-108">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="9050f-109">모니터링 보고서는 Lync Server 2013와 함께 제공 되며 lync server를 설치 하 고 모니터링을 구성한 후 Lync Server 배포 마법사에서 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9050f-109">Monitoring Reports ship with Lync Server 2013 and can be installed from the Lync Server Deployment Wizard after Lync Server has been installed and monitoring has been configured.</span></span>

<span data-ttu-id="9050f-110">참고로, 모니터링 보고서에는 SQL Server Reporting Service를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9050f-110">As noted, Monitoring Reports requires the use of SQL Server Reporting Service.</span></span> <span data-ttu-id="9050f-111">Sql server Reporting Service는 sql Server를 설치할 때와 동시에 설치 하거나 SQL Server 자체 설치 후 언제 든 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9050f-111">SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>

<span data-ttu-id="9050f-112">자세한 내용은 Lync Server 2013 배포 가이드에서 [Lync server 2013 모니터링 보고서 설치](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9050f-112">For more information, see the topic [Installing Lync Server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) in the Lync Server 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

