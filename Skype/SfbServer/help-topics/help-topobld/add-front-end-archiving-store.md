---
title: 프론트 엔드 보관 저장소 추가
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
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: 보관을 사용 하려면 보관 데이터를 저장 하기 위해 지원 되는 64 비트 버전의 Microsoft SQL Server 데이터베이스 소프트웨어가 필요 합니다. 보관에 사용 되는 이전에 정의 된 SQL Server 데이터베이스를 선택 하거나, SQL Server 데이터베이스가 위치할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 여 새 SQL server 데이터베이스를 정의 하거나, 새 SQL Server 데이터베이스에 사용할 SQL Server의 인스턴스 (기본 인스턴스 일 수 있음)를 지정할 수 있습니다. 또는 지정한 명명 된 인스턴스를 지정 합니다.
ms.openlocfilehash: 0cf61aa758b2228c065659f518c81d637022ff47
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216719"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="82829-104">프론트 엔드 보관 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="82829-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="82829-105">보관을 사용 하려면 보관 데이터를 저장 하기 위해 지원 되는 64 비트 버전의 Microsoft SQL Server 데이터베이스 소프트웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="82829-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="82829-106">보관에 사용 되는 이전에 정의 된 SQL Server 데이터베이스를 선택 하거나, SQL Server 데이터베이스가 위치할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 여 새 SQL server 데이터베이스를 정의 하거나, 새 SQL Server 데이터베이스에 사용할 SQL Server의 인스턴스 (기본 인스턴스 일 수 있음)를 지정할 수 있습니다. 또는 지정한 명명 된 인스턴스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="82829-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="82829-107">토폴로지를 게시하는 데 사용한 계정에 적절한 사용자 권한 및 사용 권한이 있는 경우 토폴로지 게시 시 모니터링 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82829-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="82829-108">나중에 설치 절차의 일부로 포함 하 여 데이터베이스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82829-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="82829-109">모니터링을 위해 SQL Server 기반 서버에 데이터베이스를 설치 하 고 배포 하려면 데이터베이스 파일을 설치할 SQL Server 기반 서버에 대 한 SQL Server sysadmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82829-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="82829-110">SQL Server sysadmin 그룹의 구성원이 아닌 경우에는 데이터베이스 파일을 배포할 때까지 해당 그룹에 추가 되도록 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82829-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="82829-111">Sysadmins 그룹의 구성원으로 설정할 수 없는 경우 SQL Server 데이터베이스 관리자에 게 데이터베이스를 구성 및 배포 하기 위한 스크립트를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82829-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="82829-112">절차를 수행 하는 데 필요한 사용자 권한 및 권한에 대 한 자세한 내용은 배포 설명서에서 [SQL Server에 대 한 배포 권한](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="82829-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


