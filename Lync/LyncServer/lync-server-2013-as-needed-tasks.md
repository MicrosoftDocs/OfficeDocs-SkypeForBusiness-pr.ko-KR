---
title: 'Lync Server 2013: 필요한 작업'
description: 'Lync Server 2013: 필요한 작업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91fe249d9615bb619426c58b22606c3ef182f9a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560004"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="350ca-103">Lync Server 2013의 필요에 따라 작업</span><span class="sxs-lookup"><span data-stu-id="350ca-103">As-needed tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="350ca-104">_**마지막으로 수정 된 항목:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="350ca-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="350ca-105">필요에 따라 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-105">Perform the following tasks as necessary.</span></span> <span data-ttu-id="350ca-106">또한 표준 절차에 따라 다음과 같은 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-106">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="350ca-107">**전체 보안 감사   ** 메시징 시스템의 업그레이드 또는 다시 디자인에 대 한 응답으로 또는 보안 위반 시도 (또는 성공한 경우)에 대 한 응답으로이 감사를 정기적으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-107">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="350ca-108">서버와 방화벽에 대한 포트 검색, 보안 수정 감사 및 타사 통과 테스트가 절차에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-108">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="350ca-109">**인증서를 만료**     로 바꾸기 Lync Server 인증서 확인은 일반 주간 작업 중 하나 이며, 절차의 일부로 서, 관리자는 모든 인증서의 만료 날짜를 기록해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-109">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="350ca-110">관리자는이 레코드를 사용 하 여 특정 인증서가 만료 되 고 필요에 따라 바뀔 때 알림을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-110">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="350ca-111">**성능 기준 업데이트**     업그레이드 또는 구성을 변경한 후에 성능 기준을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-111">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="350ca-112">조직은 초기 계획을 사용 하 여 성능 변경 사항을 측정 하 고 시스템 성능에 영향을 주는 문제를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-112">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="350ca-113">**엔터프라이즈 풀 관리**     엔터프라이즈 풀, Standard Edition 서버 및 조직의 환경에 있는 다른 모든 서버의 초기 구성은 개별 서버를 배포 하는 동안 수행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-113">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="350ca-114">Standard Edition 서버 및 엔터프라이즈 풀에 대 한 서버 및 풀의 사후 배포 관리에는 다음 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-114">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="350ca-115">프런트 엔드 서버 관리</span><span class="sxs-lookup"><span data-stu-id="350ca-115">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="350ca-116">웹 회의 관리</span><span class="sxs-lookup"><span data-stu-id="350ca-116">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="350ca-117">회의 관리</span><span class="sxs-lookup"><span data-stu-id="350ca-117">Managing Conferencing</span></span>
    
      - <span data-ttu-id="350ca-118">서비스 계정 자격 증명 변경</span><span class="sxs-lookup"><span data-stu-id="350ca-118">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="350ca-119">데이터베이스 관리</span><span class="sxs-lookup"><span data-stu-id="350ca-119">Managing Databases</span></span>
    
      - <span data-ttu-id="350ca-120">서비스 시작 및 중지 및 서버 역할 비활성화</span><span class="sxs-lookup"><span data-stu-id="350ca-120">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="350ca-121">서버 및 서버 역할 제거, 풀 제거 및 서버 및 풀 해제</span><span class="sxs-lookup"><span data-stu-id="350ca-121">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="350ca-122">**사용 관리**     Lync Server 2013을 구성 하 여 조직에 가장 적합 한 기능과 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-122">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="350ca-123">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-123">This includes the following:</span></span>
    
      - <span data-ttu-id="350ca-124">온-프레미스 웹 회의 모임에 대 한 지원 관리</span><span class="sxs-lookup"><span data-stu-id="350ca-124">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="350ca-125">메일 그룹을 사용 하 여 인스턴트 메시지 보내기 관리</span><span class="sxs-lookup"><span data-stu-id="350ca-125">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="350ca-126">연락처, 현재 상태 및 쿼리 관리</span><span class="sxs-lookup"><span data-stu-id="350ca-126">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="350ca-127">클라이언트 버전 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="350ca-127">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="350ca-128">지능형 IM 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="350ca-128">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="350ca-129">보관, 통화 정보 기록 및 모임 준수 구성</span><span class="sxs-lookup"><span data-stu-id="350ca-129">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="350ca-130">에 **지 서버 연결 관리**     외부 연결을 제공 하는 데 필요한 서버 및 설정의 지속적인 관리에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-130">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="350ca-131">내부 서버와에 지 서버 간의 연결 관리</span><span class="sxs-lookup"><span data-stu-id="350ca-131">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="350ca-132">에 지 서버에 대 한 내부 및 외부 인터페이스 및 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="350ca-132">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="350ca-133">페더레이션 파트너 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="350ca-133">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="350ca-134">**주소록 관리**     주소록 서버 관리에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-134">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="350ca-135">주소록 서버 전화 번호 정규화 구성</span><span class="sxs-lookup"><span data-stu-id="350ca-135">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="350ca-136">명령줄에서 주소록 서버 관리</span><span class="sxs-lookup"><span data-stu-id="350ca-136">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="350ca-137">**사용자 계정 관리**     사용자 계정 관리에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-137">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="350ca-138">Lync Server에 대해 사용자 계정 사용</span><span class="sxs-lookup"><span data-stu-id="350ca-138">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="350ca-139">마법사를 사용 하 여 Lync Server 사용자 구성</span><span class="sxs-lookup"><span data-stu-id="350ca-139">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="350ca-140">개별 Lync Server 사용자 계정 속성 구성</span><span class="sxs-lookup"><span data-stu-id="350ca-140">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="350ca-141">Lync Server 사용자 검색</span><span class="sxs-lookup"><span data-stu-id="350ca-141">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="350ca-142">Lync Server 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="350ca-142">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="350ca-143">Lync Server 사용자 삭제</span><span class="sxs-lookup"><span data-stu-id="350ca-143">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="350ca-144">**Lync Server 2013 로그 파일 분석**     일반적으로 문제 해결에 사용 되는 매우 유용한 도구 중 하나는 [Lync server 2013 로깅 도구 사용](https://technet.microsoft.com/library/gg558599.aspx)에 자세히 설명 된 lync Server 2013 로깅 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-144">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="350ca-145">로깅 도구는 로그 파일을 생성 하므로 (서버 기준으로) Microsoft Office Server 12 Resource Kit Tools가 컴퓨터에 설치 되어 있는 경우에는 Snooper 도구를 사용 하 여 이러한 로그 파일을 보고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-145">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="350ca-146">그렇지 않은 경우에는 Snooper 유틸리티를 사용 하는 것 보다 훨씬 덜 투명 하 고 복잡 한 텍스트 편집기를 사용 하 여 로그를 분석할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-146">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="350ca-147">프로토콜 메시지를 보고 분석 하려면</span><span class="sxs-lookup"><span data-stu-id="350ca-147">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="350ca-148">디버그 도구에서 디버깅 세션이 끝나면 로그 파일 분석을 클릭 하 여 Snooper 도구를 사용 하 여 로그 파일을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-148">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="350ca-149">다음 구성 요소에 대 한 프로토콜 로그를 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-149">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="350ca-150">Lync Server 동안의 sipstack (SIP)</span><span class="sxs-lookup"><span data-stu-id="350ca-150">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="350ca-151">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="350ca-151">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="350ca-152">Lync Server 회의 신호 트래픽 (C3P) (MCU Infra C3P 및 Focus C3P 포함)</span><span class="sxs-lookup"><span data-stu-id="350ca-152">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="350ca-153">PSOM (Lync Server Web 회의 트래픽)</span><span class="sxs-lookup"><span data-stu-id="350ca-153">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="350ca-154">Lync Server 통합 커뮤니케이션 클라이언트 플랫폼 클라이언트 (기타 CP)</span><span class="sxs-lookup"><span data-stu-id="350ca-154">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="350ca-155">보관 데이터베이스의 오류 보고서</span><span class="sxs-lookup"><span data-stu-id="350ca-155">Error reports from the archiving database</span></span>

<span data-ttu-id="350ca-156">필요에 따라 작업의 성능을 구성 하려면 As-Needed Operations 검사 목록을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="350ca-156">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="350ca-157">자세한 관리 절차는 Microsoft Lync Server 2013 관리 가이드를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="350ca-157">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="350ca-158">정책 또는 구성 설정 백업 (및 복원)</span><span class="sxs-lookup"><span data-stu-id="350ca-158">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="350ca-159">Lync Server 2013에서는 전체 시스템을 백업 및 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-159">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="350ca-160">Iif 백업 하 고 (someday restore) 단일 정책 또는 단일 구성 설정 컬렉션을 가져온 다음 해당 하는 정책을 검색 한 다음 해당 개체를 XML 파일 형식으로 저장 하는 Export-Clixml cmdlet에 파이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-160">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="350ca-161">이제 RedmondClientPolicy을 시험해 보고 여러 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-161">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="350ca-162">이전 정책을 복원 하는 대신 결정 하는 경우 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-162">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="350ca-163">이 방법은 대부분의 정책 및 설정에 적합 하지만 여러 하위 개체를 포함 하는 항목 (예를 들어, 별도의 음성 경로가 많이 포함 된 라우팅 구성 설정)에서는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="350ca-163">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

