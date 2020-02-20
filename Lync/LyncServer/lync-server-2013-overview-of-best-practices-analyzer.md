---
title: 'Lync Server 2013: 모범 사례 분석기 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a11cebfe1b8344bcad0385bbe17bb26277c498c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="07600-102">Lync Server 2013의 모범 사례 분석기 개요</span><span class="sxs-lookup"><span data-stu-id="07600-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07600-103">_**마지막으로 수정 된 항목:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="07600-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="07600-104">Lync server 2013, 모범 사례 분석기를 사용 하 여 Lync Server 2013 배포의 문제를 식별 하 고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07600-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="07600-105">Lync Server 2013, 모범 사례 분석기는 Lync Server 2013 구성 요소에서 구성 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="07600-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="07600-106">적절 한 네트워크 액세스를 사용 하 여 모범 사례 분석기를 통해 Active Directory 도메인 서비스를 실행 하는 서버, Exchange Server UM (통합 메시징) 및 Lync Server 2013을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07600-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="07600-107">모범 사례 분석기를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07600-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="07600-108">사전 검사를 수행 하 여 권장 되는 모범 사례에 따라 구성이 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="07600-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="07600-109">Lync Server 2013에 대 한 필수 업데이트를 자동으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="07600-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="07600-110">최적이 지 않은 구성 설정, 지원 되지 않는 옵션, 누락 된 업데이트 또는 권장 하지 않는 방법 등의 문제 목록을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="07600-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="07600-111">특정 문제를 해결 하 고 문제를 해결 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07600-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="07600-112">모범 사례 분석기에는 다음과 같은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07600-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="07600-113">최소 설치 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="07600-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="07600-114">문제 해결 팁을 포함 하 여 보고 된 문제에 대 한 온라인 설명서</span><span class="sxs-lookup"><span data-stu-id="07600-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="07600-115">나중에 검토할 수 있도록 저장 가능한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="07600-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="07600-116">최신 시스템 분석의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="07600-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="07600-117">모범 사례 분석기는 XML 구성 파일 집합을 사용 하 여 Lync Server 2013 환경에서 수집할 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="07600-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="07600-118">Active Directory 도메인 서비스를 확인 하는 것 외에 windows Server 운영 체제 레지스트리 및 WMI (Windows Management Instrumentation)의 설정과 같은 원본을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="07600-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="07600-119">모범 사례 분석기는 수집한 데이터를 Lync Server 2013 배포의 설정 및 구성에 대 한 미리 정의 된 규칙 집합과 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="07600-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="07600-120">수집 된 데이터를 미리 정의 된 규칙과 비교한 후 도구에서 문제를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="07600-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="07600-121">모범 사례 분석기에서 보고 하는 모든 문제에 대해 검색 된 Lync Server 2013 환경 및 권장 구성에서 찾은 사항에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07600-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="07600-122">모범 사례 분석기 또한 특정 문제에 대 한 보다 자세한 정보를 볼 수 있는 링크도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07600-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07600-123">Lync Server 2013, 모범 사례 분석기는 Lync Server 2013 구성 요소 에서만 구성 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="07600-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="07600-124">이전 버전의 도구를 사용 하 여 이전 환경을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07600-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="07600-125">자세한 내용은 <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Lync Server 2013에서 모범 사례 분석기를 실행 하기 위한 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07600-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

