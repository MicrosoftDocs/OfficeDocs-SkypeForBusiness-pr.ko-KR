---
title: 'Lync Server 2013: Lync 클라이언트 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d7f4497fb6842befba3f5facf5de023b94b4a76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="f7fca-102">Lync Server 2013에서 Lync 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="f7fca-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7fca-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f7fca-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f7fca-104">Lync 2013에는 클라이언트 배포에 대 한 다양 한 접근 방식이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="f7fca-105">이전 버전에서 출발 하면 Lync 2013에는 더 이상 자체 설치 관리자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="f7fca-106">대신 Office 2013 설치 프로그램에 Lync가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="f7fca-107">Lync 2013을 사용자에 게 배포 하려면 Office 2013 설치 방법 및 사용자 지정 도구를 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="f7fca-108">**Office 2013 Windows installer** 는 여러 MSI 파일로 구성 된 windows installer 기반 설치 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="f7fca-109">언어 중립적인 핵심 MSI 패키지는 완전 한 제품을 만들기 위해 하나 이상의 언어별 패키지와 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="f7fca-110">설치 프로그램은 개별 패키지를 조립 하 고 사용자의 컴퓨터에 Office를 설치 하는 동안과 사용자 지정 및 유지 관리 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="f7fca-111">이 섹션의 항목에서는 Office 2013 Windows Installer를 사용 하 고 사용자 지정 하 여 Lync 2013를 배포 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="f7fca-112">**Office 2013 간편 실행** 은 Microsoft office 365 포털에서 office 설치 파일을 사용자에 게 스트리밍하는 설치 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft Office 365 portal.</span></span> <span data-ttu-id="f7fca-113">관리자는 간편 실행을 위한 Office 배포 도구를 사용 하 여 설치를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="f7fca-114">Office 2013 간편 실행은 주로 Microsoft Office 365 환경에서 사용 되므로이 섹션에서는이 설치 방법을 자세히 설명 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="f7fca-115">간편 실행 설치를 사용 하 고 사용자 지정 하는 방법에 대 한 자세한 내용은 Office 2013 리소스 키트 설명서에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="f7fca-116">또한 관리자는 온-프레미스 위치에 Office 2013 간편 실행 프로그램 및 언어 원본 파일을 다운로드할 수 있으며,이는 네트워크에 대 한 수요를 최소화 하거나 사용자가 인터넷에서 소프트웨어를 설치 하지 못하도록 하는 데 유용 합니다. 기업 보안 요구 사항.</span><span class="sxs-lookup"><span data-stu-id="f7fca-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="f7fca-117">이 섹션의 항목에서는 Office 2013 MSI 기반 설치 관리자를 사용 하 여 클라이언트를 배포 하는 방법에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="f7fca-118">기본 참조는 인프라 준비, 설치 사용자 지정, Office 2013 배포 방법에 대해 자세히 설명 하는 Office 2013 리소스 키트 설명서 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="f7fca-119">그러나이 섹션의 항목을 함께 사용 하 여 Lync 2013에 대 한 배포 고려 사항을 설명 하는 Office 설명서를 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="f7fca-120">Outlook messaging 및 공동 작업 클라이언트 내에서 모임 관리를 지 원하는 Lync 2013의 온라인 모임 추가 기능이 Lync 2013를 사용 하 여 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="f7fca-121">Office 2013 설치 프로그램이 이전 버전의 Lync 또는 Office Communicator를 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="f7fca-122">Lync 2013 클라이언트는 다른 Lync 또는 Office Communicator 클라이언트와 나란히 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7fca-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f7fca-123">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="f7fca-123">In This Section</span></span>

  - [<span data-ttu-id="f7fca-124">Lync Server 2013에서 클라이언트 설치 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="f7fca-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="f7fca-125">Lync Server 2013에서 Lync 동작 및 사용자 인터페이스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="f7fca-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="f7fca-126">Lync Server 2013에서 온라인 모임 추가 기능 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="f7fca-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="f7fca-127">Lync Server 2013에서 모임 참가 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="f7fca-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="f7fca-128">Lync Server 2013에서 지원 되는 클라이언트 버전 구성</span><span class="sxs-lookup"><span data-stu-id="f7fca-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="f7fca-129">Lync Server 2013에서 향상 된 현재 상태 개인 정보 모드 구성</span><span class="sxs-lookup"><span data-stu-id="f7fca-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

