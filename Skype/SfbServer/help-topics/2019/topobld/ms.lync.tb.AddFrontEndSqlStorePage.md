---
title: 프런트 엔드 SQL Server 저장소 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Standard Edition 배포에서는 필요한 데이터베이스 소프트웨어 및 Microsoft SQL Server Express 데이터베이스를 자동으로 SQL Server 설치합니다. 따라서 모든 옵션이 미리 채우기 때문에 기본 구성을 변경할 수 없습니다.
ms.openlocfilehash: 79391900b3379836460935dfc8c0402a2914ec0d80fc398b1483dad93bdb72d2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323470"
---
# <a name="add-front-end-sql-server-store"></a>프런트 엔드 SQL Server 저장소 추가

Standard Edition 배포에서는 필요한 데이터베이스 소프트웨어 및 Microsoft SQL Server Express 데이터베이스를 자동으로 SQL Server 설치합니다. 따라서 모든 옵션이 미리 채우기 때문에 기본 구성을 변경할 수 없습니다.

Enterprise Edition 배포의 프런트 엔드 풀에는 백 엔드 데이터베이스용 64비트 SQL Server 소프트웨어가 필요합니다. 백 엔드 데이터베이스에 사용할 이전에 정의한 SQL Server 데이터베이스를 선택하거나 SQL Server 데이터베이스가 상주할 서버의 FQDN(FQDN) 및 새 SQL Server 데이터베이스에 사용할 SQL Server 인스턴스(기본 인스턴스 또는 지정한 명명된 인스턴스)를 지정하여 새 SQL Server 데이터베이스를 정의할 수 있습니다. 또한 서버 저장소에서 미러링을 사용하도록 설정하고 SQL Server 장애 조치(failover)에 대해 미러링 미러링을 지정할 수 있습니다.

지원 SQL Server 대한 자세한 내용은 지원 가능성 설명서에서 [Database Software and Clustering Support을](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) 참조하십시오. 백 엔드 데이터베이스에 대한 SQL Server 설정하는 자세한 내용은 배포 설명서에서 [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) 참조하십시오.

> [!NOTE]
> 토폴로지를 게시하는 데 사용한 계정에 적절한 사용자 권한이 있는 경우 토폴로지 게시 시 백 엔드 데이터베이스(RTC(실시간 통신))를 만들 수 있습니다. 또한 나중에 설치 절차의 일부로 데이터베이스를 만들 수 있습니다.

> [!NOTE]
> SQL Server 배포를 위해 SQL Server Enterprise Edition 기반 서버에 데이터베이스를 설치하고 배포하려면 데이터베이스 파일을 설치하는 SQL Server 기반 서버에 대한 SQL Server sysadmins 그룹의 구성원이 되어야 합니다. SQL Server sysadmins 그룹의 구성원이 아닌 경우 데이터베이스 파일이 배포될 때까지 그룹에 추가를 요청해야 합니다. sysadmins 그룹의 구성원으로 만들 수 없는 경우 데이터베이스를 구성하고 배포할 스크립트를 SQL Server 데이터베이스 관리자에게 제공해야 합니다. 절차를 수행하는 데 필요한 사용자 권한에 대한 자세한 내용은 [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)을 참조하십시오.