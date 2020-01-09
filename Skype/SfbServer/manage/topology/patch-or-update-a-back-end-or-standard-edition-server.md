---
title: 비즈니스용 Skype 서버에서 백 엔드 서버 또는 Standard Edition 서버 패치 또는 업데이트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '요약: 비즈니스용 Skype 서버의 백 엔드 서버에 업데이트나 패치를 설치 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: a88224c508426d16217adb87693515314b03e40f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991503"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="c922a-103">비즈니스용 Skype 서버에서 백 엔드 서버 또는 Standard Edition 서버 패치 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="c922a-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="c922a-104">**요약:** 비즈니스용 Skype 서버의 백 엔드 서버에 업데이트나 패치를 설치 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="c922a-105">이 항목에서는 Enterprise Edition 백 엔드 서버 또는 Standard Edition 서버에 업데이트를 설치 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="c922a-106">업그레이드 하는 동안 백 엔드 서버가 최소 30 분 동안 중단 되 면 사용자가 복원 모드로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="c922a-107">업그레이드가 완료 되 고 백 엔드 서버가 풀의 프런트 엔드 서버와 다시 연결 되 면 사용자가 전체 기능으로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="c922a-108">업그레이드 시간이 30 분 미만이 되 면 사용자에 게 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="c922a-109">백 엔드 서버 또는 Standard Edition 서버를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="c922a-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="c922a-110">CsAdministrator 역할의 구성원으로 업그레이드 하는 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="c922a-111">업데이트를 다운로드 하 고 로컬 하드 디스크에 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="c922a-112">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype**를 차례로 클릭 한 다음 비즈니스용 **skype server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="c922a-113">비즈니스용 Skype 서버 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="c922a-114">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="c922a-115">World Wide Web 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="c922a-116">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="c922a-117">모든 비즈니스용 Skype 서버 관리 셸 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="c922a-118">업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-118">Install the update.</span></span>
    
8. <span data-ttu-id="c922a-119">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="c922a-120">비즈니스용 Skype Server 서비스를 중지 하 고 GAC (전역 어셈블리 캐시)-d 어셈블리를 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="c922a-121">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="c922a-122">World Wide Web 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-122">Restart the World Wide Web service.</span></span> <span data-ttu-id="c922a-123">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-123">At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="c922a-124">다음 중 하나를 수행 하 여 SQL Server 데이터베이스에 대 한 변경 내용을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="c922a-125">Enterprise Edition 백 엔드 서버이 고 데이터베이스 보관 또는 모니터링 등의 collocated 데이터베이스가 없는 경우 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="c922a-126">Enterprise Edition 백 엔드 서버이 고이 서버에 collocated 데이터베이스가 있는 경우 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="c922a-127">스탠더드 버전 서버인 경우 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c922a-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
