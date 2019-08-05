---
title: SQL Server Reporting Services(필수 구성 요소가 충족되지 않음)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: 인프라에 배포된 모니터링 서버가 없는 경우 이 페이지가 표시됩니다. 이는 모니터링 서버 보고서 배포에 대한 최소 요구 사항이 충족되지 않았음을 나타냅니다.
ms.openlocfilehash: af04fd438620bea32bcab95cdbca295c116773b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191481"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="895e6-104">SQL Server Reporting Services(필수 구성 요소가 충족되지 않음)</span><span class="sxs-lookup"><span data-stu-id="895e6-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="895e6-p102">인프라에 배포된 모니터링 서버가 없는 경우 이 페이지가 표시됩니다. 이는 모니터링 서버 보고서 배포에 대한 최소 요구 사항이 충족되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="895e6-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="895e6-107">이 문제를 해결 하려면 도메인에 연결 된 모니터링 서버를 사용 하 고 토폴로지 작성기에 정의 되어 있으며 토폴로지가 게시 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="895e6-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="895e6-108">Sql server Reporting Services도 sql server에서 사용 가능 하 고 SQL Server의 모니터링 서버 데이터베이스에 기능으로 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895e6-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="895e6-109">자세한 내용은 [비즈니스용 Skype 서버 2015에서 모니터링 보고서 설치](../../deploy/deploy-monitoring/install-monitoring-reports.md) 및 [모니터링 배포](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="895e6-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


