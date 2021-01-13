---
title: SQL Server Reporting Services(필수 구성 요소가 충족되지 않음)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: 인프라에 배포된 모니터링 서버가 없는 경우 이 페이지가 표시됩니다. 이는 모니터링 서버 보고서 배포에 대한 최소 요구 사항이 충족되지 않았음을 나타냅니다.
ms.openlocfilehash: f02c16aad683aa01340316ce32c4dfcd12b0ef04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811098"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="5eb80-104">SQL Server Reporting Services(필수 구성 요소가 충족되지 않음)</span><span class="sxs-lookup"><span data-stu-id="5eb80-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="5eb80-p102">인프라에 배포된 모니터링 서버가 없는 경우 이 페이지가 표시됩니다. 이는 모니터링 서버 보고서 배포에 대한 최소 요구 사항이 충족되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5eb80-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="5eb80-107">이 문제를 해결하려면 모니터링 서버가 도메인에 가입되어 있는지, 해당 서버가 토폴로지 작성기에서 정의되어 있는지, 그리고 토폴로지가 게시되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="5eb80-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="5eb80-108">SQL Server Reporting Services도 사용할 수 있어야 SQL Server 서버 데이터베이스의 모니터링 서버 데이터베이스에 기능으로 설치해야 SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5eb80-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="5eb80-109">자세한 내용은 비즈니스용 Skype 서버 [2015에서](../../deploy/deploy-monitoring/install-monitoring-reports.md) 모니터링 보고서 설치 및 모니터링 [배포를 참조하세요.](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)</span><span class="sxs-lookup"><span data-stu-id="5eb80-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


