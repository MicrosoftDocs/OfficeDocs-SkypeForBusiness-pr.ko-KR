---
title: 모니터링 서버 SQL Server 저장소 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: 모니터링 서버를 사용하려면 모니터링 데이터를 저장하기 위해 지원되는 64비트 SQL Server 데이터베이스 소프트웨어가 필요합니다. 모니터링에 사용할 이전에 정의한 SQL Server SQL Server 데이터베이스를 선택하거나 SQL Server 데이터베이스가 상주할 서버의 FQDN(FQDN)을 지정하여 새 SQL Server 데이터베이스(기본 인스턴스일 수 있는)에 사용할 SQL Server 데이터베이스를 정의할 수 있습니다. 또는 지정한 명명된 인스턴스)
ms.openlocfilehash: a96dced5bfae5e8381ea28874d295dcfe146d33e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807738"
---
# <a name="add-monitoring-server-sql-server-store"></a>모니터링 서버 SQL Server 저장소 추가

모니터링 서버를 사용하려면 모니터링 데이터를 저장하기 위해 지원되는 64비트 SQL Server 데이터베이스 소프트웨어가 필요합니다. 모니터링에 사용할 이전에 정의한 SQL Server SQL Server 데이터베이스를 선택하거나 SQL Server 데이터베이스가 상주할 서버의 FQDN(FQDN)을 지정하여 새 SQL Server 데이터베이스(기본 인스턴스일 수 있는)에 사용할 SQL Server 데이터베이스를 정의할 수 있습니다. 또는 지정한 명명된 인스턴스)

지원에 대한 SQL Server 내용은 지원 가능성 설명서에서 [데이터베이스](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 소프트웨어 및 클러스터링 지원을 참조하십시오. 모니터링 데이터베이스 배치를 비롯한 모니터링 데이터베이스에 대한 자세한 내용은 지원 [](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) 가능성 설명서의 지원되는 서버[위치,](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) 계획 설명서의 [](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 모니터링 계획 및 배포 설명서의 SQL Server 데이터 및 로그 파일 배치를 참조하십시오.

> [!NOTE]
> 토폴로지를 게시하는 데 사용한 계정에 적절한 사용자 권한 및 사용 권한이 있는 경우 토폴로지 게시 시 모니터링 데이터베이스를 만들 수 있습니다. 또한 나중에 설치 절차의 일부로 데이터베이스를 만들 수 있습니다. > 모니터링을 위해 SQL Server 기반 서버에 데이터베이스를 설치하고 배포하려면 데이터베이스 파일을 설치하는 SQL Server 기반 서버에 대해 SQL Server sysadmins 그룹의 구성원이 되어야 합니다. SQL Server sysadmin 그룹의 구성원이 아닌 경우 데이터베이스 파일을 배포할 때까지 그룹에 추가를 요청해야 합니다. sysadmins 그룹의 구성원으로 만들 수 없는 경우 SQL Server 데이터베이스 관리자에게 데이터베이스를 구성하고 배포할 스크립트를 제공해야 합니다. 절차를 수행하는 데 필요한 사용자 권한에 대한 자세한 내용은 배포 설명서에서 [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)을 참조하십시오.


