---
title: 데이터베이스 설치 및 만들기
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
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: 배포용으로 만들 데이터베이스를 선택합니다. 기본적으로 데이터베이스는 정의된 사이트의 정의된 SQL Server 만들어지며 데이터베이스를 배치하는 SQL Server 따라 데이터베이스 파일을 자동으로 배포 및 구성합니다.
ms.openlocfilehash: 36912e468b0618925b3fbeb20db829d8d19249fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806938"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="2af7d-104">데이터베이스 설치 및 만들기</span><span class="sxs-lookup"><span data-stu-id="2af7d-104">Install and Create Databases</span></span>

<span data-ttu-id="2af7d-105">배포용으로 만들 데이터베이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2af7d-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="2af7d-106">기본적으로 데이터베이스는 정의된 사이트의 정의된 SQL Server 만들어지며 데이터베이스를 배치하는 SQL Server 따라 데이터베이스 파일을 자동으로 배포 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2af7d-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="2af7d-p103">**만들려는 데이터베이스 선택**: 배포 및 구성하려는 데이터베이스의 확인란을 선택합니다. 배포하려는 임의의 데이터베이스 또는 모든 데이터베이스 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2af7d-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="2af7d-109">데이터베이스를 SQL Server 인스턴스에 대해 구성한 경우 방화벽 포트를 열고 데이터베이스를 배포하는 인스턴스를 수용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af7d-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="2af7d-110">자세한 내용은 [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2af7d-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="2af7d-111">**Advanced**: click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2af7d-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="2af7d-112">고급 데이터베이스 파일 배치에 대한 자세한 내용은 [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2af7d-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="2af7d-113">**뒤로**: 이 단추를 클릭하면 이전 화면으로 돌아갑니다(이 대화 상자를 표시한 방법에 따라 항상 활성화되지는 않을 수도 있음).</span><span class="sxs-lookup"><span data-stu-id="2af7d-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="2af7d-114">**다음**: 이 단추를 클릭하면 현재 대화 상자의 선택 내용이 커밋되고 추가 정보 구성을 위해 다음 대화 상자로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2af7d-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="2af7d-115">**취소**: 이 단추를 클릭하면 구성이 종료되고 변경 내용이 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af7d-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="2af7d-116">일부 구성 화면(모두는 아님)에서는 구성을 종료하고 변경 내용을 취소할지를 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af7d-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="2af7d-117">예를 **선택하면** 현재 구성이 닫히고 현재 구성이 닫히고 토폴로지 작성기로 돌아오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af7d-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="2af7d-118">**아니요** 를 선택하면 현재 구성 대화 상자로 돌아가며 구성을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2af7d-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="2af7d-119">**도움말**: **도움말** 단추를 클릭하면 현재 구성 대화 상자와 연결된 이 도움말 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af7d-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


