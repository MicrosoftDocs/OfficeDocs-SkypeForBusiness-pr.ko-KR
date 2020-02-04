---
title: SQL 저장소 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: SQL Server 데이터베이스의 속성을 편집 하려면 SQL Server 데이터베이스 인스턴스를 변경 해야 합니다. 속성 편집 대화 상자를 사용 하 여 보관 서버 데이터베이스를 한 컴퓨터에서 다른 컴퓨터로 이동 하는 등의 작업을 수행할 수는 없습니다. 또한 속성 편집 대화 상자를 사용 하 여 중앙 관리 저장소를 호스트 하는 SQL Server 인스턴스를 변경할 수 없습니다.
ms.openlocfilehash: 2d9f03f7aed8aecc591a3f7c9177b5286fb3772b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684351"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="47d9d-105">SQL 저장소 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="47d9d-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="47d9d-106">SQL Server 데이터베이스의 속성을 편집 하려면 SQL Server 데이터베이스 인스턴스를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d9d-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="47d9d-107">**속성 편집** 대화 상자를 사용 하 여 보관 서버 데이터베이스를 한 컴퓨터에서 다른 컴퓨터로 이동 하는 등의 작업을 수행할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47d9d-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="47d9d-108">또한 **속성 편집** 대화 상자를 사용 하 여 중앙 관리 저장소를 호스트 하는 SQL Server 인스턴스를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47d9d-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="47d9d-109">SQL Server 데이터베이스의 속성 편집</span><span class="sxs-lookup"><span data-stu-id="47d9d-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="47d9d-110">중앙 관리 저장소 이외의 다른 데이터베이스에서 사용 하는 SQL Server 인스턴스를 변경 하려면 토폴로지 작성기에서 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d9d-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="47d9d-111">SQL Server 인스턴스를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="47d9d-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="47d9d-112">**SQL 저장소** 노드에서 해당 데이터베이스를 선택한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d9d-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="47d9d-113">**속성 편집** 대화 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d9d-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="47d9d-114">기본 SQL Server 인스턴스를 사용 하려면 **기본 인스턴스** 를 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d9d-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="47d9d-115">명명 된 데이터베이스 인스턴스를 사용 하려면 **명명 된 인스턴스**를 선택 하 고 텍스트 상자에 인스턴스 이름을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d9d-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="47d9d-116">전체 SQL Server 경로가 아닌 인스턴스 이름 (예: ArchivingInstance)만 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d9d-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="47d9d-117">**속성 편집** 대화 상자에서 작업 하는 경우 토폴로지 작성기는 입력 한 데이터베이스 인스턴스가 유효한 인스턴스인지 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47d9d-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="47d9d-118">예를 들어 실수로 인스턴스 이름을 typeArchivingInstanec **확인**을 클릭 하면 토폴로지 작성기에서 해당 잘못 된 인스턴스를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d9d-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="47d9d-119">이 토폴로지를 게시 하기 전에이 오류를 수정 해야 합니다. SQL Server 인스턴스를 찾을 수 없는 경우에는 토폴로지 작성기가 해당 인스턴스를 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47d9d-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

