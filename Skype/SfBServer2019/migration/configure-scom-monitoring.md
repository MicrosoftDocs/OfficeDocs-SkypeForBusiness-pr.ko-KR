---
title: SCOM 모니터링 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Microsoft 비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 System Center Operations Manager에서 작동 하도록 비즈니스용 Skype 서버 2019을 구성 하기 위한 몇 가지 작업을 완료 해야 합니다.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754048"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="a2890-103">SCOM 모니터링 구성</span><span class="sxs-lookup"><span data-stu-id="a2890-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="a2890-104">비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 몇 가지 작업을 완료 하 여 비즈니스용 Skype 서버 2019에서 System Center Operations Manager와 함께 작동 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="a2890-105">중앙 검색 논리를 관리 하도록 선택한 서버에 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="a2890-106">중앙 검색 후보 서버 레지스트리 키를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="a2890-107">기본 System Center Operations Manager 관리 서버를 구성 하 여 후보 중앙 검색 노드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="a2890-108">이러한 각 작업의 수행 지침은 아래에 제공되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="a2890-109">중앙 검색 논리를 관리 하도록 선택한 서버에 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="a2890-110">System Center Operations Manager 에이전트 파일을 설치하고 후보 검색 노드로 구성할 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="a2890-111">이 서버에 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-111">Apply updates to this server.</span></span> <span data-ttu-id="a2890-112">[Apply updates](apply-updates.md)항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a2890-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="a2890-113">중앙 검색 후보 서버 레지스트리 키를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="a2890-114">중앙 검색 논리를 관리 하도록 선택한 서버에서 Windows PowerShell 명령 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="a2890-115">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="a2890-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span><span class="sxs-lookup"><span data-stu-id="a2890-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="a2890-117">If you experience this, you can safely ignore the error.</span><span class="sxs-lookup"><span data-stu-id="a2890-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="a2890-118">기본 System Center Operations Manager 관리 서버를 구성 하 여 후보 중앙 검색 감시자 노드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="a2890-119">System Center Operations Manager 콘솔이 설치된 컴퓨터에서 **관리 팩 개체**를 확장한 후 **개체 검색**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="a2890-120">**범위 변경을** 클릭</span><span class="sxs-lookup"><span data-stu-id="a2890-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="a2890-121">**관리 팩 개체 범위 지정** 페이지에서 **LS 검색 후보**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="a2890-122">**LS 검색 후보 유효 값**을 이전 절차에서 선택한 후보 서버의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="a2890-123">변경 내용을 마무리 하려면 System Center Operations Manager 루트 관리 서버에서 상태 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2890-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

