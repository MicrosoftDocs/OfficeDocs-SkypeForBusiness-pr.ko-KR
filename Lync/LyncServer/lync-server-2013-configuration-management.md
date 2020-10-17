---
title: 'Lync Server 2013: 구성 관리'
description: 'Lync Server 2013: 구성 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5999708811cc4a34cf846a1ddd481ba38e07c62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552154"
---
# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="1645f-103">Lync Server 2013의 구성 관리</span><span class="sxs-lookup"><span data-stu-id="1645f-103">Configuration management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1645f-104">_**마지막으로 수정 된 항목:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="1645f-104">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="1645f-105">구성 관리는 하드웨어 및 소프트웨어 자산과 시스템 구성 정보를 기록 하 고 추적 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-105">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="1645f-106">일반적으로 소프트웨어 라이선스를 추적 하 고, 클라이언트 컴퓨터 및 서버에 대 한 표준 하드웨어 및 소프트웨어 빌드를 유지 관리 하 고, 새 컴퓨터에 대 한 명명 표준을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-106">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="1645f-107">구성 관리에는 일반적으로 다음과 같은 범주가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-107">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="1645f-108">**하드웨어**     이 범주는 IT 조직이 소유 하 고 있는 장비, 장비 위치 및 장비를 사용 하는 사람을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-108">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="1645f-109">이 정보를 사용 하면 조직에서 업그레이드를 계획 하 고, 표준 하드웨어 빌드를 유지 관리할 수 있으며, 회계 목적을 위해 IT 자산의 가치를 보고, 도난 방지에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-109">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="1645f-110">**소프트웨어**     이 범주는 각 컴퓨터에 설치 된 소프트웨어, 버전 번호 및 라이선스가 저장 되는 위치를 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-110">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="1645f-111">이 정보는 업그레이드를 계획 하 고, 소프트웨어 사용이 허가 되었는지 확인 하 고, 승인 되지 않은 (및 허가 되지 않은) 소프트웨어의 현재 상태를 검색 하도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-111">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="1645f-112">**표준 빌드**     이 범주는 클라이언트 컴퓨터 및 서버에 대 한 현재 표준 빌드와이 표준을 충족 하는지 여부를 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-112">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="1645f-113">표준 빌드를 정의 하 고 적용 하는 것은 직원 들이 제한 된 버전의 소프트웨어만 유지 관리 해야 하기 때문에 인력을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-113">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="1645f-114">**누적 업데이트 및 핫픽스**     이 범주는 사용 하도록 테스트 및 승인 되는 서비스 팩과 최신 상태에 있는 컴퓨터를 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-114">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="1645f-115">이 정보는 컴퓨터가 손상 될 위험을 줄이고 승인 되지 않은 업데이트를 설치한 사용자를 검색 하는 데 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-115">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="1645f-116">**시스템 구성 정보**     이 범주는 시스템의 기능, 시스템 요소 간 상호 작용 및 원활 하 게 실행 되는 시스템에 의존 하는 프로세스를 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-116">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="1645f-117">예를 들어 타사 프록시 서버를 단일 서버에 구성 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-117">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="1645f-118">오류가 발생 한 경우에는이 서버에 대 한 프록시 서버의 종속성을 이해 하 고 필요에 따라 응급 복구 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-118">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="1645f-119">다른 프런트 엔드 서버와도 통신 하도록 프록시 서버를 구성할 수 있는 경우 종속성 및 긴급 복구 계획이 변경 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-119">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="1645f-120">구성 관리 구현</span><span class="sxs-lookup"><span data-stu-id="1645f-120">Implementing configuration management</span></span>

<span data-ttu-id="1645f-121">관리 해야 하는 항목을 확인 한 후에는 데이터 및 보고 데이터를 수집 하 여 구성 관리를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-121">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="1645f-122">소규모 조직에서 가장 간단한 방법은 데이터를 수동으로 수집 하 고 (클라이언트 컴퓨터의 수 및 모델링, 설치 된 소프트웨어를) Office Word 또는 Office Excel 문서에 저장 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-122">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="1645f-123">규모가 크고 복잡 하 고 지속적으로 변화 하는 시스템의 경우 자산 검색 및 자세한 정보 수집을 자동화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-123">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="1645f-124">조직과 관련 된 정보를 결정 하 고 데이터베이스에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-124">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="1645f-125">구성 관리 데이터베이스는 다음 영역의 지원 인력 및 관리를 위한 유용한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-125">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="1645f-126">**보안 감사**     이 데이터베이스를 사용 하면 핫픽스가 적용 되어 있거나 서비스 팩 또는 최신 바이러스 백신 업데이트의 설치를 누락 시킨 Lync Server 및 클라이언트 컴퓨터 시스템을 실행 하는 서버를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-126">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="1645f-127">**소프트웨어 설치**     클라이언트 소프트웨어 버전 식별 및 추적에서는 관리자에 게 버전 업데이트 및 새 설치를 계획 하 고 라이선스 설명서 및 규정 준수를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-127">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="1645f-128">**구성 정보**     기본값에서 변경 된 모든 설정의 최신 목록을 유지 관리 하는 경우 문제를 신속 하 고 효과적으로 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-128">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="1645f-129">**업그레이드 계획**     용량 검토에서 Lync 데이터베이스 서버에 추가 저장소 공간이 필요 하다 고 생각 되는 경우 각 서버에 내부 RAID 컨트롤러가 있는지 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-129">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="1645f-130">이러한 경우에는 동일한 모델 입니까?</span><span class="sxs-lookup"><span data-stu-id="1645f-130">If they do, then are they the same model?</span></span> <span data-ttu-id="1645f-131">같은 수의 디스크가 설치 되어 있습니까?</span><span class="sxs-lookup"><span data-stu-id="1645f-131">Do they have the same number of disks installed?</span></span> <span data-ttu-id="1645f-132">구성 관리 데이터베이스에는 설치할 수 있는 디스크 유형, 번호 및 업그레이드 경로가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-132">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="1645f-133">구성 관리에 사용 되는 도구</span><span class="sxs-lookup"><span data-stu-id="1645f-133">Tools used for configuration management</span></span>

<span data-ttu-id="1645f-134">자산을 검색, 감사 및 보고 하기 위한 다양 한 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-134">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="1645f-135">이 섹션에서는 이러한 도구 중 일부에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-135">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="1645f-136">**자동화 된 스크립트**     운영 체제, 서비스 팩 수준 및 특정 컴퓨터 집합에 소프트웨어가 있는지 여부와 같은 항목을 보고 하는 간단한 스크립트를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-136">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="1645f-137">이러한 스크립트를 조직의 정확한 요구 사항에 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-137">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="1645f-138">그러나 필요한 스크립트 수와 복잡도에 따라 스크립트를 만들고 유지 관리 하는 데 많은 비용이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-138">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="1645f-139">**자동화 된 도구**     비즈니스 규모 및 조직의 요구 사항에 따라 자동화 된 도구를 사용 하는 것을 고려해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-139">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="1645f-140">Microsoft 끝점 구성 관리자와 같은 도구는 표준 보고서 서식 파일 (예: 서비스 팩 수준)을 통합 하 고 사용자 지정 된 보고서를 만들 수 있습니다 (예: 응용 프로그램의 경우).</span><span class="sxs-lookup"><span data-stu-id="1645f-140">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="1645f-141">Microsoft Endpoint Configuration Manager를 사용 하 여 하드웨어 및 소프트웨어 구성을 보고할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-141">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="1645f-142">변경 관리와의 관계</span><span class="sxs-lookup"><span data-stu-id="1645f-142">Relationship with change management</span></span>

<span data-ttu-id="1645f-143">구성 관리는 변경 관리와 밀접 하 게 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-143">Configuration management is closely related to change management.</span></span> <span data-ttu-id="1645f-144">구성 관리는 변경에 대 한 요구 사항을 식별 하 고 변경이 발생 한 것을 식별 하 고 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-144">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="1645f-145">예를 들어 구성 관리 데이터베이스는 핫픽스를 필요로 하는 서버를 식별 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-145">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="1645f-146">그런 다음 변경 관리에서는 핫픽스 적용 프로세스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-146">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="1645f-147">반대로 새 누적 업데이트를 롤아웃할 경우 변경 관리 프로세스에서이 정보를 구성 관리 시스템에 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-147">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="1645f-148">소프트웨어를 배포할 위치와 시기를 검색 하 고 추적할 수 있도록 새 소프트웨어를 식별 하도록 구성 관리 도구를 구성 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1645f-148">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

