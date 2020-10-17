---
title: 'Lync Server 2013: Lync Server 관리 도구 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ded1dbdcd81c846db9f23574fa0b39efa0c33dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498725"
---
# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="70e05-102">Lync Server 2013 관리 도구 설치</span><span class="sxs-lookup"><span data-stu-id="70e05-102">Install Lync Server 2013 administrative tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70e05-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="70e05-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="70e05-104">이 항목에서는 Lync Server 2013를 배포 하 고 관리 하는 데 필요한 관리 도구를 설치 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-104">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="70e05-105">관리 도구는 Lync Server 2013를 실행 하는 각 서버에 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-105">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="70e05-106">또한 전용 관리 콘솔과 같은 다른 컴퓨터에 관리 도구를 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="70e05-107">Active Directory 도메인 서비스 준비 단계가 이미 완료 되었는지 확인 하 여 나중에 해당 컴퓨터의 관리 도구를 사용 하 여 토폴로지를 게시할 수 있으므로, 만드는 중인 Lync Server 2013 배포와 동일한 도메인 또는 포리스트에 있는 컴퓨터에 관리 도구를 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-107">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="70e05-108">Lync Server 2013 관리 도구를 설치 하거나 사용 하기 전에 인프라, 운영 체제, 소프트웨어 및 관리자 권한 요구 사항을 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-108">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="70e05-109">인프라 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 관리 도구 인프라 요구 사항을](lync-server-2013-administrative-tools-infrastructure-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70e05-109">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="70e05-110">Lync server 2013 관리 도구를 설치 하기 위한 운영 체제 및 소프트웨어 요구 사항에 대 한 자세한 내용은 [lync server 2013의 서버 및 도구 운영 체제 지원](lync-server-2013-server-and-tools-operating-system-support.md), lync server [2013의 추가 소프트웨어 요구 사항](lync-server-2013-additional-software-requirements.md)및 [lync server 2013의 추가 서버 지원 및 요구 사항을](lync-server-2013-additional-server-support-and-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70e05-110">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="70e05-111">도구를 설치 및 사용 하는 데 필요한 사용자 권한 및 사용 권한에 대 한 자세한 내용은 [Lync Server 2013의 설정 및 관리에 필요한 관리자 권한 및 사용 권한](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70e05-111">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="70e05-112">조직에서 IIS(인터넷 정보 서비스)와 모든 웹 서비스를 시스템 드라이브가 아닌 다른 드라이브에 배치해야 하는 경우 설치 프로그램 대화 상자에서 nm-server-w15-long 파일의 설치 위치 경로를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-112">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="70e05-113">OCSCore.msi를 포함 하 여이 경로에 설치 파일을 설치 하면 나머지 Lync Server 2013 파일이이 드라이브에도 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-113">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="70e05-114">Lync Server 2013 관리 도구를 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="70e05-114">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="70e05-p104">관리 도구를 설치할 컴퓨터에 로컬 관리자(최소 요구 사항)로 로그온합니다. Windows Vista 또는 Windows 7 운영 체제에서 표준 사용자로 로그온하는 경우 UAC(사용자 계정 제어)가 사용하도록 설정되어 있으면 로컬 관리자 또는 도메인의 해당 사용자 이름과 암호를 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-p104">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools. If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="70e05-117">컴퓨터에서 설치 미디어를 찾은 다음 Setup amd64Setup.exe를 두 번 \\ 클릭 \\ \\ 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-117">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="70e05-118">Microsoft Visual C++ 2008 배포 가능 파일을 설치할지 묻는 메시지가 표시되면 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-118">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="70e05-119">**Microsoft Lync Server 2013 설치 위치** 페이지에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-119">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="70e05-120">다른 위치에 파일을 설치해야 하는 경우 이 경로를 다른 위치나 드라이브로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-120">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="70e05-121">조직에서 IIS (인터넷 정보 서비스) 및 모든 웹 서비스를 시스템 드라이브 이외의 드라이브에 배치 해야 하는 경우 설치 대화 상자에서 Lync Server 2013 파일의 설치 위치 경로를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-121">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="70e05-122">OCSCore.msi를 포함 하 여이 경로에 설치 파일을 설치 하는 경우 나머지 Lync Server 2013 파일은이 드라이브에도 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="70e05-p107">**최종 사용자 사용권 계약** 페이지에서 사용 조건을 검토하고 **동의함**, **확인**을 차례로 클릭합니다. 계속하려면 이 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-p107">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**. This step is required before you can continue.</span></span>

6.  <span data-ttu-id="70e05-125">**Microsoft Lync Server 2013 – 배포 마법사** 페이지에서 **관리자 도구 설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-125">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="70e05-126">설치가 완료되면 **끝내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70e05-126">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70e05-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70e05-127">See Also</span></span>


[<span data-ttu-id="70e05-128">Lync Server 2013 관리 도구 열기</span><span class="sxs-lookup"><span data-stu-id="70e05-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="70e05-129">Lync Server 2013 관리 도구</span><span class="sxs-lookup"><span data-stu-id="70e05-129">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

