---
title: 'Lync Server 2013: Active Directory 도메인 서비스 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b200fb122f436e7afa5587e56a9e62edd0d3fa5e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a><span data-ttu-id="318ba-102">Lync Server 2013의 Active Directory 도메인 서비스 지원</span><span class="sxs-lookup"><span data-stu-id="318ba-102">Active Directory Domain Services support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="318ba-103">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="318ba-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="318ba-104">Lync Server 2013에서는 이전의 경우와 같이 중앙 관리 저장소를 사용 하 여이 정보에 대 한 Active Directory 도메인 서비스에 의존 하지 않고 서버 및 서비스에 대 한 구성 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="318ba-104">Lync Server 2013 uses the Central Management store to store configuration data for servers and services, instead of relying on Active Directory Domain Services for this information, as in the past.</span></span> <span data-ttu-id="318ba-105">Lync Server 2013에서는 여전히 AD DS에 다음이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="318ba-105">Lync Server 2013 still stores the following in AD DS:</span></span>

  - <span data-ttu-id="318ba-106">**스키마 확장**</span><span class="sxs-lookup"><span data-stu-id="318ba-106">**Schema extensions**</span></span>
    
      - <span data-ttu-id="318ba-107">사용자 개체 확장</span><span class="sxs-lookup"><span data-stu-id="318ba-107">User object extensions</span></span>
    
      - <span data-ttu-id="318ba-108">이전에 지원 되는 버전의 이전 버전과의 호환성을 유지 하기 위해 Lync Server 2010 및 Office Communications Server 2007 R2 클래스에 대 한 확장</span><span class="sxs-lookup"><span data-stu-id="318ba-108">Extensions for Lync Server 2010 and Office Communications Server 2007 R2 classes to maintain backward compatibility with previous supported versions</span></span>

  - <span data-ttu-id="318ba-109">**데이터** (Lync Server 2013 확장 스키마와 기존 클래스에 저장)</span><span class="sxs-lookup"><span data-stu-id="318ba-109">**Data** (stored in Lync Server 2013 extended schema and in existing classes)</span></span>
    
      - <span data-ttu-id="318ba-110">사용자 SIP URI 및 기타 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="318ba-110">User SIP URI and other user settings</span></span>
    
      - <span data-ttu-id="318ba-111">응용 프로그램에 대 한 연락처 개체 (예: 응답 그룹 응용 프로그램 및 회의 전화 교환 응용 프로그램)</span><span class="sxs-lookup"><span data-stu-id="318ba-111">Contact objects for applications (for example, the Response Group application and the Conferencing Attendant application)</span></span>
    
      - <span data-ttu-id="318ba-112">이전 버전과의 호환성을 위해 게시 된 데이터</span><span class="sxs-lookup"><span data-stu-id="318ba-112">Data published for backward compatibility</span></span>
    
      - <span data-ttu-id="318ba-113">중앙 관리 저장소에 대 한 SCP (서비스 제어 지점)</span><span class="sxs-lookup"><span data-stu-id="318ba-113">A service control point (SCP) for the Central Management store</span></span>
    
      - <span data-ttu-id="318ba-114">Kerberos 인증 계정(선택적 컴퓨터 개체)</span><span class="sxs-lookup"><span data-stu-id="318ba-114">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="318ba-115">이 섹션에서는 Lync Server 2013의 AD DS 지원 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="318ba-115">This section describes the AD DS support requirements for Lync Server 2013.</span></span> <span data-ttu-id="318ba-116">토폴로지 지원에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync Server 2013에서 지 원하는 Active Directory 토폴로지](lync-server-2013-supported-active-directory-topologies.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="318ba-116">For details about topology support, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span>

<div>

## <a name="supported-domain-controller-operating-systems"></a><span data-ttu-id="318ba-117">지원 되는 도메인 컨트롤러 운영 체제</span><span class="sxs-lookup"><span data-stu-id="318ba-117">Supported Domain Controller Operating Systems</span></span>

<span data-ttu-id="318ba-118">Lync Server 2013는 다음 운영 체제를 실행 하는 도메인 컨트롤러를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="318ba-118">Lync Server 2013 supports domain controllers running the following operating systems:</span></span>

  - <span data-ttu-id="318ba-119">Windows Server 2012 R2 운영 체제</span><span class="sxs-lookup"><span data-stu-id="318ba-119">Windows Server 2012 R2 operating system</span></span>

  - <span data-ttu-id="318ba-120">Windows Server 2012 운영 체제</span><span class="sxs-lookup"><span data-stu-id="318ba-120">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="318ba-121">Windows Server 2008 R2 운영 체제</span><span class="sxs-lookup"><span data-stu-id="318ba-121">Windows Server 2008 R2 operating system</span></span>

  - <span data-ttu-id="318ba-122">Windows Server 2008 운영 체제</span><span class="sxs-lookup"><span data-stu-id="318ba-122">Windows Server 2008 operating system</span></span>

  - <span data-ttu-id="318ba-123">Windows Server 2008 Enterprise 32 비트</span><span class="sxs-lookup"><span data-stu-id="318ba-123">Windows Server 2008 Enterprise 32-Bit</span></span>

  - <span data-ttu-id="318ba-124">Window Server 2003 R2 운영 체제 32 비트 또는 64 비트 버전</span><span class="sxs-lookup"><span data-stu-id="318ba-124">The 32-bit or 64-bit versions of the Window Server 2003 R2 operating system</span></span>

  - <span data-ttu-id="318ba-125">32 비트 또는 64 비트 버전의 Windows Server 2003 운영 체제</span><span class="sxs-lookup"><span data-stu-id="318ba-125">The 32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

</div>

<div>

## <a name="forest-and-domain-functional-level"></a><span data-ttu-id="318ba-126">포리스트 및 도메인 기능 수준</span><span class="sxs-lookup"><span data-stu-id="318ba-126">Forest and Domain Functional Level</span></span>

<span data-ttu-id="318ba-127">Lync Server 2013을 배포 하는 모든 도메인을 Windows Server 2012 R2, Windows Server 2012, Windows server 2008 R2, Windows Server 2008 또는 Windows Server 2003 이상으로 올리지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="318ba-127">You must raise all domains in which you deploy Lync Server 2013 to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

<span data-ttu-id="318ba-128">Lync Server 2013을 배포 하는 모든 포리스트는 Windows Server 2012 R2, Windows Server 2012, Windows server 2008 R2, Windows Server 2008 또는 적어도 Windows Server 2003의 포리스트 기능 수준으로 발생 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="318ba-128">All forests in which you deploy Lync Server 2013 must be raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a><span data-ttu-id="318ba-129">읽기 전용 도메인 컨트롤러 지원</span><span class="sxs-lookup"><span data-stu-id="318ba-129">Support for Read-Only Domain Controllers</span></span>

<span data-ttu-id="318ba-130">Lync Server 2013은 사용할 수 있는 쓰기 가능한 도메인 컨트롤러가 있는 경우 읽기 전용 도메인 컨트롤러 또는 읽기 전용 글로벌 카탈로그 서버를 포함 하는 Active Directory 도메인 서비스 배포를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="318ba-130">Lync Server 2013 supports Active Directory Domain Services deployments that include read-only domain controllers or read-only global catalog servers, as long as there are writable domain controllers available.</span></span>

</div>

<div>

## <a name="domain-names"></a><span data-ttu-id="318ba-131">도메인 이름</span><span class="sxs-lookup"><span data-stu-id="318ba-131">Domain Names</span></span>

<span data-ttu-id="318ba-132">Lync Server에서는 단일 레이블 도메인을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="318ba-132">Lync Server does not support single-labeled domains.</span></span> <span data-ttu-id="318ba-133">예를 들어 **contoso.local**이라는 루트 도메인으로 구성된 포리스트는 지원되지만 **local**이라는 루트 도메인은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="318ba-133">For example, a forest with a root domain named **contoso.local** is supported, but a root domain named **local** is not supported.</span></span> <span data-ttu-id="318ba-134">자세한 내용은 Microsoft 기술 자료 문서 300684, "단일 레이블 DNS 이름이 있는 도메인에 대 한 Windows 구성 정보"를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752).</span><span class="sxs-lookup"><span data-stu-id="318ba-134">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="318ba-135">Lync Server에서는 도메인 이름을 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="318ba-135">Lync Server does not support renaming domains.</span></span> <span data-ttu-id="318ba-136">Lync Server가 배포 되는 도메인의 이름을 바꾸려는 경우에는 먼저 Lync Server를 제거한 다음 도메인 이름을 바꾼 다음 Lync Server를 다시 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="318ba-136">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a><span data-ttu-id="318ba-137">잠긴 AD DS 환경</span><span class="sxs-lookup"><span data-stu-id="318ba-137">Locked Down AD DS Environments</span></span>

<span data-ttu-id="318ba-138">잠겨 있는 AD DS 환경에서는 사용자 및 컴퓨터 개체가 사용 권한 상속이 사용 되지 않는 특정 Ou (조직 구성 단위)에 포함 되는 경우가 많고, 관리 위임을 보호 하 고 Gpo (그룹 정책 개체)를 사용 하도록 설정 하는 데 도움이 됩니다. 보안 정책</span><span class="sxs-lookup"><span data-stu-id="318ba-138">In a locked-down AD DS environment, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span> <span data-ttu-id="318ba-139">Lync Server 2013는 잠겨 있는 Active Directory 환경에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="318ba-139">Lync Server 2013 can be deployed in a locked-down Active Directory environment.</span></span> <span data-ttu-id="318ba-140">잠긴 환경에서 Lync Server를 배포 하는 데 필요한 사항에 대 한 자세한 내용은 배포 설명서의 [Lync server 2013에서 잠긴 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="318ba-140">For details about what is required to deploy Lync Server in a locked-down environment, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

