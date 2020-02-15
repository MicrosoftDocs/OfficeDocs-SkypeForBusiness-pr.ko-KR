---
title: 'Lync Server 2013: 관리 도구 소프트웨어 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44395f820d8837bddbf03ac903a7baa811cab842
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41998653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="6e59c-102">Lync Server 2013의 관리 도구 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e59c-102">Administrative tools software requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e59c-103">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="6e59c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="6e59c-104">이 항목에서는 운영 체제 요구 사항 외에도 Lync Server 2013 관리 도구를 설치 하 고 사용 하는 데 필요한 소프트웨어에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e59c-104">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="6e59c-105">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="6e59c-105">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="6e59c-106">Lync Server 2013에는 64 비트 버전의 Microsoft .NET Framework 4.5이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e59c-106">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="6e59c-107">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="6e59c-107">Windows PowerShell 3.0</span></span>

<span data-ttu-id="6e59c-108">Microsoft Lync Server 2013의 구성 요소를 실행 하려면 Windows PowerShell 3.0이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e59c-108">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="6e59c-109">자세한 내용은 [설치 Windows PowerShell 3.0 For Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e59c-109">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="6e59c-110">Windows Installer 버전 4.5</span><span class="sxs-lookup"><span data-stu-id="6e59c-110">Windows Installer Version 4.5</span></span>

<span data-ttu-id="6e59c-111">Lync Server 2013에서는 Windows Installer 기술을 사용 하 여 다양 한 서버 역할을 설치, 제거 및 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e59c-111">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="6e59c-112">Windows Installer 버전 4.5는 Windows Server 운영 체제의 재배포 가능 구성 요소로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e59c-112">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="6e59c-113">Windows Installer 4.5에 windows Server 2012 R2, Windows Server 2012 및 Windows Server 2008 R2와 함께 제공 되는 경우 Lync Server 2013을 실행 하는 컴퓨터에 대해 유틸리티를 다운로드할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e59c-113">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="6e59c-114">Lync Server 2013는 windows Server 2012 R2, Windows Server 2012 또는 Windows Server 2008 R2를 실행 하는 컴퓨터에만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e59c-114">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="6e59c-115">그러나 관리자 워크스테이션에 Lync Server 관리 셸 또는 Lync Server 토폴로지 작성기를 설치 하려면 Windows Installer 4.5를 다운로드 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e59c-115">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="6e59c-116">이 유틸리티는 windows 7 및 Windows 2008 R2와 함께 제공 되지만 이전 버전의 Windows 운영 체제와는 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e59c-116">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="6e59c-117">Microsoft 다운로드 센터에서 Windows Installer 4.5를 다운로드할 수 있습니다 <http://go.microsoft.com/fwlink/p/?linkid=197395>.</span><span class="sxs-lookup"><span data-stu-id="6e59c-117">You can download Windows Installer 4.5 from the Microsoft Download Center at <http://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="6e59c-118">Microsoft Silverlight 5 browser 플러그 인</span><span class="sxs-lookup"><span data-stu-id="6e59c-118">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="6e59c-119">Lync Server 2013 제어판은 웹 기반 도구 이며 최신 버전의 Microsoft Silverlight 5 browser 플러그 인을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e59c-119">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="6e59c-120">Lync Server 2013 제어판을 시작할 때이 소프트웨어가 설치 되어 있지 않거나 이전 버전이 설치 되어 있으면 Lync Server 2013 제어판에 필요한 버전을 설치 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e59c-120">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e59c-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e59c-121">See Also</span></span>


[<span data-ttu-id="6e59c-122">Lync Server 2013의 서버 및 도구 운영 체제 지원</span><span class="sxs-lookup"><span data-stu-id="6e59c-122">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="6e59c-123">Lync Server 2013의 관리 도구 인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e59c-123">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="6e59c-124">Lync Server 2013의 설정 및 관리에 필요한 관리자 권한 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="6e59c-124">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

