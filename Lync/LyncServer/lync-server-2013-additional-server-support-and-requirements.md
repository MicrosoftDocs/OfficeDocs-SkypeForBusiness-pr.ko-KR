---
title: 'Lync Server 2013: 추가 서버 지원 및 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f111b80bc88b632ff1020f45e899f220edeb7d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="8ade5-102">Lync Server 2013의 추가 서버 지원 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ade5-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ade5-103">_**마지막으로 수정한 주제:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="8ade5-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="8ade5-104">이 지원 가능성 문서의 다른 섹션에 설명 된 소프트웨어 지원 외에, Lync Server 2013에는 다음과 같은 지원 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="8ade5-105">Lync Server 2013는 특정 서버 역할에 대 한 DNS (Domain Name System) 및 하드웨어 부하 분산을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="8ade5-106">또한 적절 한 경우 중재 서버에 대 한 응용 프로그램 로드 균형 조정을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="8ade5-107">각 용도를 사용 하는 경우에 대 한 자세한 내용은 계획 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ade5-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="8ade5-108">Lync Server 2013는 DLX (메일 그룹 확장 프로토콜)를 사용 하 여 메일 그룹을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="8ade5-109">또한이 프로토콜은 메일 그룹의 구성원 자격을 가져오는 데 사용 되는 웹 서비스 메서드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="8ade5-110">Microsoft Exchange Server는 멤버가 정적으로 할당 되지 않은 동적 그룹을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="8ade5-111">대신 그룹을 확장할 때 평가 되는 쿼리를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="8ade5-112">DLX는 동적 메일 그룹을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="8ade5-113">이 DLX 제한은 Lync Server의 모든 버전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="8ade5-114">사용자 설정 마법사는 영어 이외의 문자를 SIP 호환 URI로 자동 변환을 지원 하지 않으므로 수동으로 SIP 주소를 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="8ade5-115">바이러스 백신 소프트웨어를 실행 하는 서버는 제안 된 바이러스 제외 및 기타 보안 관련 권장 사항에 대 한 [Lync Server 2013의 바이러스 백신 검색 제외](lync-server-2013-antivirus-scanning-exclusions.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ade5-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="8ade5-116">IPsec을 사용 하는 경우 오디오 및 비디오 트래픽에 사용 되는 포트 범위를 통해 IPsec을 사용 하지 않도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="8ade5-117">자세한 내용은 계획 설명서의 [Lync Server 2013의 IPsec 예외](lync-server-2013-ipsec-exceptions.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ade5-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="8ade5-118">조직에서 QoS (서비스 품질) 인프라를 사용 하는 경우 미디어 하위 시스템은이 기존 인프라 내에서 작동 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="8ade5-119">QoS를 구현 하는 방법에 대 한 자세한 내용은 운영 설명서의 [Lync Server 2013에서 qos (서비스 품질) 관리](lync-server-2013-managing-quality-of-service-qos.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ade5-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="8ade5-120">운영 체제 방화벽 사용이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="8ade5-121">Lync Server 2013는 Microsoft SQL Server 데이터베이스 소프트웨어를 제외 하 고 운영 체제 방화벽에 대 한 방화벽 예외를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="8ade5-122">SQL Server 방화벽 요구 사항에 대 한 자세한 내용은 SQL Server 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ade5-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="8ade5-123">외부 사용자 액세스에 대 한 지원을 구현 하는 데 사용 되는 외부 인터페이스는 내부 인터페이스와 동일한 네트워크가 *아닌* 별도의 서브넷에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="8ade5-124">Google 대화가 포함 된 인스턴트 메시징 페더레이션에 대해 Microsoft에서 Lync Server 2013의 XMPP 기능을 테스트 하 고 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-124">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="8ade5-125">다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션이 지원 되는지 여부와 배포 또는 문제 해결에 대 한 권장 사항을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-125">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="8ade5-126">Lync server 2013 누적 업데이트 릴리스: 7 월 2013 일, Lync Server 2013에서는 이제 2 단계 인증을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="8ade5-127">자세한 내용은 [Lync Server 2013의 2 단계 인증](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ade5-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="8ade5-128">대부분의 내부 서버에는 **개방형 인증** (OAuth)으로 정의 된 인증서 종류가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="8ade5-129">Lync Server 배포 마법사의 **요청, 인증서 설치 및 할당** 단계 중에 OAuth 인증서를 요청 하 고 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="8ade5-130">OAuth 인증서 키의 최소 크기는 1024 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="8ade5-131">2048 비트 길이 보다 작은 키 길이의 인증서를 요청 하는 경우 경고가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="8ade5-132">경고 대신 2048의 키 길이가 적용 되는 경우 발생 하는 문제를 방지 하려면 OAuth 인증서에 대해 항상 키 길이의 2048를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="8ade5-133">Windows Server 2008 R2 운영 체제가 FIPS 140-2 알고리즘을 사용 하도록 구성 된 경우 Lync Server 2013 및 Microsoft Exchange Server 2010 서비스 팩 1(SP1)이 FIPS (정보 처리 표준) 140-2 알고리즘에 대 한 지원을 통해 작동 합니다. 시스템 암호화.</span><span class="sxs-lookup"><span data-stu-id="8ade5-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="8ade5-134">FIPS 지원을 구현 하려면 Lync Server 2013를 실행 하는 각 서버를 지원 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="8ade5-135">FIPS 규격 알고리즘 및 FIPS 지원을 구현 하는 방법에 대 한 자세한 내용은 Microsoft 기술 자료 문서 811833, "시스템 암호화: 암호화, 해시, 서명에 FIPS 호환 알고리즘 사용 보안 설정 (Windows XP 및 이후 버전의 Windows [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833))에서</span><span class="sxs-lookup"><span data-stu-id="8ade5-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="8ade5-136">Exchange 2010의 FIPS 140-2 지원 및 제한 사항에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)"EXCHANGE 2010 SP1 및 Fips 호환 알고리즘에 대 한 지원"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ade5-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="8ade5-137">Lync Server 2013을 사용 하려면 배포 전이나 후에 특정 구성 요소에 다른 소프트웨어를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="8ade5-138">여기에는 운영 체제, 다운로드 가능한 소프트웨어 및 Lync Server 2013 설치 중에 자동으로 설치 되는 소프트웨어와 함께 제공 되는 소프트웨어가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="8ade5-139">다음은 필요할 수 있는 추가 소프트웨어 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="8ade5-140">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="8ade5-140">Windows Update</span></span>

  - <span data-ttu-id="8ade5-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="8ade5-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="8ade5-142">Microsoft .NET 4.5 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="8ade5-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="8ade5-143">Microsoft Visual c + + 2012 재배포 가능 패키지</span><span class="sxs-lookup"><span data-stu-id="8ade5-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ade5-144">Lync Server 2013을 설치 하면 Microsoft Visual c + + 2012 재배포 가능이 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="8ade5-145">다른 버전을 설치 하 여 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="8ade5-146">URL 재작성 모듈 버전 2.0 재배포 가능 패키지</span><span class="sxs-lookup"><span data-stu-id="8ade5-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="8ade5-147">Windows Media 형식 런타임</span><span class="sxs-lookup"><span data-stu-id="8ade5-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="8ade5-148">Windows PowerShell 버전 3.0</span><span class="sxs-lookup"><span data-stu-id="8ade5-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="8ade5-149">Microsoft Silverlight 4 브라우저 플러그 인 (Silverlight 4.0.50524.0 또는 Lync Server 제어판의 최신 버전)</span><span class="sxs-lookup"><span data-stu-id="8ade5-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="8ade5-150">Active Directory 도메인 서비스 도구</span><span class="sxs-lookup"><span data-stu-id="8ade5-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="8ade5-151">이러한 소프트웨어 요구 사항 중 일부는 특정 서버 역할 또는 구성 요소에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ade5-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="8ade5-152">이러한 소프트웨어 요구 사항에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013 추가 소프트웨어 요구 사항을](lync-server-2013-additional-software-requirements.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ade5-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

