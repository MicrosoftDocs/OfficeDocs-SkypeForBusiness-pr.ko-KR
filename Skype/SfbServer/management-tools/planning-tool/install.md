---
title: Lync Server 2013에서 선택적 소프트웨어 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: 비즈니스용 Skype Server 2015 계획 도구를 사용 하 여 비즈니스용 Skype Server 2015 인프라 디자인 및 계획을 시작 하기 전에 먼저 계획 도구를 설치 해야 합니다. 비즈니스 서버 2015에 대 한 Skype를 설치 하려는 도메인 또는 인프라의 일부인 워크스테이션 또는 서버에 계획 도구를 배포할 필요는 없습니다. 계획 도구와 함께 제공 되는 Readme 파일은 도구 설치 및 사용에 대 한 중요 한 정보를 자세히 설명 합니다. 이해를 돕기 위해 Readme 파일의 일부 정보가 여기에 중복 됩니다.
ms.openlocfilehash: 192eae34bf6cf3fa53be82d8cb4450f960c90314
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188460"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="2fa50-106">Lync Server 2013에서 선택적 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="2fa50-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="2fa50-107">비즈니스용 Skype Server 2015 계획 도구를 사용 하 여 비즈니스용 Skype Server 2015 인프라 디자인 및 계획을 시작 하기 전에 먼저 계획 도구를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="2fa50-108">비즈니스 서버 2015에 대 한 Skype를 설치 하려는 도메인 또는 인프라의 일부인 워크스테이션 또는 서버에 계획 도구를 배포할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="2fa50-109">계획 도구와 함께 제공 되는 Readme 파일은 도구 설치 및 사용에 대 한 중요 한 정보를 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="2fa50-110">이해를 돕기 위해 Readme 파일의 일부 정보가 여기에 중복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fa50-111">계획 도구는 관리자 권한이 있는 사용자가 설치 하 고 도구를 설치할 컴퓨터에 대 한 사용 권한을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="2fa50-112">계획 도구의 설치 및 작동을 위해 지원 되는 운영 체제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="2fa50-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2fa50-113">Windows 10</span></span>

- <span data-ttu-id="2fa50-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="2fa50-114">Windows 8</span></span>

- <span data-ttu-id="2fa50-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="2fa50-115">Windows 8.1</span></span>

- <span data-ttu-id="2fa50-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="2fa50-116">Windows Server 2012</span></span>

- <span data-ttu-id="2fa50-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2fa50-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="2fa50-118">Windows 7, 32 비트 버전</span><span class="sxs-lookup"><span data-stu-id="2fa50-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="2fa50-119">Windows 7, 64 비트 edition (w)에서 Windows를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="2fa50-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="2fa50-120">Windows Server 2008 R2, WOW 사용</span><span class="sxs-lookup"><span data-stu-id="2fa50-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="2fa50-121">또한 계획 도구에는 Microsoft .NET Framework 4.5이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="2fa50-122">사전 설치 요구 사항이 충족 되 면 계획 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="2fa50-123">계획 도구를 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="2fa50-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="2fa50-124">로컬 컴퓨터에 관리자 그룹의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="2fa50-125">Windows 탐색기나 명령 창을 사용 하 여 계획 도구 설치 파일을 다운로드 한 디렉터리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="2fa50-126">SkypeForBusinessPlanningTool를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-126">Locate the SkypeForBusinessPlanningTool.msi.</span></span> <span data-ttu-id="2fa50-127">Windows 탐색기에서 파일을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-127">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="2fa50-128">명령 창에 파일 이름을 입력 한 다음 enter 키를 눌러 파일을 실행 \*\*\*\* 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-128">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="2fa50-129">**비즈니스용 Skype 서버 2015의 시작 페이지에서 계획 도구 설정 마법사**의 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="2fa50-130">라이선스 계약의 사용 약관에 동의 하기로 선택한 경우 **최종 사용자 사용권 계약**을 확인 하 고 **사용권 계약에** 동의 함을 선택한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="2fa50-131">계획 도구 파일을 설치할 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-131">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="2fa50-132">기본 위치는 C:\Program Files (x86) \Skype Skype Server 2015 \ 계획 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-132">The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool.</span></span> <span data-ttu-id="2fa50-133">설치 위치를 변경 하려면 **변경을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-133">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="2fa50-134">**대상 폴더 변경**에서 파일을 설치할 위치를 찾아보거나 입력 하 고 **확인**을 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-134">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="2fa50-135">이제 설치 관리자가 계획 도구를 설치할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="2fa50-136">설치 \*\*\*\* 를 클릭 하 여 설치 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="2fa50-137">설치가 시작 되 고 진행률이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="2fa50-138">설치가 성공적으로 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="2fa50-139">계획 도구를 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="2fa50-140">선택적 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="2fa50-140">Optional Software</span></span>
<span data-ttu-id="2fa50-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="2fa50-141"></span></span>

<span data-ttu-id="2fa50-142">비즈니스용 Skype 서버 2015 계획 도구는 Microsoft Excel 및 Microsoft Visio로 내보내기 하도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="2fa50-143">이러한 응용 프로그램은 계획 도구 작동에 필요 하지 않지만 디자인의 배포 및 문서에 중요 한 가치를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="2fa50-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="2fa50-144">Microsoft Excel</span></span>

<span data-ttu-id="2fa50-145">Microsoft Excel로 디자인을 내보내면 스프레드시트에 일곱 개의 탭이 표시 되는 보고서가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="2fa50-146">요약-사이트 구성에 대 한 정보 (사용자 수, 용량 설정, 서버 프로필 정보 등)를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="2fa50-147">하드웨어 프로필-토폴로지에 지정 된 서버에 대 한 권장 하드웨어 구성 (CPU, 메모리, 디스크, 네트워크 인터페이스 등)에 대 한 보고서를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="2fa50-148">서버 구성 요소에 대 한 수량 및 권장 사양이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="2fa50-149">또한 각 서버는 사이트별로 서버 요구 사항에 대 한 완전 한 표현을 제공 하도록 사이트에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="2fa50-150">포트 요구 사항-사용 하도록 설정 된 모든 포트의 보고서와 DNS LB (도메인 이름 시스템 부하 분산) 및 HLB (하드웨어 부하 분산 장치)에 대 한 연결을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="2fa50-151">이 보고서를 사용 하 여 방화벽과 DNS LB 및 HLB 구성을 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="2fa50-152">요약 보고서-Edge Server 네트워크를 설정 하는 데 필요한 설정에 대 한 일반적인 요약 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="2fa50-153">인증서 보고서-Edge 서버를 실행 하는 데 필요한 인증서에 필요한 주체 이름 및 주체 대체 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="2fa50-154">방화벽 보고서-원본 및 대상 포트와 외부 및 내부 인터페이스에 대 한 IP 주소를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="2fa50-155">DNS Report-사용자가 만든 각 DNS 항목에 필요한 FQDN (정규화 된 도메인 이름) 및 IP/VIP 주소를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="2fa50-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="2fa50-156">Microsoft Visio</span></span>

<span data-ttu-id="2fa50-157">Microsoft Visio로 디자인을 내보내면 구성 된 토폴로지와 인프라의 설명서에 사용할 수 있는 다이어그램이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-157">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure.</span></span> <span data-ttu-id="2fa50-158">문서에 대 한 요구 사항을 충족 하기 위해 가져온 다이어그램을 편집 하 고 다시 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-158">The imported diagram can be edited and rearranged to meet your documentation needs.</span></span> <span data-ttu-id="2fa50-159">일반적인 Visio 다이어그램에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-159">The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="2fa50-160">세 개 이상의 프런트 엔드 서버를 필요로 하는 설계가 충분히 큰 경우 프런트 엔드 풀, 프런트 엔드 서버, SQL Server를 실행 하는 컴퓨터, IP 주소, Fqdn에 대 한 추가 페이지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="2fa50-161">전역 토폴로지-구성 된 비즈니스용 Skype 서버 2015 사이트의 다이어그램입니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="2fa50-162">사이트 이름 탭-Edge Server, 방화벽, 공공 교환 통신 네트워크 (PSTN) 및 게이트웨이가 있는 사이트 구성 토폴로지가 표시 되며 내부 서버 배포</span><span class="sxs-lookup"><span data-stu-id="2fa50-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="2fa50-163">내부 배포는 프런트 엔드 풀, SQL Server 기반 서버, Active Directory 도메인 서비스, 디렉터, Exchange UM (통합 메시징) 서버, Exchange 사서함 서버, Office Web Apps 서버를 포함 하 여 구성 된 서버와 풀로 구성 됩니다. 중재 서버와 영구 채팅 서버.</span><span class="sxs-lookup"><span data-stu-id="2fa50-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="2fa50-164">Edge 네트워크 다이어그램-연결 된 IP 주소와 Fqdn을 사용 하 여 Edge 서버 구성을 자세히 설명 하는 다이어그램입니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="2fa50-165">DNS 부하 분산 및 하드웨어 부하 분산 장치도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="2fa50-166">또한 디렉터 및 프런트 엔드 서버 또는 프런트 엔드 풀은 연결 된 DNS LB 또는 HLB와 할당 된 IP 주소 (계획 도구는 IPv4 및 IPv6 주소 모두 지원) 및 FQDN으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa50-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fa50-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2fa50-167">See also</span></span>
<span data-ttu-id="2fa50-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="2fa50-168"></span></span>

[<span data-ttu-id="2fa50-169">계획 도구 설치</span><span class="sxs-lookup"><span data-stu-id="2fa50-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
