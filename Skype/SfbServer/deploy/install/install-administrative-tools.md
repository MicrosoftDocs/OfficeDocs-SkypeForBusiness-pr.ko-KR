---
title: 비즈니스용 Skype 서버에 관리 도구 설치
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: '요약: 비즈니스용 Skype 서버 설치에 필요한 관리 도구를 설치하는 방법을 설명하는 문서입니다. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 무료 평가판을 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 다운로드합니다.'
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812108"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="af872-104">비즈니스용 Skype 서버에 관리 도구 설치</span><span class="sxs-lookup"><span data-stu-id="af872-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="af872-105">**요약:** 비즈니스용 Skype 서버 설치에 필요한 관리 도구를 설치하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="af872-106">Microsoft 평가판 센터에서 비즈니스용 Skype 서버 무료 평가판을 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="af872-107">관리 도구에는 토폴로지 작성기 및 제어판이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="af872-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="af872-108">관리 도구는 토폴로지의 하나 이상의 서버에 설치하거나 비즈니스용 Skype 서버에 대해 지원되는 Windows OS 버전을 실행하는 64비트 관리 Workstation에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="af872-109">1~5단계는 순서에 따라 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af872-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="af872-110">그러나 다이어그램에 설명된대로 1~5단계를 순서대로, 6, 7, 8단계를 순서대로 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="af872-111">관리 도구를 설치하는 단계는 8단계 중 3단계입니다.</span><span class="sxs-lookup"><span data-stu-id="af872-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![개요 다이어그램](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="af872-113">비즈니스용 Skype 서버 관리 도구 설치</span><span class="sxs-lookup"><span data-stu-id="af872-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="af872-114">비즈니스용 Skype 서버의 설치 미디어는 유연한 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="af872-115">이 Setup.exe 설치되는 도구는 비즈니스용 Skype 서버 배포 마법사와 비즈니스용 Skype 서버 관리 셸뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="af872-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="af872-116">핵심 구성 요소라고 하는 이러한 두 도구를 사용하여 설치 프로세스를 계속할 수 있지만 전체 비즈니스용 Skype 서버 환경에 대한 기본 기능은 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af872-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="af872-117">핵심 구성 요소를 설치하면 배포 마법사가 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="af872-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="af872-118">배포 마법사의 제목이 "관리 도구 **설치"라는** 섹션에서는 비즈니스용 Skype 서버 토폴로지 작성기 및 비즈니스용 Skype 서버 제어판을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="af872-119">모든 비즈니스용 Skype 서버 환경에는 관리 도구가 설치된 서버가 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="af872-120">관리 도구 설치에 대한 **비디오 단계를 시청하세요.**</span><span class="sxs-lookup"><span data-stu-id="af872-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="af872-121">배포 마법사에서 비즈니스용 Skype 서버 관리 도구 설치</span><span class="sxs-lookup"><span data-stu-id="af872-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="af872-122">비즈니스용 Skype 서버 설치 미디어를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="af872-123">설치가 자동으로 시작되지 않는 경우 설치를 두 번 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="af872-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="af872-124">설치 미디어를 실행하려면 Microsoft Visual C++가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="af872-125">설치할지 묻는 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="af872-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="af872-126">**예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="af872-127">비즈니스용 Skype 서버의 새로운 기능인 스마트 설치를 사용하여 인터넷에 연결하여 설치 프로세스 중에 업데이트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af872-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="af872-128">이렇게 하면 설치 시 제품에 대한 최신 업데이트가 적용된 것이 더 나은 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="af872-129">**설치** 를 클릭하여 설치를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="af872-130">사용권 계약을 신중하게 검토하고, 동의하는 경우 사용권 계약 조건에 동의하는지 선택하고 **확인을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="af872-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="af872-131">비즈니스용 Skype 서버 핵심 구성 요소가 서버에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="af872-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="af872-132">핵심 구성 요소는 그림과 같이 다음으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="af872-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![앱의 핵심 구성 요소 화면.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="af872-134">**비즈니스용 Skype 서버 배포 마법사** 비즈니스용 Skype 서버의 다양한 구성 요소를 설치하기 위한 시작 패드를 제공하는 배포 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="af872-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="af872-135">**비즈니스용 Skype 서버 관리 셸** 비즈니스용 Skype 서버를 관리하기 위해 미리 구성한 PowerShell 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="af872-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="af872-136">핵심 구성 요소 설치가 완료되면 그림과 같이 비즈니스용 Skype 서버 배포 마법사가 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="af872-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![비즈니스용 Skype 서버 배포 마법사](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="af872-138">핵심 구성 요소 외에도 해당 환경의 하나 이상의 서버에 비즈니스용 Skype 서버 토폴로지 작성기 및 비즈니스용 Skype 서버 제어판을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="af872-139">배포 **마법사에서** 관리 도구 설치를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="af872-140">**다음** 을 클릭하여 설치를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="af872-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="af872-141">설치가 완료되면 **마쳤습니다.**</span><span class="sxs-lookup"><span data-stu-id="af872-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="af872-142">이제 그림과 같이 관리 도구가 서버에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="af872-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![비즈니스용 Skype 서버 관리 도구](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="af872-144">**비즈니스용 Skype 서버 토폴로지 작성기** 토폴로지 작성, 배포 및 관리에 사용되는 프로그램</span><span class="sxs-lookup"><span data-stu-id="af872-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="af872-145">**비즈니스용 Skype 서버 제어판** 설치를 관리하는 데 사용되는 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="af872-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

