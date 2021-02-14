---
title: 비즈니스용 Skype 서버에서 AlwaysOn 가용성 그룹을 사용하여 데이터베이스 관리
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
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '요약: 기존 AlwaysOn 가용성 그룹에 비즈니스용 Skype 서버 데이터베이스를 더 추가하는 방법을 알아보고, 비즈니스용 Skype 서버에서 AlwaysOn 가용성 그룹의 일부인 백 엔드 서버를 패치하거나 업그레이드한 후 필요한 추가 단계에 대해 자세히 알아보십시오.'
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826368"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="2eb98-103">비즈니스용 Skype 서버에서 AlwaysOn 가용성 그룹을 사용하여 데이터베이스 관리</span><span class="sxs-lookup"><span data-stu-id="2eb98-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="2eb98-104">이 문서의 단계를 사용하여 비즈니스용 Skype 서버의 기존 AlwaysOn 가용성 그룹에 비즈니스용 Skype 서버 데이터베이스를 더 추가하고, 비즈니스용 Skype 서버에서 AlwaysOn 가용성 그룹의 일부인 백 엔드 서버를 패치하거나 업그레이드한 후 필요한 추가 단계에 대해 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="2eb98-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="2eb98-105">AlwaysOn 가용성 그룹에 데이터베이스 추가</span><span class="sxs-lookup"><span data-stu-id="2eb98-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="2eb98-106">이 SQL Server Management Studio AlwaysOn 가용성 그룹으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb98-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="2eb98-107">주 복제 데이터베이스로 장애 조치(fail over)합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb98-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="2eb98-108">토폴로지 작성기에서 AlwaysOn 가용성 그룹의 SQL Server FQDN을 해당 그룹의 기본 노드의 FQDN으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb98-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="2eb98-109">토폴로지 작성기 열기, 기존 배포에서 토폴로지 **다운로드를** 선택한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2eb98-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="2eb98-110">비즈니스용 Skype 서버를 확장하고, 토폴로지 및 SQL Server **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="2eb98-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="2eb98-111">새 AlwaysOn SQL 저장소를 마우스 오른쪽 단추로 클릭하고 속성 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2eb98-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="2eb98-112">페이지 아래쪽의 SQL Server **FQDN** 상자에 AlwaysOn 가용성 그룹의 기본 노드의 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb98-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="2eb98-113">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb98-113">Publish the topology.</span></span> <span data-ttu-id="2eb98-114">작업 **메뉴에서** **토폴로지** 및 게시를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2eb98-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="2eb98-115">그런 다음 확인 페이지에서 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2eb98-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="2eb98-116">이 SQL Server Management Studio 사용하여 AlwaysOn 가용성 그룹에 새 데이터베이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb98-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="2eb98-117">AlwaysOn 가용성 SQL Server 패치 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="2eb98-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="2eb98-118">AlwaysOn 가용성 그룹의 일부인 백 엔드 서버를 패치한 후 토폴로지 다시 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb98-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="2eb98-119">비즈니스용 Skype 서버 또는 서버에 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2eb98-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="2eb98-120">비즈니스용 Skype 관리 셸에서 다음 PowerShell 명령을 실행합니다(SQL AlwaysOn 데이터베이스에 변경 내용을 적용할 수 있는 권한이 있는 계정으로 로그인).</span><span class="sxs-lookup"><span data-stu-id="2eb98-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="2eb98-121">여기서 [sqlpool.contoso.com]는 AlwaysOn 가용성 그룹의 FQDN(FQDN)으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eb98-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
