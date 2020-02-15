---
title: 비즈니스용 Skype 서버에 대 한 필수 구성 요소 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '요약: 비즈니스용 Skype 서버를 설치 하기 전에 구성 해야 하는 서버 및 서버 역할에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 하세요. https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server'
ms.openlocfilehash: fedcebe601d21f0e581795c264ed26c6e90716bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018259"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="73df3-104">비즈니스용 Skype 서버에 대 한 필수 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="73df3-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="73df3-105">**요약:** 비즈니스용 Skype 서버를 설치 하기 전에 구성 해야 하는 서버 및 서버 역할에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="73df3-106">[Microsoft 평가 센터](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="73df3-107">필수 구성 요소 설치는 토폴로지의 각 서버에 필요한 역할과 기능을 설치 하 여 Windows Server를 설정 하는 것으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="73df3-108">요구 사항은 서버가 토폴로지에서 수행 하는 역할을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="73df3-109">순서에 관계 없이 1 ~ 5 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="73df3-110">그러나 다이어그램에 나와 있는 것 처럼, 1 ~ 5 단계를 순서 대로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="73df3-111">필수 구성 요소를 설치 하는 과정은 1-8 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-111">Installing prerequisites is step 1 of 8.</span></span>
  
![개요 다이어그램-필수 구성 요소 설치](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="73df3-113">Windows Server 설정</span><span class="sxs-lookup"><span data-stu-id="73df3-113">Setup Windows Server</span></span>

<span data-ttu-id="73df3-114">비즈니스용 Skype 서버에는 Windows Server 운영 체제와 설치 해야 하는 필수 구성 요소가 몇 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="73df3-115">필수 구성 요소 계획에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 서버 요구 사항](../../../SfBServer2019/plan/system-requirements.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73df3-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="73df3-116">이 절차에서는 Windows Server 2012 R2를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="73df3-117">다른 버전의 Windows Server를 사용 하는 경우에는 프로시저가 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="73df3-118">시작 하기 전에 windows Update를 사용 하 여 Windows Server가 최신 상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server가 최신 버전입니다.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="73df3-120">**설치 필수 구성 요소**에 대 한 비디오 단계를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="73df3-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="73df3-121">프런트 엔드 서버에 필요한 역할 및 기능 설치</span><span class="sxs-lookup"><span data-stu-id="73df3-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="73df3-122">서버 관리자를 사용 하 여 필요한 역할 및 기능을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="73df3-123">[비즈니스용 Skype 서버에 대 한 서버 요구 사항](../../../SfBServer2019/plan/system-requirements.md)에 나열 된 필수 구성 요소 소프트웨어 기능을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="73df3-124">필요한 소프트웨어가 비즈니스용 Skype 서버를 실행할 서버에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="73df3-125">Windows Server 2012 R2에서는 기본적으로 필요한 기능에 대 한 모든 원본 파일을 설치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="73df3-126">서버가 인터넷에 연결 되어 있지 않은 경우에는 Windows Server 2012 R2 미디어를 삽입 하 고 **대체 원본 경로 지정** 을 선택 해야 필요한 기능을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="73df3-127">원본 파일은 sources\sxs 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="73df3-128">예를 들어 Windows Server 2012 R2 미디어가 D 드라이브에 있는 경우에 대 한 경로를로 `d:\sources\sxs`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="73df3-129">Windows Update에서 최신 업데이트를 포함 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="73df3-130">인터넷에 연결 되어 있지 않은 경우 필수 업데이트에 필수 구성 요소와 함께 모든 관련 업데이트를 수동으로 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="73df3-131">이 대화 상자에 설치가 완료 되었음을 나타내는 경우에는 서버를 다시 부팅 하 여 프로세스를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="73df3-132">**Windows Update** 를 다시 실행 하 여 설치 된 역할 및 서비스에 대 한 업데이트가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="73df3-133">이 서버에서 비즈니스용 Skype 서버 제어판을 사용 하려는 경우에는 Silverlight도 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="73df3-134">Silverlight를 설치 하려면 [Microsoft silverlight](https://www.microsoft.com/silverlight/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73df3-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="73df3-135">프런트 엔드 서버 이외의 역할을 수행 하는 서버 (예: 디렉터, 영구 채팅 또는 Edge의 역할)에 대 한 필수 구성 요소는 고유한 필수 구성 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="73df3-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="73df3-136">각 서버 유형에 필요한 정확한 필수 구성 요소에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 서버 요구 사항을](../../../SfBServer2019/plan/system-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73df3-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

