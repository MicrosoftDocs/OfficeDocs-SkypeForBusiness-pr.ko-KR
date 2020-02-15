---
title: 'Lync Server 2013: Windows PowerShell 및 Lync Server 관리 도구'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e475cd9249030ec09ad3261e84e068d9db0e8c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="af5fa-102">Windows PowerShell 및 Lync Server 2013 관리 도구</span><span class="sxs-lookup"><span data-stu-id="af5fa-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af5fa-103">_**마지막으로 수정 된 항목:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="af5fa-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="af5fa-104">Microsoft Lync Server 2013에서는 Windows PowerShell을 사용 하 여 관리 도구를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="af5fa-105">Windows PowerShell에는 명령줄 환경, 제품별 명령 및 전체 스크립팅 언어가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="af5fa-106">Windows PowerShell을 사용 하 여 구현 되는 Lync Server 2013 도구에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="af5fa-107">**토폴로지 작성기**</span><span class="sxs-lookup"><span data-stu-id="af5fa-107">**Topology Builder**.</span></span> <span data-ttu-id="af5fa-108">토폴로지 작성기를 사용 하 여 계획 된 토폴로지를 만들고, 조정 하 고, 게시 하며, 서버 설치를 시작 하기 전에 토폴로지의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="af5fa-109">개별 서버에 Lync Server 2013을 설치 하는 경우 서버는 설치 프로세스의 일부로 게시 된 토폴로지를 읽고, 설치 프로그램은 토폴로지의 지시에 따라 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="af5fa-110">설치 후에는 구성 정보가 모든 서버에 자동으로 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="af5fa-111">구성 요소는 토폴로지 작성기를 통해서만 배포에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="af5fa-112">**Lync Server 관리 셸**.</span><span class="sxs-lookup"><span data-stu-id="af5fa-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="af5fa-113">배포의 전체 명령줄 관리를 위해 Lync Server 관리 셸을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="af5fa-114">**Lync Server 제어판**</span><span class="sxs-lookup"><span data-stu-id="af5fa-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="af5fa-115">Microsoft Lync Server 2013 제어판 사용자 인터페이스를 사용 하 여 배포에서 가장 일반적인 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="af5fa-116">이러한 도구에서는 약 550개의 제품별 cmdlet을 포함하여 배포 관리를 위한 Windows PowerShell cmdlet이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="af5fa-117">Lync Server 2013에 포함 된 보안 cmdlet은 주로 인증을 관리 하는 데 사용 되며 사용자 권한 및 사용 권한을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="af5fa-118">인증서 및 PIN(개인 식별 번호) 인증을 위한 cmdlet 등 인증 관리에 사용할 수 있는 다양한 cmdlet가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="af5fa-119">또한 많은 cmdlet을 사용 하 여 새 RBAC (역할 기반 액세스 제어) 기능을 통해 Lync Server 2013의 관리 제어를 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="af5fa-120">Lync Server cmdlet에 대 한 자세한 내용은 [Lync server 2013 관리 셸을](lync-server-2013-lync-server-management-shell.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="af5fa-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="af5fa-121">Windows PowerShell의 스크립트 보안 기능은 특히 Microsoft Visual Basic Scripting Edition(VBScript)을 포함하는 이전 기술들의 일부 스크립트 관련 보안 문제를 방지하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="af5fa-122">Windows PowerShell 보안 기능은 사용자가 쉽게 또는 알지 못한 상태로 스크립트를 실행할 수 없는 환경을 만들기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="af5fa-123">Windows PowerShell 보안 기능은 기본적으로 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="af5fa-124">스크립트 요구 사항 및 다양한 보안 목표에 맞게 이러한 기능의 상태를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="af5fa-125">그렇다고 해서 사용자가 스크립트를 실행할 수 없도록 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="af5fa-126">셸의 목적은 사용자가 자신이 스크립트를 실행하고 있다는 사실을 인지하지 못한 상태로 스크립트를 실행하기 어렵게 만들기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="af5fa-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="af5fa-127">자세한 내용은 Windows PowerShell 스크립트 보안을 참조 하십시오 [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).</span><span class="sxs-lookup"><span data-stu-id="af5fa-127">For details, see Windows PowerShell Script Security at [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

