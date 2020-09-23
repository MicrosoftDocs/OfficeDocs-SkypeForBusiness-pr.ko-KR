---
title: 데이터베이스 설치 옵션 페이지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: SQL Server에서 데이터베이스 및 로그 파일 배치에 대 한 고급 옵션을 구성 합니다. 다음과 같은 옵션을 사용할 수 있습니다.
ms.openlocfilehash: 4c8c456aa1fd0e9eee150e184b4d1f7934c26b65
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215309"
---
# <a name="install-database-options-page"></a><span data-ttu-id="d2345-104">데이터베이스 설치 옵션 페이지</span><span class="sxs-lookup"><span data-stu-id="d2345-104">Install Database Options Page</span></span>

<span data-ttu-id="d2345-105">SQL Server에서 데이터베이스 및 로그 파일 배치에 대 한 고급 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2345-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="d2345-106">다음과 같은 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2345-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2345-107">SQL Server 컴퓨터의 데이터 및 로그 파일 배치와 관련 된 요구 사항 및 정책에 가장 적합 한 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2345-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="d2345-108">**자동으로 데이터베이스 파일 위치 결정**: 기본 옵션은 SQL Server에서 사용 가능한 공간을 결정 하 고 최적의 성능을 위해 데이터베이스 및 로그 파일을 배포 하는 알고리즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2345-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="d2345-109">**Sql server 인스턴스 기본값 사용**: sql server의 인스턴스 설정에 따라 데이터베이스 파일 및 로그 파일을 배치 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2345-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="d2345-110">옵션은 보통 데이터베이스 관리자에 의해 관리 및 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2345-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="d2345-111">**대상 SQL server의 이러한 경로**: 데이터베이스 및 로그 파일을 저장할 드라이브 및 폴더에 대 한 전체 경로를 입력 하 여 sql server 데이터베이스 및 로그 파일에 대 한 자체 경로를 정의 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2345-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2345-112">입력하는 경로는 설치의 성능 최적화 알고리즘에 따라 수정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2345-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="d2345-113">자세한 내용은 [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2345-113">For details, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).</span></span>

 <span data-ttu-id="d2345-114">**확인**: 변경 내용을 커밋하려면 확인 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2345-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="d2345-115">**취소**: 변경 내용을 취소하고 데이터베이스 설치 화면으로 돌아가려면 취소를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2345-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="d2345-116">**도움말**: 이 도움말 페이지에 액세스하려면 도움말 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2345-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2345-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2345-117">See also</span></span>

[<span data-ttu-id="d2345-118">SQL Server 데이터 및 로그 파일 배치</span><span class="sxs-lookup"><span data-stu-id="d2345-118">SQL Server Data and Log File Placement</span></span>](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
