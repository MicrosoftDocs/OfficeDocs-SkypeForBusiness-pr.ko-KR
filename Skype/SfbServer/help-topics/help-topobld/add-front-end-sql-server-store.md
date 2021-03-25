---
title: 프런트 엔드 SQL Server 저장소 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Standard Edition 서버 배포는 필요한 Microsoft SQL Server Express 데이터베이스 소프트웨어 및 SQL Server 설치합니다. 따라서 모든 옵션이 미리 채우기 때문에 기본 구성을 변경할 수 없습니다.
ms.openlocfilehash: e369f58afd015953cf0b58ca9788965a4829fd16
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119737"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="80d6a-104">프런트 엔드 SQL Server 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="80d6a-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="80d6a-105">Standard Edition 서버 배포는 필요한 Microsoft SQL Server Express 데이터베이스 소프트웨어 및 SQL Server 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="80d6a-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="80d6a-106">따라서 모든 옵션이 미리 채우기 때문에 기본 구성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80d6a-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="80d6a-107">Enterprise Edition 서버 배포의 프런트 엔드 풀에는 백 엔드 데이터베이스용 64비트 SQL Server 소프트웨어가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="80d6a-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="80d6a-108">백 엔드 데이터베이스에 사용할 이전에 정의한 SQL Server 데이터베이스를 선택하거나 SQL Server 데이터베이스가 있는 서버의 FQDN(FQDN)과 새 SQL Server 데이터베이스에 사용할 SQL Server 인스턴스를 지정하여 새 SQL Server 데이터베이스를 정의할 수 있습니다. 또는 지정한 명명된 인스턴스)</span><span class="sxs-lookup"><span data-stu-id="80d6a-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="80d6a-109">또한 서버 저장소에서 미러링을 사용하도록 설정하고 SQL Server 장애 조치(failover)에 대해 미러링 미러링 기능을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80d6a-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="80d6a-110">지원 SQL Server 대한 자세한 내용은 지원 가능성 설명서에서 [Database Software and Clustering Support을](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="80d6a-110">For details about SQL Server support, see [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) in the Supportability documentation.</span></span> <span data-ttu-id="80d6a-111">백엔드 데이터베이스용 SQL Server를 설정하는 방법에 대한 자세한 내용은 배포 설명서의 [Lync Server 2010용 SQL Server 구성](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="80d6a-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="80d6a-p105">토폴로지를 게시하는 데 사용한 계정에 적절한 사용자 권한이 있는 경우 토폴로지 게시 시 백 엔드 데이터베이스(RTC(실시간 통신))를 만들 수 있습니다. 또한 나중에 설치 절차의 일부로 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80d6a-p105">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology. You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="80d6a-114">Enterprise Edition 배포를 위해 SQL Server 기반 서버에 데이터베이스를 설치 및 배포하려면 데이터베이스 파일을 설치하는 SQL Server 기반 서버에 대한 SQL Server sysadmins 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80d6a-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="80d6a-115">SQL Server sysadmins 그룹의 구성원이 아닌 경우 데이터베이스 파일을 배포할 때까지 그룹에 추가를 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80d6a-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="80d6a-116">sysadmins 그룹의 구성원으로 만들 수 없는 경우 데이터베이스를 구성하고 배포할 스크립트를 SQL Server 데이터베이스 관리자에게 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80d6a-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="80d6a-117">절차를 수행하는 데 필요한 사용자 권한에 대한 자세한 내용은 [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="80d6a-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server).</span></span>