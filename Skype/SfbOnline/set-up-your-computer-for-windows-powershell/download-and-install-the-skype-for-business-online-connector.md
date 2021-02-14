---
title: 비즈니스용 Skype Online Connector 모듈 다운로드 및 설치
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 비즈니스용 Skype Online 커넥터를 다운로드, 설치 및 사용하여 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다.
ms.openlocfilehash: 3928e77e5bac77dbfe89f7be5e762dd0d8ff93eb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814567"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="b603d-103">비즈니스용 Skype Online Connector 모듈 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="b603d-103">Download and install the Skype for Business Online Connector module</span></span>

> [!NOTE]
> <span data-ttu-id="b603d-104">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 공개 릴리스는 비즈니스용 Skype Online Connector와 통합되어 Teams PowerShell 관리를 위한 단일 모듈을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-104">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="b603d-105">비즈니스용 Skype Online 커넥터 모듈에는 비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있는 **New-CsOnlineSession** cmdlet이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-105">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="b603d-106">이 모듈은 64비트 컴퓨터에서만 지원됩니다(자세한 내용은 Windows PowerShell 사용하여 비즈니스용 [Skype Online](set-up-your-computer-for-windows-powershell.md) 관리용 컴퓨터 설정 참조) Microsoft 다운로드 센터에서 다운로드할 수 [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-106">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="b603d-107">SkypeOnlinePowershell.exe 파일을 다운로드한 후 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-107">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="b603d-108">파일SkypeOnlinePowershell.exe두 **번** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-108">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="b603d-109">비즈니스용 Skype Online의 Windows PowerShell 설정 마법사의 **Microsoft** 소프트웨어 사용 조건 페이지에서 사용권 계약의 조건에 동의한 다음 설치를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b603d-109">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="b603d-110">사용자 **계정 컨트롤 대화** 상자가 나타나면 [예]를 클릭하여 설치를 계속합니다. </span><span class="sxs-lookup"><span data-stu-id="b603d-110">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="b603d-111">비즈니스용 **Skype Online 완성,** Windows PowerShell 모듈 페이지에서 마쳤습니다. </span><span class="sxs-lookup"><span data-stu-id="b603d-111">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="b603d-112">설치 프로그램은 비즈니스용 Skype Online Connector 모듈(및 **New-CsOnlineSession** cmdlet)을 컴퓨터에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-112">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="b603d-113">모듈에 액세스하기 위해 관리자 Windows PowerShell 세션을 시작하고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-113">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="b603d-114">이 명령을 시작할 때마다 이 명령을 입력하지 Windows PowerShell 사용자 프로필에 명령을 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-114">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="b603d-115">이렇게 하여 다음 명령을 입력하고 Windows PowerShell Enter를 누르면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-115">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="b603d-116">메모장이 나타나면 프로필에 이미 있는 명령의 아래쪽에 다음 줄을 추가합니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="b603d-116">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="b603d-117">파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-117">Save the file.</span></span> <span data-ttu-id="b603d-118">다음에 시작할 Windows PowerShell 비즈니스용 Skype Online Connector 모듈을 자동으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-118">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="b603d-119">관리자 자격 증명으로 실행하지 않는 경우 오류 메시지가 표시되고 모듈이 Windows PowerShell 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-119">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="b603d-120">비즈니스용 Skype Online 커넥터 모듈을 설치하는 것 외에도 SkypeOnlinePowershell.exe 1) 비즈니스용 Skype Online에 대한 클라이언트 인증을 처리하는 데 사용되는 IDCRL(Identity Service 클라이언트 런타임 라이브러리)의 세 가지 추가 구성 요소도 설치합니다. 2) .NET Framework 4.5; 3) Microsoft Visual C++ 2012 재배포 패키지(x64) 패키지(버전 11.0.50727)</span><span class="sxs-lookup"><span data-stu-id="b603d-120">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="b603d-121">.NET Framework 4.5는 .NET 애플리케이션을 구축하고 실행하는 데 사용되는 인프라를 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b603d-121">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="b603d-122">Visual C++ 재배포 가능한 패키지는 Microsoft Visual Studio 2012가 설치되어 있지 않은 컴퓨터에 Visual C++ 런타임 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b603d-122">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="b603d-123">현재 컴퓨터에 설치된 커넥터 모듈의 버전 번호를 확인하려면 제어판을 열고 프로그램 및 기능을 연 다음 비즈니스용 **Skype Online,** Windows PowerShell 모듈의 버전 번호를 확인합니다. </span><span class="sxs-lookup"><span data-stu-id="b603d-123">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b603d-124">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b603d-124">Related topics</span></span>
[<span data-ttu-id="b603d-125">비즈니스용 Skype 온라인 관리를 위한 컴퓨터를 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b603d-125">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
