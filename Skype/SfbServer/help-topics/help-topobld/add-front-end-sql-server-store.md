---
title: 프런트 엔드 SQL Server 저장소 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Standard Edition 서버 배포에서는 필요한 Microsoft SQL Server Express 데이터베이스 소프트웨어 및 SQL Server 데이터베이스를 자동으로 설치 합니다. 따라서 모든 옵션이 미리 채워져 있으며 기본 구성을 변경할 수 없습니다.
ms.openlocfilehash: 614c3a852bb52a73c8a3f71ee467a2d71f82e9b6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216499"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="1beb9-104">프런트 엔드 SQL Server 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="1beb9-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="1beb9-105">Standard Edition 서버 배포에서는 필요한 Microsoft SQL Server Express 데이터베이스 소프트웨어 및 SQL Server 데이터베이스를 자동으로 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1beb9-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="1beb9-106">따라서 모든 옵션이 미리 채워져 있으며 기본 구성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1beb9-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="1beb9-107">Enterprise Edition server 배포의 프런트 엔드 풀에는 백 엔드 데이터베이스용으로 지원 되는 64 비트 버전의 SQL Server 데이터베이스 소프트웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1beb9-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="1beb9-108">이전에 정의 된 SQL Server 데이터베이스를 백 엔드 데이터베이스에 사용 하도록 선택 하거나, SQL Server 데이터베이스가 위치할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 여 새 SQL Server 데이터베이스를 정의 하거나, 기본 인스턴스일 수 있는 sql server 데이터베이스에 사용할 SQL Server 인스턴스를 정의할 수 있습니다. 또는 지정한 명명 된 인스턴스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1beb9-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="1beb9-109">또한 SQL Server 저장소에 대해 미러링을 사용 하도록 설정 하 고 자동 장애 조치 (failover)를 위해 미러링 모니터 서버를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1beb9-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="1beb9-110">SQL Server 지원에 대 한 자세한 내용은 지원 가능성 설명서에서 [데이터베이스 소프트웨어 및 클러스터링 지원을](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1beb9-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="1beb9-111">백엔드 데이터베이스용 SQL Server를 설정하는 방법에 대한 자세한 내용은 배포 설명서의 [Lync Server 2010용 SQL Server 구성](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1beb9-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="1beb9-p105">토폴로지를 게시하는 데 사용한 계정에 적절한 사용자 권한이 있는 경우 토폴로지 게시 시 백 엔드 데이터베이스(RTC(실시간 통신))를 만들 수 있습니다. 또한 나중에 설치 절차의 일부로 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1beb9-p105">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology. You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="1beb9-114">Enterprise Edition 배포용으로 SQL Server 기반 서버에 데이터베이스를 설치 하 고 배포 하려면 데이터베이스 파일을 설치할 SQL Server 기반 서버에 대 한 SQL Server sysadmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1beb9-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="1beb9-115">SQL Server sysadmins 그룹의 구성원이 아닌 경우에는 데이터베이스 파일을 배포할 때까지 해당 그룹에 추가 되도록 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1beb9-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="1beb9-116">Sysadmins 그룹의 구성원으로 설정할 수 없는 경우 SQL Server 데이터베이스 관리자에 게 데이터베이스를 구성 및 배포 하기 위한 스크립트를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1beb9-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="1beb9-117">절차를 수행하는 데 필요한 사용자 권한에 대한 자세한 내용은 [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1beb9-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


