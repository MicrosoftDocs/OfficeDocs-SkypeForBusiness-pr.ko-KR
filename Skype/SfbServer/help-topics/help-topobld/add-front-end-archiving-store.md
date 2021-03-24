---
title: 프런트 엔드 보관 저장소 추가
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
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: 보관을 사용하려면 보관 데이터를 저장하기 위해 Microsoft SQL Server 데이터베이스 소프트웨어의 지원되는 64비트 버전이 필요합니다. 보관에 사용할 이전에 정의한 SQL Server 데이터베이스를 선택하거나 SQL Server 데이터베이스가 상주할 서버의 FQDN(FQDN)을 지정하고 새 SQL Server 데이터베이스에 사용할 SQL Server 데이터베이스(기본 인스턴스일 수 있는)를 지정하여 새 SQL Server 데이터베이스를 정의할 수 있습니다. 또는 지정한 명명된 인스턴스)
ms.openlocfilehash: 9f3ee74944ca19f827229bcfcaea2a1e37d2bfcb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107844"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="0624d-104">프런트 엔드 보관 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="0624d-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="0624d-105">보관을 사용하려면 보관 데이터를 저장하기 위해 Microsoft SQL Server 데이터베이스 소프트웨어의 지원되는 64비트 버전이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0624d-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="0624d-106">보관에 사용할 이전에 정의한 SQL Server 데이터베이스를 선택하거나 SQL Server 데이터베이스가 상주할 서버의 FQDN(FQDN)을 지정하고 새 SQL Server 데이터베이스에 사용할 SQL Server 데이터베이스(기본 인스턴스일 수 있는)를 지정하여 새 SQL Server 데이터베이스를 정의할 수 있습니다. 또는 지정한 명명된 인스턴스)</span><span class="sxs-lookup"><span data-stu-id="0624d-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="0624d-107">토폴로지를 게시하는 데 사용한 계정에 적절한 사용자 권한 및 사용 권한이 있는 경우 토폴로지 게시 시 모니터링 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0624d-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="0624d-108">나중에 설치 절차의 일부로 포함된 데이터베이스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0624d-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="0624d-109">모니터링을 위해 SQL Server 기반 서버에 데이터베이스를 설치 및 배포하려면 데이터베이스 파일을 설치하는 SQL Server 기반 서버에 대한 SQL Server sysadmins 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0624d-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="0624d-110">SQL Server sysadmin 그룹의 구성원이 아닌 경우 데이터베이스 파일을 배포할 때까지 그룹에 추가를 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0624d-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="0624d-111">sysadmins 그룹의 구성원으로 만들 수 없는 경우 데이터베이스를 구성하고 배포할 스크립트를 SQL Server 데이터베이스 관리자에게 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0624d-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="0624d-112">절차를 수행하기 위해 필요한 사용자 권한 및 사용 권한에 대한 자세한 내용은 배포 설명서에서 [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0624d-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in the Deployment documentation.</span></span>