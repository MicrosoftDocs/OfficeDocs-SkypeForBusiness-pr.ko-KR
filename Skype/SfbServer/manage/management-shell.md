---
title: 비즈니스용 Skype 서버 관리 쉘
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: 비즈니스용 Skype 서버 관리 셸은 서버 관리 및 관리를 위한 명령줄 인터페이스를 제공합니다. 이 Cmdlet은 Windows PowerShell Skype 및 레거시 Lync 서버 제품과 관련이 있는 포괄적인 관리 및 관리 cmdlet 집합을 포함합니다.
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816538"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="da565-104">비즈니스용 Skype 서버 관리 쉘</span><span class="sxs-lookup"><span data-stu-id="da565-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="da565-105">비즈니스용 Skype 서버 관리 셸은 서버 관리 및 관리를 위한 명령줄 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da565-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="da565-106">이 Cmdlet은 Windows PowerShell Skype 및 레거시 Lync 서버 제품과 관련이 있는 포괄적인 관리 및 관리 cmdlet 집합을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="da565-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="da565-107">Windows PowerShell 명령줄에서 Microsoft 응용 프로그램을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="da565-108">여기에는 명령줄 환경, 제품별 명령 및 전체 스크립팅 언어가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="da565-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="da565-109">Windows PowerShell 2006년 후반 Windows 운영 체제용 다운로드 가능 릴리스로 처음 도입되어 2007년 2007의 관리 기능을 위한 명령줄 인터페이스로 Microsoft Exchange Server 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="da565-110">Lync Server 2010부터는 Lync 및 Skype 서버를 포함하여 대부분의 Microsoft Server 제품에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="da565-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="da565-111">비즈니스용 Skype 서버 관리 셸에서 700개가 넘는 Lync 및 Skype 관련 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da565-112">비즈니스용 Skype cmdlet 참조가 docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="da565-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="da565-113">아래 링크를 클릭하면 새 웹 페이지로 docs.microsoft.com 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="da565-114">이제 콘텐츠가 원본으로 제공된 후 GitHub를 통해 커뮤니티 기여에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="da565-115">기여에 관심이 있나요?</span><span class="sxs-lookup"><span data-stu-id="da565-115">Interested in contributing?</span></span> <span data-ttu-id="da565-116">리포지타임에서 README를 확인한 후 다음을 확인할 수 있습니다. [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="da565-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="da565-117">비즈니스용 Skype 서버는 관리자가 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서버를 관리할 수 있도록 하는 700개가 넘는 cmdlet을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da565-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="da565-118">다음과 같은 명령을 입력하여 명령줄에서 직접 cmdlet에 대한 도움말을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="da565-119">위의 명령은 **New-CsVoicePolicy** cmdlet에 사용할 수 있는 전체 도움말을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="da565-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="da565-120">다른 cmdlet에 대한 도움말을 보기 위해 **New-CsVoicePolicy를** 도움말을 검색할 cmdlet 이름으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="da565-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="da565-121">비즈니스용 Skype 서버를 관리하는 데 사용할 수 있는 cmdlet의 전체 목록을 검색하기 위해 셸 명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="da565-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="da565-122">비즈니스용 Skype 서버에서 Windows PowerShell 알아야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="da565-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="da565-123">비즈니스용 Skype 서버 cmdlet을 실행하기 위해 비즈니스용 Skype 서버 관리 셸을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="da565-124">비즈니스용 Skype Windows PowerShell 창을 여는 경우 기본적으로 Skype cmdlet을 실행하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="da565-125">비즈니스용 Skype 서버 cmdlet을 Windows PowerShell 명령 프롬프트에 Windows PowerShell 입력합니다. >  `Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="da565-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="da565-126">비즈니스용 Skype 서버 관리 셸은 모든 비즈니스용 Skype 서버 Enterprise Edition 프런트 엔드 서버 또는 Standard Edition 서버에 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="da565-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="da565-127">[Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet을 실행하여 비즈니스용 Skype 서버 관리 셸 도움말 콘텐츠를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="da565-128">이 Update-Help cmdlet은 비즈니스용 Skype cmdlet에 대한 업데이트를 포함하여 컴퓨터에 설치된 모든 모듈에 사용할 수 있는 최신 도움말 파일을 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="da565-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="da565-129">기본적으로 **Update-Help** cmdlet은 비즈니스용 Skype 서버에 설치된 모든 모듈을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="da565-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="da565-130">특정 모듈만 업데이트하려는 경우 _Module_ 매개 변수를 사용하여 cmdlet의 범위를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="da565-131">다음 예제에서는 비즈니스용 Skype 모듈만 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="da565-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="da565-132">인터넷에 연결되지 않은 서버에서 도움말을 업데이트해야 하는 경우 [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet을 사용하여 도움말의 최신 버전을 다운로드하고 지정한 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="da565-133">그런 다음 인터넷에 연결되지 않은 서버에서 _-SourcePath_ 매개 변수와 함께 **Update-Help** cmdlet을 사용하여 선택한 위치에서 업데이트된 도움말을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="da565-134">다음 예제에서는 도움말 파일을 네트워크 파일 공유에 저장한 다음 파일 공유에서 비즈니스용 Skype 모듈에 대한 도움말을 업데이트하는 방법을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da565-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="da565-135">자세한 내용은 [Updatable 도움말을 참조하십시오.](https://technet.microsoft.com/library/hh847735.aspx)</span><span class="sxs-lookup"><span data-stu-id="da565-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="da565-136">PowerShell을 원격으로 사용하는 경우 방화벽을 통한 통신을 허용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da565-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="da565-137">PowerShell 리모팅에서 사용하는 포트에 대한 자세한 내용은 [PowerShell Remoting Use?를 참조하세요.](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)</span><span class="sxs-lookup"><span data-stu-id="da565-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

