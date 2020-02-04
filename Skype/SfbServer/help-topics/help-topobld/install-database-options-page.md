---
title: 데이터베이스 옵션 페이지 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: SQL Server에서 데이터베이스 및 로그 파일의 배치에 대 한 고급 옵션을 구성 합니다. 사용할 수 있는 옵션은 다음과 같습니다.
ms.openlocfilehash: 0abcf0be4c6e7a4d808a7abaaad713c1b35cd37e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697203"
---
# <a name="install-database-options-page"></a><span data-ttu-id="a053a-104">데이터베이스 옵션 페이지 설치</span><span class="sxs-lookup"><span data-stu-id="a053a-104">Install Database Options Page</span></span>

<span data-ttu-id="a053a-105">SQL Server에서 데이터베이스 및 로그 파일의 배치에 대 한 고급 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a053a-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="a053a-106">사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a053a-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a053a-107">SQL Server 컴퓨터의 데이터 및 로그 파일 배치와 관련 된 요구 사항 및 정책에 가장 적합 한 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a053a-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="a053a-108">**자동으로 데이터베이스 파일 위치 결정**: 기본 옵션은 SQL Server에서 사용 가능한 공간을 결정 하 고 최적의 성능을 위해 데이터베이스 및 로그 파일을 배포 하는 알고리즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a053a-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="a053a-109">**Sql server 인스턴스 기본값 사용**: sql server의 인스턴스 설정에 따라 데이터베이스 파일 및 로그 파일을 배치 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a053a-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="a053a-110">옵션은 일반적으로 데이터베이스 관리자가 관리 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a053a-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="a053a-111">**대상 SQL server의 이러한 경로**: 데이터베이스 및 로그 파일을 배치할 드라이브 및 폴더의 전체 경로를 입력 하 여 SQL Server 데이터베이스 및 로그 파일에 대 한 고유한 경로를 정의 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a053a-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a053a-112">입력 하는 경로는 설치의 성능 최적화 알고리즘에 따라 수정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a053a-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="a053a-113">자세한 내용은 [Lync Server Management Shell을 사용 하 여 데이터베이스 설치](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a053a-113">For details, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).</span></span>

 <span data-ttu-id="a053a-114">**확인**: 변경 내용을 커밋하려면 확인 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a053a-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="a053a-115">**취소**: 변경 내용을 취소 하 고 데이터베이스 설치 화면으로 돌아가려면 취소를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a053a-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="a053a-116">**도움말:이**도움말 페이지에 액세스 하려면 도움말 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a053a-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="a053a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a053a-117">See also</span></span>

[<span data-ttu-id="a053a-118">SQL Server 데이터 및 로그 파일 배치</span><span class="sxs-lookup"><span data-stu-id="a053a-118">SQL Server Data and Log File Placement</span></span>](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
