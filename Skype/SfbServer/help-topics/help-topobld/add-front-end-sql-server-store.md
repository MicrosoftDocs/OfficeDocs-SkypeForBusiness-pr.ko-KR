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
ms.openlocfilehash: 939f12fa02951074e487066337c8bb76af59143a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824078"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="e03b5-104">프런트 엔드 SQL Server 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="e03b5-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="e03b5-105">Standard Edition 서버 배포는 필요한 Microsoft SQL Server Express 데이터베이스 소프트웨어 및 SQL Server 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e03b5-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="e03b5-106">따라서 모든 옵션이 미리 채우기 때문에 기본 구성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e03b5-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="e03b5-107">Enterprise Edition 서버 배포의 프런트 엔드 풀에는 백 엔드 데이터베이스에 대해 지원되는 SQL Server 데이터베이스 소프트웨어가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e03b5-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="e03b5-108">백 엔드 데이터베이스에 사용할 이전에 정의한 SQL Server 데이터베이스를 선택하거나 SQL Server 데이터베이스가 상주할 서버의 FQDN(FQDN)과 새 SQL Server 데이터베이스에 사용할 SQL Server 인스턴스를 지정하여 새 SQL Server 데이터베이스를 정의할 수 있습니다. 또는 지정한 명명된 인스턴스)</span><span class="sxs-lookup"><span data-stu-id="e03b5-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="e03b5-109">또한 SQL Server 저장소에서 미러링을 사용하도록 설정하고 자동 장애 조치(failover)에 대해 미러링된 미러링 SQL Server 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e03b5-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="e03b5-110">지원에 대한 SQL Server 내용은 지원 가능성 설명서에서 [데이터베이스](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 소프트웨어 및 클러스터링 지원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e03b5-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="e03b5-111">백엔드 데이터베이스용 SQL Server를 설정하는 방법에 대한 자세한 내용은 배포 설명서의 [Lync Server 2010용 SQL Server 구성](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e03b5-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="e03b5-p105">토폴로지를 게시하는 데 사용한 계정에 적절한 사용자 권한이 있는 경우 토폴로지 게시 시 백 엔드 데이터베이스(RTC(실시간 통신))를 만들 수 있습니다. 또한 나중에 설치 절차의 일부로 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e03b5-p105">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology. You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="e03b5-114">Enterprise Edition 배포를 위해 SQL Server 기반 서버에 데이터베이스를 설치하고 배포하려면 데이터베이스 파일을 설치하는 SQL Server 기반 서버에 대한 SQL Server sysadmins 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03b5-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="e03b5-115">SQL Server sysadmins 그룹의 구성원이 아닌 경우 데이터베이스 파일을 배포할 때까지 그룹에 추가를 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03b5-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="e03b5-116">sysadmins 그룹의 구성원으로 만들 수 없는 경우 SQL Server 데이터베이스 관리자에게 데이터베이스를 구성하고 배포할 스크립트를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e03b5-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="e03b5-117">절차를 수행하는 데 필요한 사용자 권한에 대한 자세한 내용은 [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e03b5-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


