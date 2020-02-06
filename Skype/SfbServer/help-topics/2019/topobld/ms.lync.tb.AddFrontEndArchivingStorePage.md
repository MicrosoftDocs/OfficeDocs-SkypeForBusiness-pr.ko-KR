---
title: 프론트 엔드 보관 저장소 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: 보관에는 보관 데이터를 저장 하기 위해 지원 되는 Microsoft SQL Server 데이터베이스 소프트웨어 64 비트 버전이 필요 합니다. Sql Server 데이터베이스를 보관할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 고 SQL Se의 인스턴스 외에 새 SQL server 데이터베이스를 저장 하는 데 사용할 이전에 정의 된 SQL Server 데이터베이스를 선택 하거나 다음을 수행할 수 있습니다. 새 SQL Server 데이터베이스에 사용 하려는 rver (기본 인스턴스 또는 사용자가 지정 하는 명명 된 인스턴스가 될 수 있음).
ms.openlocfilehash: 234d0a2d4ef14aa969b8ef8c7445558e53ca2fee
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794907"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="350e6-104">프론트 엔드 보관 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="350e6-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="350e6-105">보관에는 보관 데이터를 저장 하기 위해 지원 되는 Microsoft SQL Server 데이터베이스 소프트웨어 64 비트 버전이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="350e6-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="350e6-106">Sql Server 데이터베이스를 보관할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 고 SQL Se의 인스턴스 외에 새 SQL server 데이터베이스를 저장 하는 데 사용할 이전에 정의 된 SQL Server 데이터베이스를 선택 하거나 다음을 수행할 수 있습니다. 새 SQL Server 데이터베이스에 사용 하려는 rver (기본 인스턴스 또는 사용자가 지정 하는 명명 된 인스턴스가 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="350e6-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="350e6-107">토폴로지를 게시 하는 데 사용 되는 계정에 적절 한 사용자 권한 및 사용 권한이 있는 경우 토폴로지를 게시할 때 모니터링 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350e6-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="350e6-108">나중에 설치 절차의 일부로 포함 된 데이터베이스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350e6-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="350e6-109">모니터링을 위해 SQL Server 기반 서버에 데이터베이스를 설치 하 고 배포 하려면 데이터베이스 파일을 설치 하는 SQL Server 기반 서버에 대 한 SQL Server sysadmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="350e6-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="350e6-110">SQL Server sysadmin 그룹의 구성원이 아닌 경우 데이터베이스 파일이 배포 될 때까지 그룹에 추가 되도록 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="350e6-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="350e6-111">Sysadmins 그룹의 구성원을 만들 수 없는 경우에는 데이터베이스를 구성 하 고 배포 하는 스크립트를 사용 하 여 SQL Server 데이터베이스 관리자를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="350e6-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="350e6-112">절차를 수행 하는 데 필요한 사용자 권한 및 권한에 대 한 자세한 내용은 배포 설명서에서 [SQL Server 배포 권한을](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="350e6-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


