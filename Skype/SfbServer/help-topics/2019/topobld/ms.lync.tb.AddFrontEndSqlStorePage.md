---
title: 프런트 엔드 SQL Server 스토어 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: 표준 버전 서버 배포는 필요한 Microsoft SQL Server Express 데이터베이스 소프트웨어 및 SQL Server 데이터베이스를 자동으로 설치 합니다. 따라서 모든 옵션이 미리 채워져 있으며 기본 구성을 변경할 수 없습니다.
ms.openlocfilehash: 589870007c2a9dea187038e7a4197b16aad25578
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196925"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="66dbc-104">프런트 엔드 SQL Server 스토어 추가</span><span class="sxs-lookup"><span data-stu-id="66dbc-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="66dbc-105">표준 버전 서버 배포는 필요한 Microsoft SQL Server Express 데이터베이스 소프트웨어 및 SQL Server 데이터베이스를 자동으로 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="66dbc-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="66dbc-106">따라서 모든 옵션이 미리 채워져 있으며 기본 구성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66dbc-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="66dbc-107">Enterprise Edition server 배포의 프런트 엔드 풀에는 백 엔드 데이터베이스용으로 지원 되는 64 비트 버전의 SQL Server 데이터베이스 소프트웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="66dbc-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="66dbc-108">이전에 정의 된 SQL Server 데이터베이스를 백 엔드 데이터베이스에 사용할 수 있도록 선택 하거나, SQL Server 데이터베이스가 상주할 서버의 정규화 된 도메인 이름 (FQDN)을 지정 하 여 새 SQL Server 데이터베이스를 정의 하 고, SQL S 인스턴스를 새 SQL Server 데이터베이스 (기본 인스턴스 또는 지정한 명명 된 인스턴스)에 사용 하려는 erver입니다.</span><span class="sxs-lookup"><span data-stu-id="66dbc-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="66dbc-109">SQL Server store에서 미러링을 사용할 수 있도록 선택 하 고 자동 장애 조치에 미러링 미러링 모니터 서버를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66dbc-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="66dbc-110">SQL Server 지원에 대 한 자세한 내용은 지원 가능성 설명서의 [데이터베이스 소프트웨어 및 클러스터링 지원을](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66dbc-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="66dbc-111">백 엔드 데이터베이스용 SQL Server를 설정 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Sql Server 구성을](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66dbc-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="66dbc-112">토폴로지를 게시 하는 데 사용 되는 계정에 적절 한 사용자 권한 및 사용 권한이 있는 경우 토폴로지를 게시할 때 백 엔드 데이터베이스 (RTC (실시간 통신))를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66dbc-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="66dbc-113">나중에 설치 절차의 일부로 포함 하 여 데이터베이스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66dbc-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="66dbc-114">Enterprise Edition 배포용 SQL Server 기반 서버에 데이터베이스를 설치 하 고 배포 하려면 데이터베이스 파일을 설치 하는 SQL Server 기반 서버에 대 한 SQL Server sysadmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66dbc-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="66dbc-115">SQL Server sysadmins 그룹의 구성원이 아닌 경우 데이터베이스 파일을 배포할 때까지 그룹에 추가 하도록 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66dbc-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="66dbc-116">Sysadmins 그룹의 구성원을 만들 수 없는 경우에는 데이터베이스를 구성 하 고 배포 하는 스크립트를 사용 하 여 SQL Server 데이터베이스 관리자를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66dbc-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="66dbc-117">절차를 수행 하는 데 필요한 사용자 권한 및 권한에 대 한 자세한 내용은 [SQL Server에 대 한 배포 권한을](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66dbc-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


