---
title: 'Lync Server 2013: 하이브리드 배포 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0902150170d51aa590afc8b3d02c887968a2031
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="37163-102">Lync Server 2013 하이브리드 배포 계획</span><span class="sxs-lookup"><span data-stu-id="37163-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37163-103">_**마지막으로 수정한 주제:** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="37163-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="37163-104">하이브리드 배포를 계획 하는 동안 사용자 및 네트워크 인프라에 대 한 다음과 같은 요구 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="37163-105">인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="37163-105">Infrastructure Requirements</span></span>

<span data-ttu-id="37163-106">하이브리드 배포를 구현 하 고 배포 하려면 환경에 다음이 구성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="37163-107">비즈니스용 Skype Online이 활성화 된 Microsoft Office 365 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="37163-107">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> <span data-ttu-id="37163-108">온-프레미스 배포의 경우 단일 테 넌 트만 하이브리드 구성에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="37163-109">지원 되는 토폴로지에서 배포 되는 비즈니스용 Skype 서버 또는 Lync Server의 단일 온 프레미스 배포 (인프라)입니다.</span><span class="sxs-lookup"><span data-stu-id="37163-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="37163-110">토폴로지 요구 사항을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37163-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="37163-111">하이브리드 용 Lync Server 2013 또는 Lync Server 2010 배포를 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013 하이브리드 배포 구성을](lync-server-2013-configuring-hybrid-deployments.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37163-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="37163-112">비즈니스용 Skype 서버 2015 관리 도구.</span><span class="sxs-lookup"><span data-stu-id="37163-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="37163-113">Lync Server 2013 또는 Lync Server 2010를 사용 하는 경우 Lync Server 2013 관리 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="37163-114">사용자가 온-프레미스에서 Office에 로그인 할 때 동일한 로그인 자격 증명을 사용할 수 있도록 Office 365의 Single Sign-on을 지원 하려면 Azure Active Directory (AAD) Connect의 암호 동기화 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="37163-115">Office 365에서 single sign-on에 AD FS (Active Directory Federation Services)를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="37163-116">자세한 내용은 [온-프레미스 id를 Azure Active Directory와 통합](http://go.microsoft.com/fwlink/p/?linkid=619754)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37163-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="37163-117">온-프레미스 및 온라인 Active Directory 개체를 동기화 된 상태로 유지 하는 단일 디렉터리 동기화 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="37163-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="37163-118">디렉터리 동기화에 대 한 자세한 내용은 [디렉터리 통합 도구](http://go.microsoft.com/fwlink/p/?linkid=530320)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37163-118">For details about Directory Synchronization, see [Directory Integration Tools](http://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="37163-119">Lync 클라이언트 지원</span><span class="sxs-lookup"><span data-stu-id="37163-119">Lync Client Support</span></span>

<span data-ttu-id="37163-120">Lync 클라이언트에서 지원 되는 기능 외에도 온-프레미스 및 온라인 환경에서 사용할 수 있는 기능에는 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="37163-121">조직의 사용자를 집에 배치할 위치를 결정 하기 전에 Lync Server의 다양 한 구성에 대 한 클라이언트 지원을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="37163-122">Lync 하이브리드 배포의 비즈니스용 Skype Online에서 지원 되는 클라이언트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="37163-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="37163-123">Lync 2010</span></span>

  - <span data-ttu-id="37163-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="37163-124">Lync 2013</span></span>

  - <span data-ttu-id="37163-125">Lync Windows 스토어 앱</span><span class="sxs-lookup"><span data-stu-id="37163-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="37163-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="37163-126">Lync Web App</span></span>

  - <span data-ttu-id="37163-127">Lync 모바일</span><span class="sxs-lookup"><span data-stu-id="37163-127">Lync Mobile</span></span>

  - <span data-ttu-id="37163-128">Mac용 Lync 2011</span><span class="sxs-lookup"><span data-stu-id="37163-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="37163-129">Lync 채팅방 시스템</span><span class="sxs-lookup"><span data-stu-id="37163-129">Lync Room System</span></span>

  - <span data-ttu-id="37163-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="37163-130">Lync Basic 2013</span></span>

<span data-ttu-id="37163-131">클라이언트 지원에 대 한 자세한 내용은 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37163-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="37163-132">Lync Online 용 클라이언트</span><span class="sxs-lookup"><span data-stu-id="37163-132">Clients for Lync Online</span></span>](http://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="37163-133">Lync Server 2013 의 클라이언트 비교 표</span><span class="sxs-lookup"><span data-stu-id="37163-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="37163-134">Lync Server 2013 의 모바일 클라이언트 비교 표</span><span class="sxs-lookup"><span data-stu-id="37163-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="37163-135">토폴로지 요구 사항</span><span class="sxs-lookup"><span data-stu-id="37163-135">Topology Requirements</span></span>

<span data-ttu-id="37163-136">비즈니스용 Skype Online으로 하이브리드 배포를 구성 하려면 다음 지원 토폴로지 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="37163-137">비즈니스용 skype server 2015를 실행 하는 모든 서버와의 비즈니스용 Skype 서버 2015 배포</span><span class="sxs-lookup"><span data-stu-id="37163-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="37163-138">Lync server 2013를 실행 하는 모든 서버에 2013 배포</span><span class="sxs-lookup"><span data-stu-id="37163-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="37163-139">Lync server 2010는 최신 누적 업데이트로 Lync Server 2010를 실행 하는 모든 서버에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37163-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="37163-140">페더레이션 edge 서버의 페더레이션 Edge 서버와 다음 홉 서버는 최신 누적 업데이트로 Lync Server 2010을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="37163-141">비즈니스용 Skype 서버 2015 또는 Lync Server 2013 관리 도구는 하나 이상의 서버 또는 관리 워크스테이션에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="37163-142">비즈니스용 Skype 서버 2015을 실행 하는 하나 이상의 사이트에서 다음 서버 역할을 사용 하는 혼합 Lync Server 2013 및 비즈니스용 Skype Server 2015 배포:</span><span class="sxs-lookup"><span data-stu-id="37163-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="37163-143">하나 이상의 엔터프라이즈 풀 또는 Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="37163-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="37163-144">SIP 페더레이션과 연결 된 디렉터 풀 (있는 경우)</span><span class="sxs-lookup"><span data-stu-id="37163-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="37163-145">SIP 페더레이션과 연결 된 Edge 풀</span><span class="sxs-lookup"><span data-stu-id="37163-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="37163-146">비즈니스용 Skype 서버 2015을 실행 하는 하나 이상의 사이트에서 다음 서버 역할이 포함 된 혼합 Lync Server 2010 및 비즈니스용 Skype Server 2015 배포:</span><span class="sxs-lookup"><span data-stu-id="37163-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="37163-147">하나 이상의 엔터프라이즈 풀 또는 Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="37163-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="37163-148">SIP 페더레이션과 연결 된 디렉터 풀 (있는 경우)</span><span class="sxs-lookup"><span data-stu-id="37163-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="37163-149">사이트의 SIP 페더레이션과 연결 된 Edge 풀</span><span class="sxs-lookup"><span data-stu-id="37163-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="37163-150">Lync server 2013을 실행 하는 하나 이상의 사이트에서 다음 서버 역할을 사용 하 여 lync server 2010 및 Lync Server 2013 배포가 혼합 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="37163-151">사이트에서 하나 이상의 엔터프라이즈 풀 또는 Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="37163-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="37163-152">사이트에 있는 경우 SIP 페더레이션과 연결 된 디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="37163-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="37163-153">사이트의 SIP 페더레이션과 연결 된 Edge 풀</span><span class="sxs-lookup"><span data-stu-id="37163-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="37163-154">온라인에서 온-프레미스와 UNRESOLVED_TOKEN_VAL (입력) 간에 사용자 이동을 비롯 한 모든 사용자 관리는 최신 버전의 관리 도구를 사용 하 여 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="37163-155">관리 도구는 기존 온-프레미스 배포 및 인터넷에 대 한 연결 액세스 권한이 있는 별도의 서버에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="37163-156">온-프레미스 배포의 사용자를 UNRESOLVED_TOKEN_VAL (skype16_online)으로 이동 하려면 온-프레미스 배포에 연결 된 관리 도구를 사용 하 여 온- <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">CsUser</A> cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="37163-157">지원 되는 토폴로지에 대 한 자세한 내용은 [Lync server 2013에서 지원 되](lync-server-2013-supported-topologies.md)는 토폴로지와 [엔터프라이즈 하이브리드 배포에 대 한 Lync Server 2013 참조 토폴로지](http://go.microsoft.com/fwlink/p/?linkid=398709)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37163-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="37163-158">Lync Online에 하이브리드 배포 및 PowerShell 연결에 대 한 문제 해결 정보는 lync [online: Lync PowerShell 및 하이브리드 문제 해결](http://go.microsoft.com/fwlink/p/?linkid=306718)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37163-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="37163-159">페더레이션 허용/차단 목록에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="37163-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="37163-160">허용 된 도메인 목록에는 파트너의 Edge FQDN (정규화 된 도메인 이름)이 구성 된 도메인이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37163-160">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="37163-161">이를 *허용 된 파트너 서버* 또는 *직접 페더레이션 파트너*라고 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-161">These are sometimes referred to as *allowed partner servers* or *direct federation partners*.</span></span> <span data-ttu-id="37163-162">온-프레미스 배포에서 각각 *파트너 검색* 및 *허용 된 파트너 도메인 목록*이라고 하는 열려 있는 페더레이션과 닫힌 페더레이션 간의 차이에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-162">You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="37163-163">하이브리드 배포를 성공적으로 구성 하려면 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="37163-164">도메인 일치는 온-프레미스 배포 및 Office 365 테 넌 트에 대해 동일 하 게 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-164">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant.</span></span> <span data-ttu-id="37163-165">온-프레미스 배포에서 파트너 검색을 사용 하도록 설정한 경우 온라인 테 넌 트에 대해 open federation를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-165">If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant.</span></span> <span data-ttu-id="37163-166">파트너 검색을 사용할 수 없는 경우에는 사용자의 온라인 테 넌 트에 대해 닫힌 페더레이션이 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-166">If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="37163-167">온-프레미스 배포의 차단 된 도메인 목록이 온라인 테 넌 트에 대 한 차단 된 도메인 목록과 정확히 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="37163-168">온-프레미스 배포의 허용 도메인 목록이 온라인 테 넌 트에 대해 허용 된 도메인 목록과 정확히 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="37163-169">Lync Online 제어판을 사용 하 여 구성 된 온라인 테 넌 트의 외부 통신에 대해 페더레이션을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="37163-170">DNS 설정</span><span class="sxs-lookup"><span data-stu-id="37163-170">DNS Settings</span></span>

<span data-ttu-id="37163-171">하이브리드 배포에 대 한 DNS 레코드를 만들 때 모든 Lync 외부 DNS 레코드는 온-프레미스 인프라를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="37163-172">필수 DNS 레코드에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS (Domain Name System) 요구 사항을](lync-server-2013-domain-name-system-dns-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37163-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="37163-173">또한 다음 표에 설명 된 DNS 확인이 온-프레미스 배포에서 작동 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37163-174">DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="37163-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="37163-175">확인할 사람</span><span class="sxs-lookup"><span data-stu-id="37163-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="37163-176">DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="37163-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37163-177">_Tcp에 대 한 DNS SRV 레코드 _sipfederationtls. &lt;EDGE&gt; 외부 IP에 액세스 하기 위해 지원 되는 모든 SIP 도메인이 sipdomain.com.</span><span class="sxs-lookup"><span data-stu-id="37163-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="37163-178">Edge 서버 (s)</span><span class="sxs-lookup"><span data-stu-id="37163-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="37163-179">하이브리드 구성에서 페더레이션된 통신을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-179">Enable federated communication in a hybrid configuration.</span></span> <span data-ttu-id="37163-180">Edge 서버는 온-프레미스와 온라인 간에 분할 된 SIP 도메인의 페더레이션 트래픽을 라우팅하는 위치를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-180">The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37163-181">DNS A Edge 웹 회의 서비스의 FQDN (예: 웹 회의에 대 한 webcon.contoso.com 해결) 외부 IP에 대 한 i d A A</span><span class="sxs-lookup"><span data-stu-id="37163-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="37163-182">내부 회사 네트워크에 연결 된 사용자 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="37163-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="37163-183">온라인 사용자가 온-프레미스 호스트 모임에서 콘텐츠를 프레젠테이션 하거나 볼 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-183">Enable online users to present or view content in on-premises hosted meetings.</span></span> <span data-ttu-id="37163-184">콘텐츠에는 PowerPoint 파일, 화이트 보드, 설문 조사 및 공유 메모가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37163-184">Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="37163-185">조직에서 DNS를 구성 하는 방법에 따라 해당 SIP 도메인에 대 한 내부 호스팅 DNS 영역에 이러한 레코드를 추가 하 여 해당 레코드에 대 한 내부 DNS 확인을 제공 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="37163-186">방화벽 고려 사항</span><span class="sxs-lookup"><span data-stu-id="37163-186">Firewall Considerations</span></span>

<span data-ttu-id="37163-187">네트워크의 컴퓨터는 표준 인터넷 DNS 조회를 수행할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-187">Computers on your network must be able to perform standard Internet DNS lookups.</span></span> <span data-ttu-id="37163-188">이러한 컴퓨터가 표준 인터넷 사이트에 도달할 수 있는 경우 네트워크는이 요구 사항을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-188">If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="37163-189">Microsoft Online Services 데이터 센터의 위치에 따라 와일드 카드 도메인 이름 (예: outlook.com의 \*모든 트래픽)을 기준으로 연결을 허용 하도록 네트워크 방화벽 장치를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="37163-190">조직의 방화벽이 와일드 카드 이름 구성을 지원 하지 않는 경우 허용 하려는 IP 주소 범위 및 지정 된 포트를 수동으로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="37163-191">[Office 365 url 및 IP 주소 범위](http://go.microsoft.com/fwlink/p/?linkid=252942)에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37163-191">Refer to the Help topic [Office 365 URLs and IP address ranges](http://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="37163-192">포트 및 프로토콜 요구 사항</span><span class="sxs-lookup"><span data-stu-id="37163-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="37163-193">내부 Lync Server 2013 통신의 포트 요구 사항 외에도 다음 포트를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37163-194">프로토콜/포트</span><span class="sxs-lookup"><span data-stu-id="37163-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="37163-195">프로그램도</span><span class="sxs-lookup"><span data-stu-id="37163-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37163-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="37163-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="37163-197">인바운드 열기</span><span class="sxs-lookup"><span data-stu-id="37163-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="37163-198">페더레이션 서버 역할 (Active Directory Federation Services)</span><span class="sxs-lookup"><span data-stu-id="37163-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="37163-199">자세한 내용은 <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">AD FS 역할 서비스 이해</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37163-199">For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="37163-200">Active Directory Federation Services (프록시 서버 역할)</span><span class="sxs-lookup"><span data-stu-id="37163-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="37163-201">Microsoft Online Services 포털</span><span class="sxs-lookup"><span data-stu-id="37163-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="37163-202">내 회사 포털</span><span class="sxs-lookup"><span data-stu-id="37163-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="37163-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="37163-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="37163-204">Lync 클라이언트 (온-프레미스 Lync Server에서 Lync Online으로 통신)</span><span class="sxs-lookup"><span data-stu-id="37163-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37163-205">TCP 80 및 443</span><span class="sxs-lookup"><span data-stu-id="37163-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="37163-206">인바운드 열기</span><span class="sxs-lookup"><span data-stu-id="37163-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="37163-207">Microsoft Online Services 디렉터리 동기화 도구</span><span class="sxs-lookup"><span data-stu-id="37163-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37163-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="37163-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="37163-209">Edge 서버의 인바운드/아웃 바운드 열기</span><span class="sxs-lookup"><span data-stu-id="37163-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37163-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="37163-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="37163-211">데이터 공유 세션에 대 한 열기 인바운드/아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="37163-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37163-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="37163-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="37163-213">오디오, 비디오, 응용 프로그램 공유 세션에 대 한 열기 인바운드/아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="37163-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37163-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="37163-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="37163-215">오디오 및 비디오 세션에 대 한 열기 인바운드/아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="37163-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37163-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="37163-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="37163-217">오디오 및 비디오 세션에 대 한 아웃 바운드 열기</span><span class="sxs-lookup"><span data-stu-id="37163-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="37163-218">사용자 계정 및 데이터</span><span class="sxs-lookup"><span data-stu-id="37163-218">User Accounts and Data</span></span>

<span data-ttu-id="37163-219">Lync Server 2013 하이브리드 배포의 경우 사용자 계정이 Active Directory 도메인 서비스에서 만들어지도록 Lync Online에서 홈으로 지정할 모든 사용자가 먼저 온-프레미스 배포에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="37163-220">이렇게 하면 사용자를 비즈니스용 Skype Online으로 이동 하 여 사용자의 연락처 목록을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="37163-221">Lync 온-프레미스 및 AD FS 및 Dirsync 온라인 배포 간에 사용자 계정을 동기화 하는 경우, 사용자가 온-프레미스 및 온라인 Lync 배포 사이에 조직의 모든 Lync 사용자에 대 한 광고 계정을 동기화 해야 합니다. Lync Online으로 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="37163-222">모든 사용자를 동기화 하지 않으면 조직에서 온-프레미스 및 온라인 사용자 간의 통신이 예상 대로 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="37163-223">사용자가 Office 365 용 온라인 포털을 사용 하 여 만들어진 경우 사용자 계정이 온-프레미스 Active Directory와 동기화 되지 않으며 사용자는 온-프레미스 Active Directory에 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="37163-224">Lync Online에서 사용자를 이미 만들었고 온-프레미스 Lync Server를 사용 하 여 하이브리드를 구성 하려는 경우 lync <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">server 2013에서 Lync Online에서 lync 온-프레미스로 사용자 이동을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37163-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="37163-225">또한 하이브리드 배포를 계획할 때 다음과 같은 사용자 관련 문제를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="37163-226">**사용자 연락처**   Lync Online 사용자에 대 한 연락처 제한은 250입니다.</span><span class="sxs-lookup"><span data-stu-id="37163-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="37163-227">계정이 Lync Online으로 이동 되 면 해당 번호를 초과 하는 모든 연락처가 사용자의 연락처 목록에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37163-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="37163-228">**인스턴트 메시지 및 현재 상태**   사용자 연락처 목록, 그룹, acl (액세스 제어 목록)이 사용자 계정으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="37163-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="37163-229">**회의 데이터, 모임 콘텐츠, 예약 된 모임**   이 콘텐츠는 사용자 계정으로 마이그레이션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="37163-230">사용자는 계정이 Lync Online으로 마이그레이션될 때 모임 일정을 재조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="37163-231">사용자 정책 및 기능</span><span class="sxs-lookup"><span data-stu-id="37163-231">User Policies and Features</span></span>

  - <span data-ttu-id="37163-232">Lync Server 2013 하이브리드 환경에서는 온-프레미스 또는 온라인 중 하나에서 인스턴트 메시지, 음성 및 모임에 대 한 사용을 가능 하 게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="37163-233">**Lync 클라이언트**     일부 사용자는 lync Online으로 이동할 때 새 클라이언트 버전이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="37163-234">Office Communications Server 2007 R2의 경우 Lync Online으로 마이그레이션하기 전에 사용자를 Lync Server 2013 풀로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="37163-235">클라이언트 지원에 대 한 자세한 내용은 Lync Online 및 [지원 되는 lync 클라이언트 및 네트워크 포트 구성](http://go.microsoft.com/fwlink/p/?linkid=281901) [에 대 한 클라이언트](http://go.microsoft.com/fwlink/p/?linkid=281902) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37163-235">For more information about client support, see [Clients for Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](http://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="37163-236">**온-프레미스 정책 및 구성 (비 사용자)**   온라인 및 온-프레미스 정책은 별도의 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="37163-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="37163-237">둘 다에 적용 되는 전역 정책은 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37163-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

