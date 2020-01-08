---
title: 'Lync Server 2013: 모범 사례 분석기 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a304f33071b8be13c61c3f930f196113ac3af6de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="4b72b-102">Lync Server 2013의 모범 사례 분석기 개요</span><span class="sxs-lookup"><span data-stu-id="4b72b-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b72b-103">_**마지막으로 수정한 주제:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="4b72b-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="4b72b-104">Lync Server 2013, 모범 사례 분석기를 사용 하 여 Lync Server 2013 배포의 문제를 식별 하 고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="4b72b-105">Lync Server 2013, 모범 사례 분석기는 Lync Server 2013 구성 요소에서 구성 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="4b72b-106">적절 한 네트워크 액세스를 사용 하 여 모범 사례 분석기는 Active Directory 도메인 서비스, Exchange UM (서버 통합 메시징) 및 Lync Server 2013를 실행 하는 서버를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="4b72b-107">모범 사례 분석기를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="4b72b-108">사전 검사를 수행 하 여 권장 되는 모범 사례에 따라 구성이 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="4b72b-109">Lync Server 2013의 필수 업데이트를 자동으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="4b72b-110">최적화 되지 않은 구성 설정, 지원 되지 않는 옵션, 누락 된 업데이트 또는 권장 하지 않는 방법 등의 문제 목록을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="4b72b-111">특정 문제를 해결 하 고 해결할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="4b72b-112">모범 사례 분석기는 다음과 같은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="4b72b-113">최소 설치 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4b72b-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="4b72b-114">문제 해결 팁을 포함 하 여 보고 된 문제에 대 한 온라인 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="4b72b-115">나중에 검토를 위해 저장할 수 있는 구성 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="4b72b-116">최신 시스템 분석 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="4b72b-117">모범 사례 분석기에서는 XML 구성 파일 집합을 사용 하 여 Lync Server 2013 환경에서 수집할 정보를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="4b72b-118">Active Directory 도메인 서비스를 확인 하는 것 외에도 Windows Server 운영 체제 레지스트리와 WMI (Windows Management Instrumentation)의 설정 등의 소스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="4b72b-119">모범 사례 분석기는 수집 하는 데이터와 Lync Server 2013 배포의 설정 및 구성에 대 한 미리 정의 된 규칙 집합을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="4b72b-120">수집 된 데이터와 미리 정의 된 규칙을 비교한 후 도구가 문제를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="4b72b-121">보고 되는 모든 문제에 대해 모범 사례 분석기는 스캔 한 Lync Server 2013 환경에서 발견 된 내용과 권장 구성에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="4b72b-122">모범 사례 분석기는 또한 특정 문제에 대 한 자세한 정보에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b72b-123">Lync Server 2013, 모범 사례 분석기는 Lync Server 2013 구성 요소 에서만 구성 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="4b72b-124">이전 버전의 도구를 사용 하 여 이전 환경을 스캔할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b72b-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="4b72b-125">자세한 내용은 <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Lync Server 2013에서 모범 사례 분석기를 실행 하기 위한 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b72b-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

