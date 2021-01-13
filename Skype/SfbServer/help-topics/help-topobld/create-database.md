---
title: 데이터베이스 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: 토폴로지 작성기에서는 데이터베이스를 저장소에 설치하는 SQL Server 있습니다. 토폴로지 작성기에서 데이터베이스를 설치할 때 응용 프로그램은 토폴로지의 정보를 읽은 다음 지정된 컴퓨터 또는 SQL Server 클러스터에 필요한 SQL Server 설치합니다. 이는 토폴로지 작성기를 사용하여 사용 가능한 유일한 데이터베이스 설치 유형입니다. 특정 컴퓨터에 특정 데이터베이스를 설치해야 하는 경우 또는 함께 사용 가능한 데이터베이스를 설치해야 하는 경우 명령줄 인터페이스와 Windows PowerShell cmdlet을 Install-CsDatabase 합니다.
ms.openlocfilehash: 0ba463ed2995aae2a31890633b7a959cf889837c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833088"
---
# <a name="create-database"></a><span data-ttu-id="02f52-106">데이터베이스 만들기</span><span class="sxs-lookup"><span data-stu-id="02f52-106">Create Database</span></span>
 
<span data-ttu-id="02f52-107">토폴로지 작성기에서는 저장소에 데이터베이스를 설치하는 SQL Server 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02f52-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="02f52-108">토폴로지 작성기에서 데이터베이스를 설치할 때 응용 프로그램은 토폴로지의 정보를 읽은 다음 지정된 컴퓨터 또는 SQL Server 클러스터에 SQL Server 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="02f52-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="02f52-109">이는 토폴로지 작성기를 사용하여 사용 가능한 유일한 데이터베이스 설치 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="02f52-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="02f52-110">특정 컴퓨터에 특정 데이터베이스를 설치해야 하는 경우 또는 함께 사용 가능한 데이터베이스를 설치해야 하는 경우 명령줄 인터페이스와 [Windows PowerShell-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet을 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02f52-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="02f52-111">데이터베이스 만들기</span><span class="sxs-lookup"><span data-stu-id="02f52-111">Creating a Database</span></span>

1. <span data-ttu-id="02f52-112">비즈니스용 Skype 서버 2015 노드를 클릭한 다음 데이터베이스 **설치를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="02f52-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="02f52-113">데이터베이스  설치 대화 상자의 데이터베이스  만들기 페이지에서 새 데이터베이스를 만들 SQL Server 저장소의 FQDN(정식 도메인 이름)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02f52-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="02f52-p103">**고급** 을 클릭합니다. **데이터베이스 파일 위치 선택** 대화 상자에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02f52-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="02f52-p104">**데이터베이스 파일 위치 자동 지정**. 이 옵션을 선택하는 경우 토폴로지 작성기에서 기본 제공 알고리즘을 사용하여 데이터베이스 로그 및 데이터 파일의 저장 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02f52-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="02f52-118">**SQL Server 인스턴스 기본값 사용**.</span><span class="sxs-lookup"><span data-stu-id="02f52-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="02f52-119">이 옵션을 선택하면 기본 제공 알고리즘을 사용하여 데이터베이스 로그 및 데이터 파일의 저장소 위치를 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02f52-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="02f52-120">대신 로그 및 데이터 파일은 SQL Server 기본값 경로로 지정된 위치에 저장됩니다(이러한 경로는 SQL Server 관리자가 고급에서 구성해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="02f52-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="02f52-121">데이터 파일은 기본 SQL Server 데이터 파일 위치에 저장되고 로그 파일은 기본 로그 파일 위치에 SQL Server 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="02f52-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="02f52-122">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="02f52-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="02f52-123">**데이터베이스 만들기** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="02f52-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="02f52-124">**데이터베이스 생성 완료** 페이지에서 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="02f52-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

