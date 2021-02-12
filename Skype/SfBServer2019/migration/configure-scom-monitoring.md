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
description: Microsoft 비즈니스용 Skype 서버 2019로 마이그레이션한 후 System Center Operations Manager에서 작동하도록 비즈니스용 Skype 서버 2019를 구성하기 위한 몇 가지 작업을 완료해야 합니다.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754048"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="055b8-103">SCOM 모니터링 구성</span><span class="sxs-lookup"><span data-stu-id="055b8-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="055b8-104">비즈니스용 Skype 서버 2019로 마이그레이션한 후 System Center Operations Manager에서 작동하도록 비즈니스용 Skype 서버 2019를 구성하기 위한 몇 가지 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="055b8-105">중앙 검색 논리를 관리하기 위해 선택된 서버에 업데이트를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="055b8-106">중앙 검색 후보 서버 레지스트리 키를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="055b8-107">후보 중앙 검색 노드를 다시 설정하도록 기본 System Center Operations Manager 관리 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="055b8-108">이러한 각 작업의 수행 지침은 아래에 제공되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="055b8-109">중앙 검색 논리를 관리하기 위해 선택된 서버에 업데이트를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="055b8-110">System Center Operations Manager 에이전트 파일을 설치하고 후보 검색 노드로 구성할 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="055b8-111">이 서버에 업데이트를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-111">Apply updates to this server.</span></span> <span data-ttu-id="055b8-112">업데이트 적용 [항목을 참조하세요.](apply-updates.md)</span><span class="sxs-lookup"><span data-stu-id="055b8-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="055b8-113">중앙 검색 후보 서버 레지스트리 키를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="055b8-114">중앙 검색 논리를 관리하기로 선택된 서버에서 명령 Windows PowerShell 를 습니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="055b8-115">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="055b8-p102">레지스트리를 편집할 때마다 레지스트리 키가 이미 있으면 명령이 실패했다는 오류가 발생할 수 있습니다. 이 문제가 발생할 경우 오류를 무시해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="055b8-118">후보 중앙 검색 감시자 노드를 다시 설정하도록 기본 System Center Operations Manager 관리 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="055b8-119">System Center Operations Manager 콘솔이 설치된 컴퓨터에서 **관리 팩 개체** 를 확장한 후 **개체 검색** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="055b8-120">범위 **변경 클릭**</span><span class="sxs-lookup"><span data-stu-id="055b8-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="055b8-121">**관리 팩 개체 범위 지정** 페이지에서 **LS 검색 후보** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="055b8-122">**LS 검색 후보 유효 값** 을 이전 절차에서 선택한 후보 서버의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="055b8-123">변경 내용을 마무리하려면 System Center Operations Manager 루트 관리 서버에서 상태 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="055b8-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

