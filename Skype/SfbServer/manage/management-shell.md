---
title: 비즈니스용 Skype 서버 관리 쉘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: 비즈니스용 Skype 서버 관리 셸에서는 서버 관리 및 관리를 위한 명령줄 인터페이스를 제공 합니다. 이 파일은 Windows PowerShell을 기반으로 작성 되었으며, Skype 및 레거시 Lync server 제품과 관련 된 광범위 한 관리 및 관리 cmdlet 집합을 포함 합니다.
ms.openlocfilehash: 085c8f4a8a454f97dc4fbc640a6f5c8a70baec31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044260"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="8e547-104">비즈니스용 Skype 서버 관리 쉘</span><span class="sxs-lookup"><span data-stu-id="8e547-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="8e547-105">비즈니스용 Skype 서버 관리 셸에서는 서버 관리 및 관리를 위한 명령줄 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="8e547-106">이 파일은 Windows PowerShell을 기반으로 작성 되었으며, Skype 및 레거시 Lync server 제품과 관련 된 광범위 한 관리 및 관리 cmdlet 집합을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="8e547-107">Windows PowerShell을 사용 하면 명령줄에서 Microsoft 응용 프로그램을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="8e547-108">명령줄 환경, 제품별 명령 및 전체 스크립트 언어를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="8e547-109">Windows PowerShell은 처음에 2006의 Windows 운영 체제에 대 한 다운로드 가능한 릴리스로 도입 되었으며, Microsoft Exchange Server 2007의 관리 효율성을 위한 명령줄 인터페이스로 통합 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="8e547-110">Lync Server 2010로 시작 하는 Lync 및 Skype 서버를 포함 하 여 대부분의 Microsoft 서버 제품에 통합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="8e547-111">비즈니스용 Skype 서버 관리 셸에서 사용할 수 있는 700 Lync 및 Skype 관련 cmdlet이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e547-112">비즈니스용 Skype cmdlet 참조가 docs.microsoft.com로 이동 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="8e547-113">아래 링크를 클릭 하면 새 docs.microsoft.com 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="8e547-114">이제 콘텐츠가 사용 가능 하 게 열리고 GitHub를 통한 커뮤니티 기고에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="8e547-115">참여에 관심이 있으십니까?</span><span class="sxs-lookup"><span data-stu-id="8e547-115">Interested in contributing?</span></span> <span data-ttu-id="8e547-116">여기에 있는 리포지토리의 추가 정보를 확인 하세요.[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="8e547-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="8e547-117">비즈니스용 skype 서버에는 관리자가 비즈니스용 skype 서버 관리 셸을 사용 하 여 비즈니스용 Skype 서버를 관리 하도록 해 주는 cmdlet이 700 개 이상 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="8e547-118">명령줄에서 다음과 같은 명령을 입력 하 여 cmdlet에 대 한 도움말을 직접 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="8e547-119">위 명령은 **set-csvoicepolicy** cmdlet에 사용할 수 있는 전체 도움말을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="8e547-120">다른 cmdlet에 대 한 도움말을 보려면 **set-csvoicepolicy** 를 도움말을 검색 하려는 cmdlet의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="8e547-121">비즈니스용 Skype 서버를 관리 하는 데 사용할 수 있는 전체 cmdlet 목록을 검색 하려면 셸 명령 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="8e547-122">비즈니스용 Skype 서버의 Windows PowerShell에 대해 알아야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="8e547-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="8e547-123">비즈니스용 Skype 서버 cmdlet을 실행 하려면 비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="8e547-124">비즈니스용 Skype 서버 관리 셸이 아닌 Windows PowerShell 창을 여는 경우 기본적으로 Skype cmdlet을 실행 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="8e547-125">Windows PowerShell 내에서 비즈니스용 Skype 서버 cmdlet을 실행 하려면 먼저 Windows PowerShell 명령 프롬프트에 다음을 입력 합니다. >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="8e547-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="8e547-126">비즈니스용 skype 서버 관리 셸은 모든 비즈니스용 Skype 서버 Enterprise Edition 프런트 엔드 서버 또는 Standard Edition 서버에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="8e547-127">[업데이트-도움말](https://technet.microsoft.com/library/hh849720.aspx) cmdlet을 실행 하 여 비즈니스용 Skype 서버 관리 셸 도움말 콘텐츠를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="8e547-128">업데이트-도움말 cmdlet은 비즈니스용 Skype cmdlet에 대 한 업데이트를 포함 하 여 컴퓨터에 설치 된 모든 모듈에 사용할 수 있는 최신 도움말 파일을 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="8e547-129">기본적으로, **업데이트-도움말** Cmdlet은 비즈니스용 Skype 서버에 설치 된 모든 모듈을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="8e547-130">특정 모듈만 업데이트 하려는 경우 _Module_ 매개 변수를 사용 하 여 cmdlet의 범위를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="8e547-131">다음 예에서는 비즈니스용 Skype 모듈만 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="8e547-132">인터넷에 연결 되어 있지 않은 서버에서 도움말을 업데이트 해야 하는 경우에는 [help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet을 사용 하 여 최신 버전의 도움말을 가져온 다음 지정한 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="8e547-133">그런 다음 인터넷에 연결 되지 않은 서버에서 _-SourcePath_ 매개 변수와 함께 **업데이트 도움말** cmdlet을 사용 하 여 선택한 위치에서 업데이트 된 도움말을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="8e547-134">다음은 도움말 파일을 네트워크 파일 공유에 저장 한 다음 파일 공유에서 비즈니스용 Skype 모듈에 대 한 도움말을 업데이트 하는 방법을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="8e547-135">자세한 내용은 업데이트할 수 있는 [도움말](https://technet.microsoft.com/library/hh847735.aspx)정보를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e547-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8e547-136">PowerShell을 원격으로 사용 하는 경우 방화벽을 통한 통신을 허용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e547-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="8e547-137">PowerShell remoting에서 사용 하는 포트에 대 한 자세한 내용은 [Powershell remoting에서 사용](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)하는 포트를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e547-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

