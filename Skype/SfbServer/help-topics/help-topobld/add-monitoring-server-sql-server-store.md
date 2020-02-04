---
title: 모니터링 서버 SQL 서버 저장소 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 모니터링 데이터를 저장 하려면 모니터링 서버에 지원 되는 64 비트 버전의 SQL Server 데이터베이스 소프트웨어가 필요 합니다. Sql server 데이터베이스가 상주할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 여 새 SQL Server 데이터베이스를 정의 하는 것으로, 이전에 모니터링 하는 데 사용할 SQL Server 데이터베이스를 선택 하거나이 인스턴스를 사용할 수 있습니다. 새 SQL Server 데이터베이스 (기본 인스턴스가 될 수 있거나 지정한 명명 된 인스턴스)에 사용할 서버를 선택 합니다.
ms.openlocfilehash: 8c74462e0623c34fbbbf4c3f67d1a0adf0f3c922
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698183"
---
# <a name="add-monitoring-server-sql-server-store"></a><span data-ttu-id="75462-104">모니터링 서버 SQL 서버 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="75462-104">Add Monitoring Server SQL Server Store</span></span>

<span data-ttu-id="75462-105">모니터링 데이터를 저장 하려면 모니터링 서버에 지원 되는 64 비트 버전의 SQL Server 데이터베이스 소프트웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="75462-105">Monitoring Server requires a supported 64-bit edition of SQL Server database software to store the monitoring data.</span></span> <span data-ttu-id="75462-106">Sql server 데이터베이스가 상주할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 여 새 SQL Server 데이터베이스를 정의 하는 것으로, 이전에 모니터링 하는 데 사용할 SQL Server 데이터베이스를 선택 하거나이 인스턴스를 사용할 수 있습니다. 새 SQL Server 데이터베이스 (기본 인스턴스가 될 수 있거나 지정한 명명 된 인스턴스)에 사용할 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75462-106">You can either select a previously defined SQL Server database to be used for monitoring, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

<span data-ttu-id="75462-107">SQL Server 지원에 대 한 자세한 내용은 지원 가능성 설명서의 [데이터베이스 소프트웨어 및 클러스터링 지원을](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="75462-107">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="75462-108">모니터링 데이터베이스의 위치를 포함 하 여 모니터링 데이터베이스에 대 한 자세한 내용은 배포[설명서의 계획](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) 문서 및 [SQL Server 데이터 및 로그 파일 배치](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 에서 [지원 되는 서버 위치](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="75462-108">For details about the monitoring database, including collocation of the monitoring database, see [Supported Server Location](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation,[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="75462-109">토폴로지를 게시 하는 데 사용 되는 계정에 적절 한 사용자 권한 및 사용 권한이 있는 경우 토폴로지를 게시할 때 모니터링 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75462-109">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="75462-110">나중에 설치 절차의 일부로 포함 하 여 데이터베이스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75462-110">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="75462-111">SQL Server 기반 서버에서 모니터링을 위해 데이터베이스를 설치 하 고 배포 하는 > 데이터베이스 파일을 설치 하는 SQL Server 기반 서버에 대 한 SQL Server sysadmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75462-111">> To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="75462-112">SQL Server sysadmin 그룹의 구성원이 아닌 경우 데이터베이스 파일을 배포할 때까지 그룹에 추가 하도록 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75462-112">If you are not a member of the SQL Server sysadmin group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="75462-113">Sysadmins 그룹의 구성원을 만들 수 없는 경우에는 데이터베이스를 구성 하 고 배포 하는 스크립트를 사용 하 여 SQL Server 데이터베이스 관리자를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75462-113">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="75462-114">이러한 절차를 수행 하는 데 필요한 사용자 권한 및 권한에 대 한 자세한 내용은 배포 설명서에서 [SQL Server 배포 권한을](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="75462-114">For details about the user rights and permissions that you need to accomplish these procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


