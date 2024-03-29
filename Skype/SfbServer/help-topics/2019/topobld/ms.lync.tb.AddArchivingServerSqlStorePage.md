---
title: 보관 서버 SQL 서버 저장소 추가
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: 보관 서버에는 보관 데이터를 저장하기 위해 지원되는 64비트 SQL Server 데이터베이스 소프트웨어가 필요합니다. 보관에 사용할 이전에 정의한 SQL Server 데이터베이스를 선택하거나 SQL Server 데이터베이스가 상주할 서버의 FQDN(FQDN)과 새 SQL Server 데이터베이스 인스턴스를 지정하여 새 SQL Server 데이터베이스를 정의할 수 SQL Server  데이터베이스(지정한 기본 인스턴스 또는 명명된 인스턴스일 수 있습니다.)
ms.openlocfilehash: 2901e50ea93de36c0cb3e61a0f954c7589f3b4af
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392040"
---
# <a name="add-archiving-server-sql-server-store"></a>보관 서버 SQL 서버 저장소 추가

보관 서버에는 보관 데이터를 저장하기 위해 지원되는 64비트 SQL Server 데이터베이스 소프트웨어가 필요합니다. 보관에 사용할 이전에 정의한 SQL Server 데이터베이스를 선택하거나 SQL Server 데이터베이스가 상주할 서버의 FQDN(FQDN)과 새 SQL Server 데이터베이스 인스턴스를 지정하여 새 SQL Server 데이터베이스를 정의할 수 SQL Server  데이터베이스(지정한 기본 인스턴스 또는 명명된 인스턴스일 수 있습니다.)

> [!NOTE]
> 토폴로지 게시에 사용되는 계정에 적절한 사용자 권한 및 사용 권한이 있는 경우 토폴로지 게시 시 보관 데이터베이스(LcsLog)를 만들 수 있습니다. 나중에 설치 절차의 일부로 또는 그 외의 경우 데이터베이스를 만들 수도 있습니다.

> [!NOTE]
> 보관용 SQL Server 기반 서버에 데이터베이스를 설치 및 배포하려면 데이터베이스 파일을 설치하는 SQL Server 기반 서버에 대한 SQL Server sysadmins 그룹의 구성원이 되어야 합니다. SQL Server sysadmins 그룹의 구성원이 아닌 경우 데이터베이스 파일을 배포할 때까지 그룹에 추가를 요청해야 합니다. sysadmins 그룹의 구성원으로 만들 수 없는 경우 데이터베이스를 구성하고 배포할 스크립트를 SQL Server 데이터베이스 관리자에게 제공해야 합니다. 절차를 수행하기 위해 필요한 사용자 권한 및 사용 권한에 대한 자세한 내용은 배포 설명서에서 [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) 참조하십시오.