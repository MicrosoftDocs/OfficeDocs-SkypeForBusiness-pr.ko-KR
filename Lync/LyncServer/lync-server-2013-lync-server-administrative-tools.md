---
title: 'Lync Server 2013: Lync Server 관리 도구'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ac976f2c05268b5cf864511b19db1fd251edbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525115"
---
# <a name="lync-server-2013-administrative-tools"></a><span data-ttu-id="cc616-102">Lync Server 2013 관리 도구</span><span class="sxs-lookup"><span data-stu-id="cc616-102">Lync Server 2013 administrative tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc616-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="cc616-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="cc616-104">이 항목에서는 Lync Server 2013의 관리 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-104">This topic describes the administrative tools for Lync Server 2013.</span></span>

<span data-ttu-id="cc616-105">관리 도구는 각 Lync Server 서버에 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-105">The administrative tools are installed by default on each Lync Server server.</span></span> <span data-ttu-id="cc616-106">또한 전용 관리 콘솔과 같은 다른 컴퓨터에 관리 도구를 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="cc616-107">관리 도구를 설치 하는 절차는 [Install Lync Server 2013 관리 도구](lync-server-2013-install-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cc616-107">For procedures to install the administrative tools, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span> <span data-ttu-id="cc616-108">관리 작업을 수행 하는 도구를 여는 절차는 [Open Lync Server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cc616-108">For procedures to open the tools to perform management tasks, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

<span data-ttu-id="cc616-109">Lync Server 관리 도구를 설치 하거나 사용 하기 전에 인프라, 운영 체제, 소프트웨어 및 관리자 권한 요구 사항을 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-109">Ensure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server administrative tools.</span></span> <span data-ttu-id="cc616-110">인프라 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 관리 도구 인프라 요구 사항을](lync-server-2013-administrative-tools-infrastructure-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc616-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="cc616-111">Lync Server 관리 도구를 설치 하기 위한 운영 체제 및 소프트웨어 요구 사항에 대 한 자세한 내용은 [lync server 2013의 서버 및 도구 운영 체제 지원](lync-server-2013-server-and-tools-operating-system-support.md), lync server [2013의 추가 소프트웨어 요구 사항](lync-server-2013-additional-software-requirements.md)및 [lync server 2013의 추가 서버 지원 및 요구 사항을](lync-server-2013-additional-server-support-and-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc616-111">For details about operating system and software requirements to install the Lync Server administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="cc616-112">이 도구를 설치 및 사용 하기 위해 필요한 사용자 권한 및 사용 권한은 [Lync Server 2013의 설정 및 관리에 필요한 관리자 권한 및 사용 권한에](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-112">The user rights and permissions required to install and use the tools are described in [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<span data-ttu-id="cc616-113">관리 도구는 다음 항목으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-113">The administrative tools consist of the following:</span></span>

  - <span data-ttu-id="cc616-114">**Lync Server 배포 마법사**     Lync Server를 배포 하 고 모든 관리 도구를 설치 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-114">**Lync Server Deployment Wizard**   Use to deploy Lync Server and to install all administrative tools.</span></span>

  - <span data-ttu-id="cc616-115">**Lync Server 토폴로지 작성기**     배포의 구성 요소를 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-115">**Lync Server Topology Builder**   Use to define components in your deployment.</span></span>

  - <span data-ttu-id="cc616-116">**Lync Server 제어판**     웹 기반 인터페이스를 사용 하 여 배포를 지속적으로 관리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-116">**Lync Server Control Panel**   Use for ongoing management of your deployment by using a web-based interface.</span></span>

  - <span data-ttu-id="cc616-117">**Lync Server 관리 셸**     명령줄을 사용 하 여 배포를 지속적으로 관리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-117">**Lync Server Management Shell**   Use for ongoing management of your deployment by using the command line.</span></span>

  - <span data-ttu-id="cc616-118">**Lync Server 로깅 도구**     배포의 문제를 해결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-118">**Lync Server Logging tool**   Use to troubleshoot problems in your deployment.</span></span>

  - <span data-ttu-id="cc616-119">**중앙 로깅 서비스**     한 컴퓨터, 풀, 사이트 또는 전역에서 로그 및 추적 파일을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-119">**Centralized Logging Service**   Collect logs and trace files from one computer, pool, site or global.</span></span> <span data-ttu-id="cc616-120">공급자, 플래그 및 추적 수준이 포함 된 시나리오를 선택 하 고 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-120">Select and define scenarios that contain providers, flags and trace levels.</span></span> <span data-ttu-id="cc616-121">로깅은 텍스트 기반 도구 또는 Snooper.exe와 같은 도구를 사용 하 여 수집 및 집계 되 고 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-121">Logging is collected, aggregated and displayed with tools such as any text-based tool or Snooper.exe.</span></span>

<span data-ttu-id="cc616-122">기본적으로 토폴로지 작성기 및 Lync Server 제어판을 사용 하 여 배포를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-122">You can manage your deployment by primarily using Topology Builder and Lync Server Control Panel.</span></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="cc616-123">배포 마법사</span><span class="sxs-lookup"><span data-stu-id="cc616-123">Deployment Wizard</span></span>

<span data-ttu-id="cc616-124">Lync Server를 아직 설치 하지 않은 컴퓨터에 설치 미디어에 포함 된 Lync Server 배포 마법사를 사용 하 여 모든 관리 도구를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-124">You must use the Lync Server Deployment Wizard included on the installation media to install all administrative tools onto a computer on which you have not already installed Lync Server.</span></span> <span data-ttu-id="cc616-125">관리 도구 설치 프로세스 중에 Lync Server 배포 마법사는 다른 도구와 함께 로컬로 설치 되므로 나중에 추가 구성 요소에 대 한 파일을 설치 하거나 컴퓨터에서 사용 하지 않으려는 구성 요소에 대 한 파일을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-125">During the administrative tools installation process, the Lync Server Deployment Wizard is installed locally along with the other tools so that you can later use it to install files for additional components or remove files for components that you do not want on the computer.</span></span>

<span data-ttu-id="cc616-126">Lync Server 설치 미디어에서 처음으로 Lync Server 배포 마법사를 실행 하는 방법에 대 한 자세한 내용은 [Install Lync server 2013 관리 도구](lync-server-2013-install-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cc616-126">For details about how to run the Lync Server Deployment Wizard for the first time from the Lync Server installation media, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

</div>

<div>

## <a name="topology-builder"></a><span data-ttu-id="cc616-127">토폴로지 작성기</span><span class="sxs-lookup"><span data-stu-id="cc616-127">Topology Builder</span></span>

<span data-ttu-id="cc616-128">토폴로지 작성기를 사용 하 여 수행할 수 있는 배포 작업에 대 한 자세한 내용은 각 서버 역할에 대 한 배포 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cc616-128">For details about deployment tasks that you can you perform by using Topology Builder, see the Deployment documentation for each server role.</span></span>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="cc616-129">Lync Server 제어판</span><span class="sxs-lookup"><span data-stu-id="cc616-129">Lync Server Control Panel</span></span>

<span data-ttu-id="cc616-130">Lync Server 2013 제어판을 사용 하 여 Lync Server 2013를 관리 하 고 유지 관리 하는 데 필요한 대부분의 관리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-130">You can use Lync Server 2013 Control Panel to perform most of the administrative tasks required to manage and maintain Lync Server 2013.</span></span> <span data-ttu-id="cc616-131">Lync Server 제어판은 조직의 사용자, 클라이언트 및 장치 외에도 Lync Server 실행 서버의 구성을 관리 하기 위한 GUI (그래픽 사용자 인터페이스)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-131">Lync Server Control Panel provides you with a graphical user interface (GUI) to manage the configuration of the servers running Lync Server, in addition to the users, clients, and devices in your organization.</span></span> <span data-ttu-id="cc616-132">Lync server 관리 셸이 lync server 제어판을 기본 메커니즘으로 사용 하 여 Lync Server 구성을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-132">Lync Server Management Shell uses Lync Server Control Panel as the underlying mechanism to perform Lync Server configuration.</span></span>

<span data-ttu-id="cc616-133">Lync Server 제어판은 모든 Lync Server 프런트 엔드 서버 또는 Standard Edition 서버에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-133">Lync Server Control Panel is automatically installed on every Lync Server Front End Server or Standard Edition server.</span></span> <span data-ttu-id="cc616-134">이번 릴리스에서는 에지 서버를 원격으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-134">In this release, you administer Edge Servers remotely.</span></span> <span data-ttu-id="cc616-135">Lync server를 중앙에서 관리 하려는 관리 콘솔과 같은 다른 컴퓨터에 Lync Server 제어판을 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-135">You can also install Lync Server Control Panel on another computer, such as a management console from which you want to centrally manage Lync Server.</span></span> <span data-ttu-id="cc616-136">자세한 내용은 [Install Lync Server 2013 관리 도구](lync-server-2013-install-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cc616-136">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="cc616-137">Lync Server 제어판을 사용 하 여 설정을 구성 하려면 CsAdministrator 역할에 할당 된 계정을 사용 하 여 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-137">To configure settings using Lync Server Control Panel, you must be logged in using an account that is assigned to the CsAdministrator role.</span></span> <span data-ttu-id="cc616-138">Lync Server 2013에서 사용할 수 있는 미리 정의 된 관리 역할에 대 한 자세한 내용은 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync server 2013에서 역할 기반 액세스 제어 계획</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cc616-138">For details about the predefined administrative roles available in Lync Server 2013, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="cc616-139">Lync Server 제어판을 사용 하 여 설정을 구성 하려면 최소 화면 해상도 1024 x 768의 컴퓨터도 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-139">To configure settings using Lync Server Control Panel, you must also use a computer with a minimum screen resolution of 1024 x 768.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a><span data-ttu-id="cc616-140">Communications Server 관리 셸</span><span class="sxs-lookup"><span data-stu-id="cc616-140">Lync Server Management Shell</span></span>

<span data-ttu-id="cc616-141">Lync Server에서 Lync Server 관리 셸은 관리 및 관리에 대 한 새로운 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-141">In Lync Server, the Lync Server Management Shell provides a new method for administration and management.</span></span> <span data-ttu-id="cc616-142">Lync Server 관리 셸은 Windows PowerShell 명령줄 인터페이스를 기반으로 작성 된 강력한 관리 인터페이스로, Lync Server와 관련 된 포괄적인 cmdlet 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-142">Lync Server Management Shell is a powerful management interface, built on the Windows PowerShell command-line interface, that includes a comprehensive set of cmdlets that are specific to Lync Server.</span></span> <span data-ttu-id="cc616-143">Lync Server 관리 셸을 사용 하 여 다양 한 구성 및 자동화 컨트롤을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-143">With Lync Server Management Shell, you gain a rich set of configuration and automation controls.</span></span> <span data-ttu-id="cc616-144">토폴로지 작성기 및 Lync Server 제어판 둘 다 Lync Server의 관리를 지원 하기 위해 이러한 cmdlet의 하위 집합을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-144">Topology Builder and Lync Server Control Panel both implement subsets of these cmdlets to support management of Lync Server.</span></span> <span data-ttu-id="cc616-145">Lync Server 관리 셸에서는 모든 Lync Server 관리 작업에 대 한 cmdlet이 포함 되며,이 cmdlet을 개별적으로 사용 하 여 배포를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-145">The Lync Server Management Shell includes cmdlets for all Lync Server administration tasks, and you can use the cmdlets individually to manage your deployment.</span></span> <span data-ttu-id="cc616-146">자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서 또는 각 cmdlet에 대 한 명령줄 도움말을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cc616-146">For details, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation or the command-line help for each cmdlet.</span></span>

</div>

<div>

## <a name="logging-tool"></a><span data-ttu-id="cc616-147">로깅 도구</span><span class="sxs-lookup"><span data-stu-id="cc616-147">Logging Tool</span></span>

<span data-ttu-id="cc616-148">Lync Server 로깅 도구를 이용 하면 제품을 실행 하는 동안 제품에서 로깅 및 추적 정보를 캡처하여 문제를 쉽게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-148">The Lync Server Logging Tool facilitates troubleshooting by capturing logging and tracing information from the product while the product is running.</span></span> <span data-ttu-id="cc616-149">이 도구를 사용 하 여 모든 Lync Server 서버 역할에서 디버그 세션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-149">You can use the tool to run debug sessions on any Lync Server server role.</span></span> <span data-ttu-id="cc616-150">로깅 도구에 대 한 자세한 내용은 TechNet 라이브러리에서 Lync Server 2010 로깅 도구 설명서를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) .</span><span class="sxs-lookup"><span data-stu-id="cc616-150">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc616-151">중앙 로깅 서비스는 모든 상황에서 Lync Server 로깅 도구를 통해 모든 로깅 수집에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-151">The Centralized Logging Service is recommended for all logging collection over the Lync Server Logging Tool in all circumstances.</span></span> <span data-ttu-id="cc616-152">Lync Server 로깅 도구는 계속 작동 하지만, 중앙 로깅 서비스가 이미 실행 되 고 있는 경우에는 거의 대부분의 경우에는 비효율적으로 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-152">The Lync Server Logging Tool will still work, but it will interfere or be rendered mostly ineffective if the Centralized Logging Service is already running.</span></span> <span data-ttu-id="cc616-153">중앙 로깅 서비스 또는 Lync Server 로깅 도구를 하나만 사용 해야 하며 동시에 수행 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc616-153">You should use only the Centralized Logging Service or the Lync Server Logging Tool, but never both concurrently.</span></span> <span data-ttu-id="cc616-154">중앙 로깅 서비스에 대 한 자세한 내용과 단독으로 사용 해야 하는 이유는 <A href="lync-server-2013-using-the-centralized-logging-service.md">Lync Server 2013에서 중앙화 된 로깅 서비스 사용</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc616-154">For more information on the Centralized Logging Service and why you should use it exclusively, see <A href="lync-server-2013-using-the-centralized-logging-service.md">Using the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cc616-155">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="cc616-155">In This Section</span></span>

  - [<span data-ttu-id="cc616-156">Lync Server 2013의 관리 도구 인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc616-156">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [<span data-ttu-id="cc616-157">Lync Server 2013의 서버 및 도구 운영 체제 지원</span><span class="sxs-lookup"><span data-stu-id="cc616-157">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="cc616-158">Lync Server 2013의 관리 도구 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc616-158">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)

  - [<span data-ttu-id="cc616-159">Lync Server 2013의 설정 및 관리에 필요한 관리자 권한 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="cc616-159">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [<span data-ttu-id="cc616-160">Lync Server 2013의 토폴로지 게시 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc616-160">Requirements to publish a topology in Lync Server 2013</span></span>](lync-server-2013-requirements-to-publish-a-topology.md)

  - [<span data-ttu-id="cc616-161">Lync Server 2013 관리 도구 설치</span><span class="sxs-lookup"><span data-stu-id="cc616-161">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

  - [<span data-ttu-id="cc616-162">Lync Server 2013 관리 도구 열기</span><span class="sxs-lookup"><span data-stu-id="cc616-162">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)

  - [<span data-ttu-id="cc616-163">Lync Server 2013 제어판 문제 해결</span><span class="sxs-lookup"><span data-stu-id="cc616-163">Troubleshooting Lync Server 2013 Control Panel</span></span>](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [<span data-ttu-id="cc616-164">Lync Server 2013에서 중앙 로깅 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="cc616-164">Using the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc616-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc616-165">See Also</span></span>


[<span data-ttu-id="cc616-166">Lync Server 2013 관리 셸</span><span class="sxs-lookup"><span data-stu-id="cc616-166">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

