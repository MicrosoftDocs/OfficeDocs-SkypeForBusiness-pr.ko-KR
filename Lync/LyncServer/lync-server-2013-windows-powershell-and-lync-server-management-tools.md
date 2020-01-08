---
title: 'Lync Server 2013: Windows PowerShell 및 Lync Server 관리 도구'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814253d909ff7065ccc028cf5822be7a7331a2fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="9742f-102">Windows PowerShell 및 Lync Server 2013 관리 도구</span><span class="sxs-lookup"><span data-stu-id="9742f-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9742f-103">_**마지막으로 수정한 주제:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="9742f-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="9742f-104">Microsoft Lync Server 2013에서 관리 도구는 Windows PowerShell을 사용 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="9742f-105">Windows PowerShell에는 명령줄 환경, 제품별 명령, 전체 스크립트 언어가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="9742f-106">Windows PowerShell을 사용 하 여 구현 되는 Lync Server 2013 도구에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="9742f-107">**토폴로지 작성기**.</span><span class="sxs-lookup"><span data-stu-id="9742f-107">**Topology Builder**.</span></span> <span data-ttu-id="9742f-108">토폴로지 작성기를 사용 하 여 계획 된 토폴로지를 만들고, 조정 하 고, 게시 하 고, 서버 설치를 시작 하기 전에 토폴로지의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="9742f-109">개별 서버에 Lync Server 2013을 설치 하는 경우 서버는 설치 프로세스의 일부로 게시 된 토폴로지를 읽고, 설치 프로그램은 토폴로지에서 지시한 대로 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="9742f-110">설치 후에는 모든 서버에 구성 정보가 자동으로 복제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="9742f-111">토폴로지 작성기를 사용 하는 경우에만 구성 요소를 배포에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="9742f-112">**Lync Server 관리 셸**.</span><span class="sxs-lookup"><span data-stu-id="9742f-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="9742f-113">배포의 전체 명령줄 관리를 위해 Lync Server Management Shell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="9742f-114">**Lync 서버 컨트롤 패널**</span><span class="sxs-lookup"><span data-stu-id="9742f-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="9742f-115">Microsoft Lync Server 2013 제어판 사용자 인터페이스를 사용 하 여 배포에서 가장 일반적인 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="9742f-116">이러한 도구는 550 제품별 cmdlet을 포함 하 여 배포 관리를 위해 Windows PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="9742f-117">Lync Server 2013에 포함 된 보안 cmdlet은 주로 인증을 관리 하는 데 사용 되며 사용자 권한 및 사용 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="9742f-118">인증서 및 PIN (개인 식별 번호) 인증에 대 한 cmdlet을 비롯 한 다양 한 cmdlet을 인증 관리에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="9742f-119">또한 많은 cmdlet을 사용 하 여 Lync Server 2013의 관리 제어를 위임할 수 있는 새 RBAC (역할 기반 액세스 제어) 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="9742f-120">Lync Server cmdlet에 대 한 자세한 내용은 [Lync server 2013 관리 셸을](lync-server-2013-lync-server-management-shell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9742f-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="9742f-121">Windows PowerShell 용 스크립트 보안 기능은 Microsoft VBScript (Visual Basic Scripting Edition)를 포함 하 여 이전 기술의 일부 스크립팅 관련 보안 문제를 방지 하기 위해 특별히 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="9742f-122">Windows PowerShell 보안 기능은 사용자가 스크립트를 쉽게 실행할 수 없는 환경을 만들기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="9742f-123">기본적으로 Windows PowerShell 보안 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="9742f-124">이러한 기능의 상태를 스크립트 요구와 다양 한 보안 목표에 맞게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="9742f-125">이는 셸이 사용자가 스크립트를 실행할 수 없다는 것을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="9742f-126">대신 셸은 기본적으로 사용자가 수행 하는 작업을 인식 하지 않고 스크립트를 실행할 수 있도록 어렵게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9742f-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="9742f-127">자세한 내용은 Windows PowerShell 스크립트 보안을 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).</span><span class="sxs-lookup"><span data-stu-id="9742f-127">For details, see Windows PowerShell Script Security at [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

