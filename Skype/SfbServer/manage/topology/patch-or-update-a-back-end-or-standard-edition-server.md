---
title: 비즈니스용 Skype 서버에서 백 엔드 서버 또는 Standard Edition 서버 패치 또는 업데이트
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
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '요약: 비즈니스용 Skype 서버에서 백 엔드 서버에 업데이트 또는 패치를 설치하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826308"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="dd28e-103">비즈니스용 Skype 서버에서 백 엔드 서버 또는 Standard Edition 서버 패치 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="dd28e-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="dd28e-104">**요약:** 비즈니스용 Skype 서버에서 백 엔드 서버에 업데이트 또는 패치를 설치하는 방법을 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="dd28e-105">이 항목에서는 Enterprise Edition 백 엔드 서버 또는 Standard Edition 서버에 업데이트를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="dd28e-p101">업그레이드하는 동안 백 엔드 서버가 30분 이상 중단되는 경우에는 사용자가 복구 모드로 전환될 수 있습니다. 업그레이드가 완료되고 백 엔드 서버가 다시 풀의 프런트 엔드 서버에 연결되면 사용자가 전체 기능 모드로 복구됩니다. 업그레이드에 30분 미만이 걸리는 경우에는 사용자에게 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-p101">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode. When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality. If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="dd28e-109">백 엔드 서버 또는 Standard Edition 서버를 업데이트하는 경우</span><span class="sxs-lookup"><span data-stu-id="dd28e-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="dd28e-110">CsAdministrator 역할의 구성원으로 업그레이드할 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="dd28e-111">업데이트를 다운로드한 후 로컬 하드 디스크로 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="dd28e-112">비즈니스용 Skype 서버 관리 셸을 시작합니다. **시작,** **모든** 프로그램, 비즈니스용 **Skype,** 비즈니스용 **Skype** 서버 관리 셸을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="dd28e-113">비즈니스용 Skype 서버 서비스를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="dd28e-114">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="dd28e-115">World Wide Web 서비스를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="dd28e-116">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="dd28e-117">비즈니스용 Skype 서버 관리 셸 창을 모두 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="dd28e-118">업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-118">Install the update.</span></span>
    
8. <span data-ttu-id="dd28e-119">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd28e-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="dd28e-120">비즈니스용 Skype 서버 서비스를 다시 중지하여 GAC(전역 어셈블리 캐시) -d 어셈블리를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="dd28e-121">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="dd28e-122">World Wide Web 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-122">Restart the World Wide Web service.</span></span> <span data-ttu-id="dd28e-123">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-123">At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="dd28e-124">다음 중 하나를 수행하여 SQL Server 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="dd28e-125">이 서버가 Enterprise Edition 백 엔드 서버인 경우 보관 또는 모니터링 데이터베이스와 같이 이 서버에 함께 있는 데이터베이스가 없는 경우 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="dd28e-126">Enterprise Edition 백 엔드 서버가고 이 서버에 함께 있는 데이터베이스가 있는 경우 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="dd28e-127">Standard Edition 서버인 경우 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dd28e-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
