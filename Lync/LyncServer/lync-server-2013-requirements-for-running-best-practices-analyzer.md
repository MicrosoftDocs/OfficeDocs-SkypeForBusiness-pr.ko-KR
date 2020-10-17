---
title: 'Lync Server 2013: 모범 사례 분석기를 실행 하기 위한 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for running Best Practices Analyzer
ms:assetid: 3c7dc44e-5f8a-40a7-9ebb-9ad707ac0007
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591345(v=OCS.15)
ms:contentKeyID: 48183880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f097da7dc35c63cb385abd7ea233ec85df386a6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511845"
---
# <a name="requirements-for-running-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="20329-102">Lync Server 2013에서 모범 사례 분석기를 실행 하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="20329-102">Requirements for running Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20329-103">_**마지막으로 수정 된 항목:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="20329-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="20329-104">Lync server 2013, 모범 사례 분석기를 사용 하 여 Lync Server 2013 환경을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20329-104">You can use Lync Server 2013, Best Practices Analyzer to scan your Lync Server 2013 environment.</span></span> <span data-ttu-id="20329-105">이전 환경을 검사 하는 데 사용할 수 없지만 이전 버전의 도구를 사용 하 여 해당 환경을 검색할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20329-105">You cannot use it to scan previous environments, but you can use the previous versions of the tool to scan those environments.</span></span> <span data-ttu-id="20329-106">모범 사례 분석기의 Lync Server 2010 및 Office Communications Server 2007 R2 버전을 다운로드 하 고 사용 하는 방법에 대 한 자세한 내용은 "Lync Server 2010, Best Practices Analyzer" [https://go.microsoft.com/fwlink/p/?linkId=210536](https://go.microsoft.com/fwlink/p/?linkid=256358) 및 "office communications server 2007 And Office Communications server 2007 r 2에 대 한 모범 사례 분석기"를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=256358](https://go.microsoft.com/fwlink/p/?linkid=210651) .</span><span class="sxs-lookup"><span data-stu-id="20329-106">For details about downloading and using the Lync Server 2010 and Office Communications Server 2007 R2 versions of Best Practices Analyzer, see "Lync Server 2010, Best Practices Analyzer" at [https://go.microsoft.com/fwlink/p/?linkId=210536](https://go.microsoft.com/fwlink/p/?linkid=256358) and "Best Practices Analyzer for Office Communications Server 2007 and Office Communications Server 2007 R2" at [https://go.microsoft.com/fwlink/p/?linkId=256358](https://go.microsoft.com/fwlink/p/?linkid=210651).</span></span>

<span data-ttu-id="20329-107">검색을 시작 하기 전에 Lync Server 2013 환경의 모든 구성 요소가 실행 중이 고 온라인 상태 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20329-107">Prior to starting your scan, you should ensure that all components in your Lync Server 2013 environment are running and online.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20329-p102">방화벽 설정과 권한을 포함하여 에지 서버 및 관련 경계 네트워크 설정의 구성에 따라 모범 사례 분석기가 에지 서버를 액세스하고 검색하지 못할 수 있습니다. 검색에 에지 서버를 포함하고 보고서에 에지 서버 액세스 문제가 보고되면 문제가 보고서에 다시 표시되지 않도록 검색 옵션에서 에지 서버를 제거하고 다시 검색을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20329-p102">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers. If you include Edge Servers in your scan and the reports indicate that there is an issue with accessing Edge Servers, you might want to remove Edge Servers from the scan options and run the scan again so that the issues do not show up in the report.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

