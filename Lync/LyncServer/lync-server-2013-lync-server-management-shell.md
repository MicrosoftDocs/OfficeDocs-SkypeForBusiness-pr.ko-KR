---
title: 'Lync Server 2013: Lync Server 관리 셸'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29fdc8e5f13687d2bed0e0c35609187c57d11592
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="a6c9a-102">Lync Server 2013 관리 셸</span><span class="sxs-lookup"><span data-stu-id="a6c9a-102">Lync Server 2013 Management Shell</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6c9a-103">_**마지막으로 수정한 주제:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="a6c9a-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6c9a-104">비즈니스용 Skype cmdlet 참조가 docs.microsoft.com으로 이동 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-104">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="a6c9a-105">아래 링크를 클릭 하면 새 docs.microsoft.com 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-105">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="a6c9a-106">이제 콘텐츠가 열리고, GitHub를 통해 커뮤니티에서 기고 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-106">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="a6c9a-107">참여 하는 데 관심이 있으십니까?</span><span class="sxs-lookup"><span data-stu-id="a6c9a-107">Interested in contributing?</span></span> <span data-ttu-id="a6c9a-108">여기에 있는 리포지토리의 추가 정보를 확인 하세요.<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="a6c9a-108">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="a6c9a-109">Microsoft Lync Server 2010에는 Microsoft Office Communications Server 2007 R2에서 제공 하는 것과 비교 하 여 다양 한 새롭고 향상 된 기능이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-109">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="a6c9a-110">한 가지 개선 사항은 구현을 관리 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-110">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="a6c9a-111">예를 들어 Lync Server 제어판 이라는 새 사용자 인터페이스가 있는데,이는 대부분의 사용자가 Microsoft 관리 콘솔에서 사용 하는 대규모 이동을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-111">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="a6c9a-112">관리 효율성에 대 한 그 밖의 주요 개선 사항은 Windows PowerShell을 포함 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-112">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="a6c9a-113">Windows PowerShell을 사용 하면 명령줄에서 Microsoft 응용 프로그램을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-113">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="a6c9a-114">여기에는 명령줄 환경, 제품별 명령, 전체 스크립팅 언어가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-114">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="a6c9a-115">Windows PowerShell은 먼저 2006에서 발생 하는 Windows 운영 체제의 다운로드 가능한 릴리스로 도입 되었으며 Microsoft Exchange Server 2007의 관리 효율성을 위한 명령줄 인터페이스로 통합 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-115">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="a6c9a-116">그 당시에는 microsoft Lync Server 2013의 최신 버전을 Microsoft 서버 제품에 통합 하는 것이 더 커지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-116">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="a6c9a-117">Lync Server 2010는 배포의 모든 측면을 관리 하는 데 사용할 수 있는 550 제품별 cmdlet을 도입 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-117">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="a6c9a-118">다음 섹션에는 cmdlet 및 해당 설명 목록이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-118">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="a6c9a-119">이 정보는 명령줄에서 직접 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-119">This information is also available directly from the command line.</span></span> <span data-ttu-id="a6c9a-120">Lync Server 관리 셸 명령 프롬프트에서 다음을 입력 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-120">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="a6c9a-121">예를 들어 명령 프롬프트에서 **New-CsVoicePolicy** cmdlet에 대한 도움말을 검색하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-121">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="a6c9a-122">Lync Server 2013의 Windows PowerShell에 대해 알아야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="a6c9a-122">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="a6c9a-123">Lync Server cmdlet을 실행 하려면 Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-123">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a6c9a-124">Lync Server 관리 셸이 아닌 Windows PowerShell 창을 여는 경우 기본적으로 Lync Server cmdlet을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-124">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="a6c9a-125">Windows PowerShell에서 Lync Server cmdlet을 실행 하려면 먼저 Windows PowerShell 명령 프롬프트에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-125">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="a6c9a-126">가져오기-모듈 Lync</span><span class="sxs-lookup"><span data-stu-id="a6c9a-126">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="a6c9a-127">Lync server 관리 셸은 모든 Lync Server Enterprise Edition 프런트 엔드 서버 또는 Standard Edition 서버에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-127">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="a6c9a-128">Windows PowerShell 및 Microsoft Lync Server 2013 cmdlet에 대 한 새로운 및 업데이트 된 정보, 샘플 스크립트, 시작 및 학습에 대 한 도움말은 Lync Server Windows PowerShell 블로그에서 [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6c9a-128">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

