---
title: 'Lync Server 2013: 백업 및 복원 전략 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcdfbb6b51a966149451e8f396b345b0383947e3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="f9225-102">Lync Server 2013에 대 한 백업 및 복원 전략 설정</span><span class="sxs-lookup"><span data-stu-id="f9225-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9225-103">_**마지막으로 수정 된 항목:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="f9225-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="f9225-104">Lync Server에 대 한 백업 및 복원 계획을 개발 하려면 먼저 조직의 목표를 충족 하는 전략을 개발 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="f9225-105">효과적인 백업 및 복원 전략을 개발 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="f9225-106">비즈니스 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="f9225-106">Establish business priorities.</span></span>

  - <span data-ttu-id="f9225-107">백업 및 복원 요구 사항을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="f9225-108">업무 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="f9225-108">Establishing Business Priorities</span></span>

<span data-ttu-id="f9225-p102">조직의 업무 우선 순위를 평가합니다. 일반적으로 백업 및 복원 전략에 영향을 주는 기본 업무 우선 순위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-p102">Evaluate the business priorities of your organization. Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="f9225-111">업무 연속성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9225-111">Business continuity requirements</span></span>

  - <span data-ttu-id="f9225-112">데이터 완전성</span><span class="sxs-lookup"><span data-stu-id="f9225-112">Data completeness</span></span>

  - <span data-ttu-id="f9225-113">데이터 중요도</span><span class="sxs-lookup"><span data-stu-id="f9225-113">Data criticality</span></span>

  - <span data-ttu-id="f9225-114">이동성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9225-114">Portability requirements</span></span>

  - <span data-ttu-id="f9225-115">비용 제약 조건</span><span class="sxs-lookup"><span data-stu-id="f9225-115">Cost constraints</span></span>

<span data-ttu-id="f9225-116">고객을 위해 개발 하는 Sla (서비스 수준 계약)를 확인 하기 위해 이러한 도움말과 같은 비즈니스 요구 사항을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="f9225-117">서비스 수준 계약은 백업 및 복구 전략을 이끕니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="f9225-118">백업 및 복원 요구 사항 식별</span><span class="sxs-lookup"><span data-stu-id="f9225-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="f9225-119">비즈니스 우선 순위 및 서비스 수준 계약은 Lync Server 백업 및 복원에 대 한 조직의 요구 사항을 결정 하는 데 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="f9225-120">다음에 대한 요구 사항을 식별하고 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="f9225-121">**백업 주기**백업 빈도에 대 한 자세한 내용은 [Lync Server 2013의 백업 및 복원에](lync-server-2013-best-practices-for-backup-and-restoration.md)대 한 모범 사례를 참조 하십시오.   </span><span class="sxs-lookup"><span data-stu-id="f9225-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="f9225-122">**백업 및 복원 도구**   에는 도구를 사용 하는 사람 및 해당 하는 컴퓨터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="f9225-123">이 항목에서 설명 하는 도구와 필요한 권한에 대 한 자세한 내용은 [Lync Server 2013의 백업 및 복원 요구 사항: 도구 및 사용 권한](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9225-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="f9225-124">**백업 위치**   백업이 로컬로 또는 원격으로 진행 되 고 있는지 여부를 확인 하 고 보안 및 접근성을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="f9225-125">백업에 사용할 미디어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="f9225-126">**하드웨어 및 소프트웨어 요구 사항**   에서는 백업 및 복원을 지 원하는 데 필요한 소프트웨어 및 네트워크 연결 및 특정 구성 요소의 복원과 관련 된 하드웨어 및 소프트웨어 요구 사항을 식별 하 고 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="f9225-127">하드웨어 및 소프트웨어 요구 사항을 개발할 때는 다음과 같은 여러 복원 시나리오를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="f9225-128">**복원 시나리오**   여기서는 다음과 같은 시나리오에 대 한 복원 프로세스를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="f9225-129">Lync Server 풀에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-129">A Lync Server pool fails.</span></span> <span data-ttu-id="f9225-130">이 시나리오에서는 풀에 각 서버를 다시 구축해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="f9225-131">Standard Edition 서버에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-131">A Standard Edition server fails.</span></span> <span data-ttu-id="f9225-132">이 시나리오에서는 새 컴퓨터 또는 깨끗한 컴퓨터에서 서버를 다시 구축하고 데이터베이스를 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="f9225-133">중앙 관리 저장소 손실</span><span class="sxs-lookup"><span data-stu-id="f9225-133">Loss of the Central Management store.</span></span> <span data-ttu-id="f9225-134">이 시나리오에서는 최소한 중앙 관리 저장소를 복원 하 고 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="f9225-135">중앙 관리 저장소가 여전히 정상적으로 작동 하는 경우 백 엔드 서버의 손실</span><span class="sxs-lookup"><span data-stu-id="f9225-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="f9225-136">이 시나리오에서는 새 컴퓨터 또는 깨끗한 컴퓨터에서 서버를 다시 구축하고 데이터베이스를 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="f9225-137">Lync Server 풀의 구성원 인 서버에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="f9225-138">이 시나리오에서는 새 컴퓨터나 깨끗 한 컴퓨터에서 서버를 다시 구축 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="f9225-139">파일 저장소가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-139">A File Store fails.</span></span> <span data-ttu-id="f9225-140">이 시나리오에서는 파일 서버 또는 파일 클러스터를 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="f9225-141">보관, 모니터링 또는 영구 채팅 데이터베이스에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="f9225-142">이 시나리오에서는 데이터베이스를 다시 만들고 데이터가 조직에 중요한 경우, 데이터를 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="f9225-143">Lync Server를 백업 및 실행 하는 데에는 보관, 모니터링 및 영구 채팅 데이터가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9225-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

