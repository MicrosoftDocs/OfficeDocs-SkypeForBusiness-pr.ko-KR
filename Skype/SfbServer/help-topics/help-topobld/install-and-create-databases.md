---
title: 데이터베이스 설치 및 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: 배포에 대해 만들려는 데이터베이스를 선택 합니다. 기본적으로 데이터베이스는 정의 된 사이트의 정의 된 SQL Server에서 만들어지고 데이터베이스를 배치 하는 SQL Server에 따라 데이터베이스 파일을 자동으로 배포 하 고 구성 합니다.
ms.openlocfilehash: cf3493932fc699751cb31e1ab6f76312195b4e0a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697213"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="5250a-104">데이터베이스 설치 및 만들기</span><span class="sxs-lookup"><span data-stu-id="5250a-104">Install and Create Databases</span></span>

<span data-ttu-id="5250a-105">배포에 대해 만들려는 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5250a-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="5250a-106">기본적으로 데이터베이스는 정의 된 사이트의 정의 된 SQL Server에서 만들어지고 데이터베이스를 배치 하는 SQL Server에 따라 데이터베이스 파일을 자동으로 배포 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5250a-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="5250a-107">**만들려는 데이터베이스를 선택**합니다. 배포 하 고 구성 하려는 데이터베이스의 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5250a-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="5250a-108">배포할 데이터베이스 중 하나 또는 모두의 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5250a-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="5250a-109">해당 데이터베이스를 배포 하는 인스턴스를 수용 하기 위해 SQL Server가 이미 인스턴스에 대해 구성 되어 있어야 하며 방화벽 포트를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5250a-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="5250a-110">자세한 내용은 [Lync server 용 SQL server 2013 미리 보기 구성을](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5250a-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="5250a-111">**고급**: sql server를 클릭 하 고 **고급** 단추를 클릭 하 여 sql server의 데이터베이스 파일 위치에 대 한 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5250a-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="5250a-112">고급 데이터베이스 파일 배치에 대 한 자세한 내용은 [Lync Server Management Shell을 사용 하 여 데이터베이스 설치](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5250a-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="5250a-113">**뒤로**:이 단추를 클릭 하면 이전 화면으로 돌아갑니다 (이 대화 상자에 표시 된 방법에 따라 항상 사용 가능 하지 않을 수도 있음).</span><span class="sxs-lookup"><span data-stu-id="5250a-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="5250a-114">**다음**:이 단추를 클릭 하면 현재 대화 상자에서 선택한 내용이 커밋되고 추가 정보를 구성 하는 다음 대화 상자로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5250a-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="5250a-115">**취소**:이 단추를 클릭 하면 구성이 종료 되 고 변경 내용이 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5250a-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="5250a-116">일부 구성 화면에서는 종료 하 고 변경 내용을 취소 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5250a-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="5250a-117">**예** 를 선택 하면 현재 구성이 닫히고 현재 구성이 닫히고 토폴로지 작성기로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="5250a-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="5250a-118">**아니요** 를 선택 하면 현재 구성 대화 상자로 돌아가고 구성을 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5250a-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="5250a-119">**도움말**: **도움말** 단추를 클릭 하면 현재 구성 대화 상자와 연결 된 도움말 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5250a-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


