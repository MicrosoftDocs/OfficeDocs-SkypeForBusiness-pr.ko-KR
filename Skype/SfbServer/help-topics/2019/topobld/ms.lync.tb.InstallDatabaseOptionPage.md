---
title: 데이터베이스 설치 옵션 페이지
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 데이터베이스 및 로그 파일 배치에 대한 고급 옵션을 구성할 수 SQL Server. 다음과 같은 옵션을 사용할 수 있습니다.
ms.openlocfilehash: 4b4323f2b0e953ff24a458a2f28f75f52d4f0149
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121646"
---
# <a name="install-database-options-page"></a><span data-ttu-id="7fa16-104">데이터베이스 설치 옵션 페이지</span><span class="sxs-lookup"><span data-stu-id="7fa16-104">Install Database Options Page</span></span>

<span data-ttu-id="7fa16-105">데이터베이스 및 로그 파일 배치에 대한 고급 옵션을 구성할 수 SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fa16-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="7fa16-106">다음과 같은 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa16-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7fa16-107">사용자 컴퓨터의 데이터 및 로그 파일 배치와 관련한 요구 사항 및 정책에 가장 적합한 SQL Server 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa16-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="7fa16-108">**데이터베이스 파일** 위치 자동 결정: 기본 옵션은 데이터베이스의 사용 가능한 공간을 결정하고 최적의 성능을 SQL Server 및 로그 파일을 배포하는 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa16-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="7fa16-109">**SQL Server 인스턴스 기본값** 사용: 인스턴스 설정에 따라 데이터베이스 파일 및 로그 파일을 SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fa16-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="7fa16-110">옵션은 보통 데이터베이스 관리자에 의해 관리 및 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fa16-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="7fa16-111">**대상** SQL Server 경로: 데이터베이스 및 로그 파일이 배치될 드라이브 및 폴더의 전체 경로를 입력하여 SQL Server 데이터베이스 및 로그 파일에 대한 경로를 정의하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa16-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7fa16-112">입력하는 경로는 설치의 성능 최적화 알고리즘에 따라 수정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa16-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="7fa16-113">자세한 내용은 [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7fa16-113">For details, see [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).</span></span>

 <span data-ttu-id="7fa16-114">**확인**: 변경 내용을 커밋하려면 확인 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa16-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="7fa16-115">**취소**: 변경 내용을 취소하고 데이터베이스 설치 화면으로 돌아가려면 취소를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa16-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="7fa16-116">**도움말**: 이 도움말 페이지에 액세스하려면 도움말 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa16-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fa16-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fa16-117">See also</span></span>

[<span data-ttu-id="7fa16-118">SQL Server 데이터 및 로그 파일 배치</span><span class="sxs-lookup"><span data-stu-id="7fa16-118">SQL Server Data and Log File Placement</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)