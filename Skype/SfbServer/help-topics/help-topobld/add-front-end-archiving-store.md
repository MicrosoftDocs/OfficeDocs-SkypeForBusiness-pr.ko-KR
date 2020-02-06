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
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: 보관에는 보관 데이터를 저장 하기 위해 지원 되는 Microsoft SQL Server 데이터베이스 소프트웨어 64 비트 버전이 필요 합니다. Sql Server 데이터베이스를 보관할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 고 SQL Se의 인스턴스 외에 새 SQL server 데이터베이스를 저장 하는 데 사용할 이전에 정의 된 SQL Server 데이터베이스를 선택 하거나 다음을 수행할 수 있습니다. 새 SQL Server 데이터베이스에 사용 하려는 rver (기본 인스턴스 또는 사용자가 지정 하는 명명 된 인스턴스가 될 수 있음).
ms.openlocfilehash: e315e27ddb96d018ca0bead13564ad88e944cd34
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820930"
---
# <a name="add-front-end-archiving-store"></a>프론트 엔드 보관 저장소 추가

보관에는 보관 데이터를 저장 하기 위해 지원 되는 Microsoft SQL Server 데이터베이스 소프트웨어 64 비트 버전이 필요 합니다. Sql Server 데이터베이스를 보관할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 고 SQL Se의 인스턴스 외에 새 SQL server 데이터베이스를 저장 하는 데 사용할 이전에 정의 된 SQL Server 데이터베이스를 선택 하거나 다음을 수행할 수 있습니다. 새 SQL Server 데이터베이스에 사용 하려는 rver (기본 인스턴스 또는 사용자가 지정 하는 명명 된 인스턴스가 될 수 있음).

> [!NOTE]
> 토폴로지를 게시 하는 데 사용 되는 계정에 적절 한 사용자 권한 및 사용 권한이 있는 경우 토폴로지를 게시할 때 모니터링 데이터베이스를 만들 수 있습니다. 나중에 설치 절차의 일부로 포함 된 데이터베이스를 만들 수도 있습니다.

> [!NOTE]
> 모니터링을 위해 SQL Server 기반 서버에 데이터베이스를 설치 하 고 배포 하려면 데이터베이스 파일을 설치 하는 SQL Server 기반 서버에 대 한 SQL Server sysadmins 그룹의 구성원 이어야 합니다. SQL Server sysadmin 그룹의 구성원이 아닌 경우 데이터베이스 파일이 배포 될 때까지 그룹에 추가 되도록 요청 해야 합니다. Sysadmins 그룹의 구성원을 만들 수 없는 경우에는 데이터베이스를 구성 하 고 배포 하는 스크립트를 사용 하 여 SQL Server 데이터베이스 관리자를 제공 해야 합니다. 절차를 수행 하는 데 필요한 사용자 권한 및 권한에 대 한 자세한 내용은 배포 설명서에서 [SQL Server 배포 권한을](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) 참조 하세요.


