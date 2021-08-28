---
title: 모니터링 서버 SQL Server 저장소 추가
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
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 모니터링 서버를 사용하려면 모니터링 데이터를 저장하기 위해 지원되는 64비트 SQL Server 데이터베이스 소프트웨어가 필요합니다. 모니터링에 사용할 이전에 정의한 SQL Server 데이터베이스를 선택하거나, SQL Server 데이터베이스가 상주할 서버의 FQDN(FQDN)과 새 SQL Server 데이터베이스에 사용할 SQL Server 인스턴스(기본 인스턴스 또는 지정한 명명된 인스턴스)를 지정하여 새 SQL Server 데이터베이스를 정의할 수 있습니다.
ms.openlocfilehash: ad141dff28b978066f5dfb9d6af81047bec2048c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593752"
---
# <a name="add-monitoring-server-sql-server-store"></a>모니터링 서버 SQL Server 저장소 추가

모니터링 서버를 사용하려면 모니터링 데이터를 저장하기 위해 지원되는 64비트 SQL Server 데이터베이스 소프트웨어가 필요합니다. 모니터링에 사용할 이전에 정의한 SQL Server 데이터베이스를 선택하거나, SQL Server 데이터베이스가 상주할 서버의 FQDN(FQDN)과 새 SQL Server 데이터베이스에 사용할 SQL Server 인스턴스(기본 인스턴스 또는 지정한 명명된 인스턴스)를 지정하여 새 SQL Server 데이터베이스를 정의할 수 있습니다.

지원 SQL Server 대한 자세한 내용은 지원 가능성 설명서에서 [Database Software and Clustering Support을](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) 참조하십시오. 모니터링 데이터베이스 배치를 비롯한 모니터링 데이터베이스에 대한 자세한 내용은 지원 [](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) 가능성 설명서의 지원되는 서버 위치, 계획 설명서의[모니터링](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) 계획 및 배포 [설명서의](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) SQL Server 데이터 및 로그 파일 배치를 참조하십시오.

> [!NOTE]
> 토폴로지를 게시하는 데 사용한 계정에 적절한 사용자 권한 및 사용 권한이 있는 경우 토폴로지 게시 시 모니터링 데이터베이스를 만들 수 있습니다. 또한 나중에 설치 절차의 일부로 데이터베이스를 만들 수 있습니다. > 모니터링을 위해 SQL Server 기반 서버에 데이터베이스를 설치 및 배포하려면 데이터베이스 파일을 설치하는 SQL Server 기반 서버에 대한 SQL Server sysadmins 그룹의 구성원이 되어야 합니다. SQL Server sysadmin 그룹의 구성원이 아닌 경우 데이터베이스 파일이 배포될 때까지 그룹에 추가를 요청해야 합니다. sysadmins 그룹의 구성원으로 만들 수 없는 경우 데이터베이스를 구성하고 배포할 스크립트를 SQL Server 데이터베이스 관리자에게 제공해야 합니다. 절차를 수행하는 데 필요한 사용자 권한에 대한 자세한 내용은 배포 설명서에서 [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)을 참조하십시오.