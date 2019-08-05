---
title: 비즈니스용 Skype 서버에 관리 도구 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: '요약: 비즈니스용 Skype 서버 설치에 필요한 관리 도구를 설치 하는 방법에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server하세요.'
ms.openlocfilehash: b700180a18cf7fcac3cb0353ff302edd1ed78584
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197737"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="3e43d-104">비즈니스용 Skype 서버에 관리 도구 설치</span><span class="sxs-lookup"><span data-stu-id="3e43d-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="3e43d-105">**요약:** 비즈니스용 Skype 서버 설치에 필요한 관리 도구를 설치 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="3e43d-106">Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)하세요.</span><span class="sxs-lookup"><span data-stu-id="3e43d-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="3e43d-107">관리 도구에는 토폴로지 작성기와 제어판이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="3e43d-108">관리 도구는 토폴로지의 하나 이상의 서버에 설치 되어 있거나 비즈니스용 Skype Server에 대해 지원 되는 Windows OS 버전을 실행 하는 64 비트 관리 워크스테이션에도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="3e43d-109">1 ~ 5 단계는 순서에 관계 없이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="3e43d-110">그러나 6, 7, 8 단계를 순서 대로 수행 하 고 다이어그램에 명시 된 대로 1 ~ 5 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="3e43d-111">관리 도구 설치 방법은 8 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![개요 다이어그램](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="3e43d-113">비즈니스용 Skype 서버 관리 도구 설치</span><span class="sxs-lookup"><span data-stu-id="3e43d-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="3e43d-114">비즈니스용 Skype Server의 설치 미디어는 유연한 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="3e43d-115">처음 setup.exe를 실행할 때는 비즈니스용 Skype 서버 배포 마법사와 비즈니스용 Skype 서버 관리 셸이 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="3e43d-116">핵심 구성 요소 라는 두 도구를 사용 하 여 설치 프로세스를 계속할 수 있지만, 전체 비즈니스용 Skype Server 환경에 대 한 기본 기능을 제공 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="3e43d-117">핵심 구성 요소를 설치한 후 배포 마법사가 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="3e43d-118">**관리 도구 설치** 라는 배포 마법사의 섹션에서는 비즈니스용 Skype 서버 토폴로지 작성기와 비즈니스용 Skype 서버 제어판을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3e43d-119">모든 Skype for Business Server 환경에는 관리 도구가 설치 된 서버가 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="3e43d-120">**관리 도구 설치**의 비디오 단계를 시청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="3e43d-121">배포 마법사에서 비즈니스용 Skype 서버 관리 도구 설치</span><span class="sxs-lookup"><span data-stu-id="3e43d-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="3e43d-122">비즈니스용 Skype 서버 설치 미디어를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="3e43d-123">설치 프로그램이 자동으로 시작 되지 않으면 **설정을**두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="3e43d-124">설치 미디어를 실행 하려면 Microsoft Visual c + +가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="3e43d-125">설치 여부를 묻는 대화 상자가 팝업 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="3e43d-126">**예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="3e43d-127">비즈니스용 Skype Server의 새로운 기능인 스마트 설정을 사용 하 여 설치 프로세스 중에 인터넷에 연결 하 여 업데이트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="3e43d-128">이렇게 하면 설치 시 제품에 대 한 최신 업데이트가 있는지 확인 하 여 더 나은 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="3e43d-129">설치 \*\*\*\* 를 클릭 하 여 설치를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="3e43d-130">사용권 계약을 신중 하 게 검토 하 고 동의할 경우 **사용권 계약에 동의 함을**선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="3e43d-131">비즈니스용 Skype Server Core 구성 요소가 서버에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="3e43d-132">핵심 구성 요소는 그림에 표시 된 대로 다음과 같이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![앱 화면의 핵심 구성 요소.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="3e43d-134">**비즈니스용 Skype 서버 배포 마법사** 비즈니스용 Skype 서버의 다양 한 구성 요소를 설치 하기 위한 시작 패드를 제공 하는 배포 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="3e43d-135">**비즈니스용 Skype 서버 관리 셸** 비즈니스용 Skype 서버 관리를 가능 하 게 하는 미리 구성 된 PowerShell 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="3e43d-136">핵심 구성 요소의 설치가 완료 되 면 그림에 표시 된 대로 비즈니스용 Skype 서버 배포 마법사가 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![비즈니스용 Skype 서버 배포 마법사](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="3e43d-138">핵심 구성 요소 외에도, 환경에서 하나 이상의 서버에 비즈니스용 Skype 서버 토폴로지 작성기 및 비즈니스용 Skype Server 제어판을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="3e43d-139">배포 마법사에서 **관리 도구 설치** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="3e43d-140">**다음** 을 클릭 하 여 설치를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="3e43d-141">설치가 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="3e43d-142">이제 그림과 같이 관리 도구가 서버에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![비즈니스용 Skype 서버 관리 도구](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="3e43d-144">**비즈니스용 Skype 서버 토폴로지 작성기** 토폴로지를 빌드, 배포 및 관리 하는 데 사용 되는 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="3e43d-145">**비즈니스용 Skype Server 제어판** 설치를 관리 하는 데 사용 되는 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="3e43d-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

