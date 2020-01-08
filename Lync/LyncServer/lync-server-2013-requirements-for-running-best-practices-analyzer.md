---
title: 'Lync Server 2013: 모범 사례 분석기를 실행 하기 위한 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements for running Best Practices Analyzer
ms:assetid: 3c7dc44e-5f8a-40a7-9ebb-9ad707ac0007
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591345(v=OCS.15)
ms:contentKeyID: 48183880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcdba078f60a4e2012840aedf618b2786181a47b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-running-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="621fc-102">Lync Server 2013에서 모범 사례 분석기를 실행 하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="621fc-102">Requirements for running Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="621fc-103">_**마지막으로 수정한 주제:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="621fc-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="621fc-104">Lync Server 2013, 모범 사례 분석기를 사용 하 여 Lync Server 2013 환경을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621fc-104">You can use Lync Server 2013, Best Practices Analyzer to scan your Lync Server 2013 environment.</span></span> <span data-ttu-id="621fc-105">이전 환경을 검사 하는 데 사용할 수는 없지만 이전 버전의 도구를 사용 하 여 해당 환경을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621fc-105">You cannot use it to scan previous environments, but you can use the previous versions of the tool to scan those environments.</span></span> <span data-ttu-id="621fc-106">Lync Server 2010 및 Office Communications Server 2007 R2 버전의 모범 사례 분석기를 다운로드 하 고 사용 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=210536](http://go.microsoft.com/fwlink/p/?linkid=256358) [http://go.microsoft.com/fwlink/p/?linkId=256358](http://go.microsoft.com/fwlink/p/?linkid=210651)"Lync Server 2010, 모범 사례 분석기" office Communications Server 2007 및 Office communications server 2007 R2의 모범 사례 분석기 "를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="621fc-106">For details about downloading and using the Lync Server 2010 and Office Communications Server 2007 R2 versions of Best Practices Analyzer, see "Lync Server 2010, Best Practices Analyzer" at [http://go.microsoft.com/fwlink/p/?linkId=210536](http://go.microsoft.com/fwlink/p/?linkid=256358) and "Best Practices Analyzer for Office Communications Server 2007 and Office Communications Server 2007 R2" at [http://go.microsoft.com/fwlink/p/?linkId=256358](http://go.microsoft.com/fwlink/p/?linkid=210651).</span></span>

<span data-ttu-id="621fc-107">검사를 시작 하기 전에 Lync Server 2013 환경의 모든 구성 요소가 실행 중이 고 온라인 상태 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="621fc-107">Prior to starting your scan, you should ensure that all components in your Lync Server 2013 environment are running and online.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="621fc-108">Edge 서버 구성 및 방화벽 설정 및 사용 권한을 비롯 한 관련 경계 네트워크 설정에 따라 모범 사례 분석기에서 Edge 서버에 액세스 하 고 검색 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621fc-108">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers.</span></span> <span data-ttu-id="621fc-109">스캔에 Edge 서버를 포함 하는 경우 보고서에 Edge 서버에 액세스 하는 데 문제가 있는 것으로 표시 되는 경우 검사 옵션에서 Edge 서버를 제거 하 고 검사를 다시 실행 하 여 문제가 보고서에 표시 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621fc-109">If you include Edge Servers in your scan and the reports indicate that there is an issue with accessing Edge Servers, you might want to remove Edge Servers from the scan options and run the scan again so that the issues do not show up in the report.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

