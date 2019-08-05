---
title: 비즈니스용 Skype 서버에서 AlwaysOn 가용성 그룹을 사용 하 여 데이터베이스 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '요약: 기존 AlwaysOn 가용성 그룹에 비즈니스용 Skype 서버 데이터베이스를 추가 하는 방법에 대해 알아보고, Skype에서 AlwaysOn 가용성 그룹의 일부인 백 엔드 서버를 패치 또는 업그레이드 한 후 필요한 추가 단계에 대해 알아보세요. 비즈니스 서버.'
ms.openlocfilehash: c6d8877448a68aa2331f3c290170418f6dca08ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187107"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="12978-103">비즈니스용 Skype 서버에서 AlwaysOn 가용성 그룹을 사용 하 여 데이터베이스 관리</span><span class="sxs-lookup"><span data-stu-id="12978-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="12978-104">비즈니스용 Skype Server의 기존 AlwaysOn 가용성 그룹에 비즈니스용 Skype 서버 데이터베이스를 추가 하 고 AlwaysOn의 일부인 백 엔드 서버를 패치 또는 업그레이드 한 후 필요한 추가 단계에 대 한 자세한 내용을 보려면이 문서의 단계를 사용 합니다. 비즈니스용 Skype 서버의 가용성 그룹.</span><span class="sxs-lookup"><span data-stu-id="12978-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="12978-105">AlwaysOn 가용성 그룹에 데이터베이스 추가</span><span class="sxs-lookup"><span data-stu-id="12978-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="12978-106">SQL Server Management Studio를 열고 AlwaysOn 가용성 그룹으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="12978-107">주 복제본으로 장애 조치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="12978-108">토폴로지 작성기에서 AlwaysOn 가용성 그룹의 SQL Server FQDN을 해당 그룹의 주 노드의 FQDN으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="12978-109">토폴로지 작성기를 열고 **기존 배포에서 토폴로지 다운로드**를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="12978-110">비즈니스용 Skype 서버를 확장 하 고, 토폴로지를 확장 하 고, **SQL Server 스토어**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="12978-111">새 AlwaysOn 가용성 그룹의 SQL 저장소를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="12978-112">페이지의 맨 아래에 있는 **SQL SERVER FQDN** 상자에 AlwaysOn 가용성 그룹의 기본 노드에 대 한 FQDN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="12978-113">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-113">Publish the topology.</span></span> <span data-ttu-id="12978-114">**작업** 메뉴에서 **토폴로지** , **게시**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="12978-115">확인 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="12978-116">SQL Server Management Studio를 사용 하 여 AlwaysOn 가용성 그룹에 새 데이터베이스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="12978-117">AlwaysOn 가용성 그룹에서 SQL Server 패치 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="12978-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="12978-118">AlwaysOn 가용성 그룹의 일부인 백 엔드 서버를 패치 한 후에는 토폴로지를 다시 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="12978-119">비즈니스용 Skype 서버 또는 서버에 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="12978-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="12978-120">다음과 같이 비즈니스용 Skype 관리 셸에서 다음 PowerShell 명령을 실행 합니다 (SQL AlwaysOn 데이터베이스에 변경 내용을 적용 하도록 적절 하 게 permissioned 된 계정으로 로그인).</span><span class="sxs-lookup"><span data-stu-id="12978-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="12978-121">여기서 [sqlpool.contoso.com]는 AlwaysOn 가용성 그룹의 FQDN (정규화 된 도메인 이름)으로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12978-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
