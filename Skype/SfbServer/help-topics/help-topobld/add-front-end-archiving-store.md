---
title: 프런트 엔드 보관 저장소 추가
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: 보관을 사용하려면 보관 데이터를 저장하기 위해 Microsoft SQL Server 데이터베이스 소프트웨어의 지원되는 64비트 버전이 필요합니다. 보관에 사용할 이전에 정의한 SQL Server 데이터베이스를 선택하거나 SQL Server 데이터베이스가 상주할 서버의 FQDN(FQDN)을 지정하여 새 SQL Server 데이터베이스(기본 인스턴스 또는 지정한 명명된 인스턴스)에 사용할 SQL Server 인스턴스를 지정하여 새 SQL Server 데이터베이스를 정의할 수 있습니다.
ms.openlocfilehash: ecf1aad9b21a3501e8f05dfdecbd5b1472846b58
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837840"
---
# <a name="add-front-end-archiving-store"></a>프런트 엔드 보관 저장소 추가

보관을 사용하려면 보관 데이터를 저장하기 위해 Microsoft SQL Server 데이터베이스 소프트웨어의 지원되는 64비트 버전이 필요합니다. 보관에 사용할 이전에 정의한 SQL Server 데이터베이스를 선택하거나 SQL Server 데이터베이스가 상주할 서버의 FQDN(FQDN)을 지정하여 새 SQL Server 데이터베이스(기본 인스턴스 또는 지정한 명명된 인스턴스)에 사용할 SQL Server 인스턴스를 지정하여 새 SQL Server 데이터베이스를 정의할 수 있습니다.

> [!NOTE]
> 토폴로지를 게시하는 데 사용한 계정에 적절한 사용자 권한 및 사용 권한이 있는 경우 토폴로지 게시 시 모니터링 데이터베이스를 만들 수 있습니다. 나중에 설치 절차의 일부로 포함된 데이터베이스를 만들 수도 있습니다.

> [!NOTE]
> 모니터링을 위해 SQL Server 기반 서버에 데이터베이스를 설치 및 배포하려면 데이터베이스 파일을 설치하는 SQL Server 기반 서버에 대한 SQL Server sysadmins 그룹의 구성원이 되어야 합니다. SQL Server sysadmin 그룹의 구성원이 아닌 경우 데이터베이스 파일을 배포할 때까지 그룹에 추가를 요청해야 합니다. sysadmins 그룹의 구성원으로 만들 수 없는 경우 데이터베이스를 구성하고 배포할 스크립트를 SQL Server 데이터베이스 관리자에게 제공해야 합니다. 절차를 수행하기 위해 필요한 사용자 권한 및 사용 권한에 대한 자세한 내용은 배포 설명서에서 [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) 참조하십시오.