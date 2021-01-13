---
title: SQL 저장소 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: 데이터베이스 데이터베이스의 속성을 SQL Server 데이터베이스 인스턴스를 SQL Server 합니다. 속성 편집 대화 상자를 사용하여 컴퓨터 간에 보관 서버 데이터베이스를 이동하는 등의 작업을 수행할 수는 없습니다. 또한 속성 편집 대화 상자를 사용하여 중앙 관리 저장소를 호스팅하는 SQL Server 인스턴스를 변경할 수 없습니다.
ms.openlocfilehash: d6601349afcc458fc4ba8c3f4feb8810a9c71c42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818098"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="2ebdd-105">SQL 저장소 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="2ebdd-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="2ebdd-106">데이터베이스 데이터베이스의 속성을 SQL Server 데이터베이스 인스턴스를 SQL Server 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ebdd-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="2ebdd-107">**속성 편집** 대화 상자를 사용하여 컴퓨터 간에 보관 서버 데이터베이스를 이동하는 등의 작업을 수행할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ebdd-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="2ebdd-108">또한 속성 편집 대화  상자를 사용하여 중앙 관리 저장소를 호스팅하는 SQL Server 인스턴스를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ebdd-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="2ebdd-109">데이터베이스의 속성 SQL Server 편집</span><span class="sxs-lookup"><span data-stu-id="2ebdd-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="2ebdd-110">중앙 관리 저장소가 SQL Server 데이터베이스 인스턴스를 변경하려면 토폴로지 작성기에서 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="2ebdd-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="2ebdd-111">인스턴스를 수정하려면 SQL Server</span><span class="sxs-lookup"><span data-stu-id="2ebdd-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="2ebdd-112">**SQL 저장소** 노드 아래에서 적절한 데이터베이스를 선택한 다음 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2ebdd-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="2ebdd-113">**속성 편집** 대화 상자에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2ebdd-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="2ebdd-114">기본 인스턴스를 SQL Server 기본 인스턴스를 선택하고 확인을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="2ebdd-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="2ebdd-115">명명된 데이터베이스 인스턴스를 사용하려면 **명명된 인스턴스** 를 선택하고 텍스트 상자에 인스턴스 이름을 입력한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2ebdd-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="2ebdd-116">전체 인스턴스 경로가 아닌 인스턴스 이름(예: ArchivingInstance)만 SQL Server 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ebdd-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="2ebdd-117">속성 편집 대화  상자에서 작업하는 경우 토폴로지 작성기에서 입력한 데이터베이스 인스턴스가 유효한 인스턴스가 아닌지 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ebdd-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="2ebdd-118">예를 들어 잘못 인스턴스 이름으로ArchivingInstanec를 입력한 다음 확인을 클릭하면 토폴로지 작성기에서 해당 잘못된 인스턴스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ebdd-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="2ebdd-119">이 토폴로지 게시를 위해 먼저 이 실수를 수정해야 합니다. SQL Server 인스턴스를 찾을 수 없는 경우 토폴로지 작성기에서 해당 인스턴스를 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ebdd-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

