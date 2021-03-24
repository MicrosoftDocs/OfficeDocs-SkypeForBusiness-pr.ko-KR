---
title: SQL 저장소 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
description: 새 SQL 저장소를 정의하려면( SQL Server 기반 데이터베이스 및 기본 인스턴스인 SQL Server 인스턴스를 지정하는 경우 다음을 지정합니다.
ms.openlocfilehash: 28018a7320bc42761a668aaff385302016781592
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095602"
---
# <a name="add-sql-store"></a><span data-ttu-id="db195-103">SQL 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="db195-103">Add SQL Store</span></span>

<span data-ttu-id="db195-104">새 SQL 저장소를 정의하려면( SQL Server 기반 데이터베이스 및 기본 인스턴스인 SQL Server 인스턴스를 지정하는 경우 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="db195-104">To define a new SQL Store, which means that you are specifying a SQL Server-based database and an instance of SQL Server—either a default instance or a named instance—you specify the following.</span></span>

<span data-ttu-id="db195-105">정의할 데이터베이스 인스턴스를 호스팅할 서버의 FQDN(SQL Server 도메인 이름)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="db195-105">Specify the fully qualified domain name (FQDN) of the SQL Server that will host the database instance that you are defining.</span></span>

<span data-ttu-id="db195-106">데이터를 호스팅할 SQL Server 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="db195-106">Specify the instance of SQL Server that will host the data.</span></span> <span data-ttu-id="db195-107">기본 인스턴스를 지정할 수도 있고 명명된 인스턴스를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db195-107">You can specify the default instance, or you can specify a named instance.</span></span>

<span data-ttu-id="db195-108">특정 인스턴스에서의 데이터베이스 배치는 분명하게 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db195-108">Collocation of databases in specific instances should be very clearly understood.</span></span> <span data-ttu-id="db195-109">서버 배치 및 데이터베이스 인스턴스 배치에 대한 자세한 내용은 [Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment) 및 [Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="db195-109">For details about server collocation and database instance collocation, see [Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment) and [Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment).</span></span>