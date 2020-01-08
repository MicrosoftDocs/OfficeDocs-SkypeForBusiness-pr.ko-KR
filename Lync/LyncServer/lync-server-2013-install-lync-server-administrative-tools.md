---
title: 'Lync Server 2013: Lync Server 관리 도구 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1115d5848806f95d35a158f36b7689967cec5d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="74f74-102">Lync Server 2013 관리 도구 설치</span><span class="sxs-lookup"><span data-stu-id="74f74-102">Install Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74f74-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="74f74-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="74f74-104">이 항목에서는 Lync Server 2013를 배포 하 고 관리 하는 데 필요한 관리 도구를 설치 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-104">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="74f74-105">관리 도구는 Lync Server 2013를 실행 하는 각 서버에 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-105">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="74f74-106">또한 다른 컴퓨터에 관리 도구 (예: 전용 관리 콘솔)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="74f74-107">Active Directory 도메인 서비스 준비 단계가 이미 실행 되 고 있는지 확인 하 여 만드는 Lync Server 2013 배포와 동일한 도메인 또는 포리스트의 컴퓨터에 관리 도구를 설치 하는 것이 좋습니다. 완료를 통해 나중에 해당 컴퓨터의 관리 도구를 사용 하 여 토폴로지를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-107">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="74f74-108">Lync Server 2013 관리 도구를 설치 하거나 사용 하기 전에 인프라, 운영 체제, 소프트웨어 및 관리자 권한 요구 사항이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-108">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="74f74-109">인프라 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 관리 도구 인프라 요구 사항을](lync-server-2013-administrative-tools-infrastructure-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74f74-109">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="74f74-110">Lync Server 2013 관리 도구를 설치 하기 위한 운영 체제 및 소프트웨어 요구 사항에 대 한 자세한 내용은 [Lync server 2013의 서버 및 도구 운영 체제 지원](lync-server-2013-server-and-tools-operating-system-support.md), lync [server 2013에 대 한 추가 소프트웨어 요구 사항](lync-server-2013-additional-software-requirements.md)및 [lync server 2013의 추가 서버 지원 및 요구 사항을](lync-server-2013-additional-server-support-and-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74f74-110">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="74f74-111">도구를 설치 하 고 사용 하는 데 필요한 사용자 권한 및 사용 권한에 대 한 자세한 내용은 [Lync Server 2013의 설정 및 관리에 필요한 관리자 권한 및 사용 권한을](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74f74-111">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="74f74-112">조직에서 IIS (인터넷 정보 서비스) 및 시스템 드라이브가 아닌 다른 드라이브의 모든 웹 서비스를 찾아야 하는 경우 설정 대화 상자에서 Lync Server 파일의 설치 위치 경로를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-112">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="74f74-113">OCSCore를 포함 하 여이 경로에 설치 파일을 설치 하는 경우에는 Lync Server 2013 파일의 나머지 부분도이 드라이브에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-113">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="74f74-114">Lync Server 2013 관리 도구를 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="74f74-114">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="74f74-115">관리 도구를 설치 하려는 컴퓨터에 로컬 관리자 (최소 요구 사항)로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-115">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools.</span></span> <span data-ttu-id="74f74-116">Windows Vista 또는 Windows 7 운영 체제에 표준 사용자로 로그온 한 경우 UAC (사용자 계정 컨트롤)를 사용 하도록 설정 하면 로컬 관리자 또는 도메인에 해당 하는 사용자 이름 및 암호를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-116">If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="74f74-117">컴퓨터에서 설치 미디어를 찾은 다음 설치 \\\\amd64\\setup.exe를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-117">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="74f74-118">Microsoft Visual c + + 2008 배포 가능을 설치 하 라는 메시지가 표시 되 면 **예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-118">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="74f74-119">**Microsoft Lync Server 2013 설치 위치** 페이지에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-119">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="74f74-120">다른 위치에 파일을 설치 해야 하는 경우이 경로를 다른 위치 또는 드라이브로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-120">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="74f74-121">조직에서 IIS (인터넷 정보 서비스) 및 시스템 드라이브가 아닌 다른 드라이브의 모든 웹 서비스를 찾아야 하는 경우 설정 대화 상자에서 Lync Server 2013 파일의 설치 위치 경로를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-121">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="74f74-122">OCSCore를 포함 하 여이 경로에 설치 파일을 설치 하면 나머지 Lync Server 2013 파일이이 드라이브에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="74f74-123">**최종 사용자 사용권 계약** 페이지에서 사용 약관을 검토 하 고 **동의 함**을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-123">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="74f74-124">계속 하려면이 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-124">This step is required before you can continue.</span></span>

6.  <span data-ttu-id="74f74-125">**Microsoft Lync Server 2013 – 배포 마법사** 페이지에서 **관리자 도구 설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-125">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="74f74-126">설치가 성공적으로 완료 되 면 **끝내기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f74-126">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74f74-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74f74-127">See Also</span></span>


[<span data-ttu-id="74f74-128">Lync Server 2013 관리 도구 열기</span><span class="sxs-lookup"><span data-stu-id="74f74-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="74f74-129">Lync Server 2013 관리 도구</span><span class="sxs-lookup"><span data-stu-id="74f74-129">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

