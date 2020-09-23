---
title: 모니터링 서버 SQL Server 저장소 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 모니터링 서버를 사용 하려면 모니터링 데이터를 저장 하기 위해 지원 되는 64 비트 버전의 SQL Server 데이터베이스 소프트웨어가 필요 합니다. 이전에 정의 된 SQL Server 데이터베이스를 모니터링에 사용 하도록 선택 하거나, SQL Server 데이터베이스가 상주할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 여 새 sql server 데이터베이스를 정의 하거나, 새 SQL Server 데이터베이스에 사용할 SQL Server 인스턴스 (기본 인스턴스 일 수 있음)를 지정할 수 있습니다. 또는 지정한 명명 된 인스턴스를 지정 합니다.
ms.openlocfilehash: adeb5385b385345163d7dc99b0a652837ab8bca4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217899"
---
# <a name="add-monitoring-server-sql-server-store"></a>모니터링 서버 SQL Server 저장소 추가

모니터링 서버를 사용 하려면 모니터링 데이터를 저장 하기 위해 지원 되는 64 비트 버전의 SQL Server 데이터베이스 소프트웨어가 필요 합니다. 이전에 정의 된 SQL Server 데이터베이스를 모니터링에 사용 하도록 선택 하거나, SQL Server 데이터베이스가 상주할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 여 새 sql server 데이터베이스를 정의 하거나, 새 SQL Server 데이터베이스에 사용할 SQL Server 인스턴스 (기본 인스턴스 일 수 있음)를 지정할 수 있습니다. 또는 지정한 명명 된 인스턴스를 지정 합니다.

SQL Server 지원에 대 한 자세한 내용은 지원 가능성 설명서에서 [데이터베이스 소프트웨어 및 클러스터링 지원을](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 참조 하십시오. 모니터링 데이터베이스의 배치 데이터베이스에 대 한 자세한 내용은 배포 설명서에서 [지원 되는 서버 위치](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) , 계획 설명서의[모니터링 계획](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) 및 [SQL Server 데이터 및 로그 파일 배치](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 를 참조 하십시오.

> [!NOTE]
> 토폴로지를 게시하는 데 사용한 계정에 적절한 사용자 권한 및 사용 권한이 있는 경우 토폴로지 게시 시 모니터링 데이터베이스를 만들 수 있습니다. 또한 나중에 설치 절차의 일부로 데이터베이스를 만들 수 있습니다. SQL Server 기반 서버에서 데이터베이스를 설치 하 고 배포 하려면 데이터베이스 파일을 설치할 SQL Server 기반 서버에 대해 sql server sysadmins 그룹의 구성원 이어야 합니다. > SQL Server sysadmin 그룹의 구성원이 아닌 경우에는 데이터베이스 파일을 배포할 때까지 해당 그룹에 추가 되도록 요청 해야 합니다. Sysadmins 그룹의 구성원으로 설정할 수 없는 경우 SQL Server 데이터베이스 관리자에 게 데이터베이스를 구성 및 배포 하기 위한 스크립트를 제공 해야 합니다. 절차를 수행하는 데 필요한 사용자 권한에 대한 자세한 내용은 배포 설명서에서 [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)을 참조하십시오.


