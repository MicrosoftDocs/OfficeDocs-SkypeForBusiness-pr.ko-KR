---
title: 데이터베이스 설치 옵션 페이지
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
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 데이터베이스 및 로그 파일 배치에 대한 고급 옵션을 구성할 수 SQL Server. 다음과 같은 옵션을 사용할 수 있습니다.
ms.openlocfilehash: 6b9ad2dc1dd91eeb0834c43394f00221d687d0d66058c5037e6d90c83cd10bad
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321720"
---
# <a name="install-database-options-page"></a>데이터베이스 설치 옵션 페이지

데이터베이스 및 로그 파일 배치에 대한 고급 옵션을 구성할 수 SQL Server. 다음과 같은 옵션을 사용할 수 있습니다.

> [!IMPORTANT]
> 컴퓨터의 데이터 및 로그 파일 배치와 관련한 요구 사항 및 정책에 가장 적합한 SQL Server 선택합니다.

 **데이터베이스 파일** 위치 자동 결정: 기본 옵션은 데이터베이스의 사용 가능한 공간을 결정하고 최적의 성능을 SQL Server 및 로그 파일을 배포하는 알고리즘을 사용합니다.

 **인스턴스 SQL Server** 사용: 인스턴스 설정에 따라 데이터베이스 파일 및 로그 파일을 SQL Server. 옵션은 보통 데이터베이스 관리자에 의해 관리 및 구성됩니다.

 대상 SQL Server **경로:** 데이터베이스 및 로그 파일이 배치될 드라이브 및 폴더의 전체 경로를 입력하여 SQL Server 데이터베이스 및 로그 파일에 대한 경로를 정의하려면 이 옵션을 선택합니다.

> [!IMPORTANT]
> 입력하는 경로는 설치의 성능 최적화 알고리즘에 따라 수정될 수 있습니다. 자세한 내용은 [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)를 참조하십시오.

 **확인**: 변경 내용을 커밋하려면 확인 단추를 클릭합니다.

 **취소**: 변경 내용을 취소하고 데이터베이스 설치 화면으로 돌아가려면 취소를 클릭합니다.

 **도움말**: 이 도움말 페이지에 액세스하려면 도움말 단추를 클릭합니다.

## <a name="see-also"></a>참고 항목

[SQL Server 데이터 및 로그 파일 배치](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)