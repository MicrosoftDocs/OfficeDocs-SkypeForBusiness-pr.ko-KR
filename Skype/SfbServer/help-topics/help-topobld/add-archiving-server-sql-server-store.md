---
title: 보관 서버 SQL 서버 저장소 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: 보관 서버에는 보관 데이터를 저장 하기 위해 지원 되는 64 비트 버전의 SQL Server 데이터베이스 소프트웨어가 필요 합니다. SQL Server 데이터베이스를 저장할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 여 새 SQL server 데이터베이스를 보관 하거나 정의 하는 데 사용할 이전에 정의 된 SQL Server 데이터베이스를 선택 하거나, 새 SQL Server 데이터베이스에 사용할 SQL Server 인스턴스 (기본 인스턴스 또는 지정한 명명 된 인스턴스 일 수 있음)를 선택할 수 있습니다.
ms.openlocfilehash: eb25152916c61ff40274705a408fe0a7a618cbcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217439"
---
# <a name="add-archiving-server-sql-server-store"></a>보관 서버 SQL 서버 저장소 추가

보관 서버에는 보관 데이터를 저장 하기 위해 지원 되는 64 비트 버전의 SQL Server 데이터베이스 소프트웨어가 필요 합니다. SQL Server 데이터베이스를 저장할 서버의 FQDN (정규화 된 도메인 이름)을 지정 하 여 새 SQL server 데이터베이스를 보관 하거나 정의 하는 데 사용할 이전에 정의 된 SQL Server 데이터베이스를 선택 하거나, 새 SQL Server 데이터베이스에 사용할 SQL Server 인스턴스 (기본 인스턴스 또는 지정한 명명 된 인스턴스 일 수 있음)를 선택할 수 있습니다.

> [!NOTE]
> 토폴로지를 게시 하는 데 사용 되는 계정에 적절 한 사용자 권한 및 사용 권한이 있는 경우에는 토폴로지를 게시할 때 LcsLog (보관 데이터베이스)를 만들 수 있습니다. 설치 절차의 일부로 나중에 데이터베이스를 만들 수도 있습니다.

> [!NOTE]
> 보관을 위해 SQL Server 기반 서버에 데이터베이스를 설치 하 고 배포 하려면 데이터베이스 파일을 설치할 SQL Server 기반 서버에 대해 SQL Server sysadmins 그룹의 구성원 이어야 합니다. SQL Server sysadmins 그룹의 구성원이 아닌 경우에는 데이터베이스 파일을 배포할 때까지 해당 그룹에 추가 되도록 요청 해야 합니다. Sysadmins 그룹의 구성원으로 설정할 수 없는 경우 SQL Server 데이터베이스 관리자에 게 데이터베이스를 구성 및 배포 하기 위한 스크립트를 제공 해야 합니다. 절차를 수행 하는 데 필요한 사용자 권한 및 권한에 대 한 자세한 내용은 배포 설명서에서 [SQL Server에 대 한 배포 권한](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) 를 참조 하십시오.


