---
title: 데이터베이스 설치 및 만들기
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: 배포용으로 만들 데이터베이스를 선택합니다. 기본적으로 데이터베이스는 정의된 사이트의 정의된 SQL Server 만들어지며 데이터베이스를 배치하는 SQL Server 데이터베이스 파일을 자동으로 배포 및 구성합니다.
ms.openlocfilehash: 9dd5e0f0ce800489ab937feae1cda68809540d81
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849111"
---
# <a name="install-and-create-databases"></a>데이터베이스 설치 및 만들기

배포용으로 만들 데이터베이스를 선택합니다. 기본적으로 데이터베이스는 정의된 사이트의 정의된 SQL Server 만들어지며 데이터베이스를 배치하는 SQL Server 데이터베이스 파일을 자동으로 배포 및 구성합니다.

 **만들려는 데이터베이스 선택**: 배포 및 구성하려는 데이터베이스의 확인란을 선택합니다. 배포하려는 임의의 데이터베이스 또는 모든 데이터베이스 확인란을 선택합니다.

> [!CAUTION]
> 데이터베이스가 SQL Server 인스턴스에 대해 이미 구성된 경우 방화벽 포트를 열고 데이터베이스를 배포하는 인스턴스를 수용해야 합니다. 자세한 내용은 [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)

 **고급:** 사용자 SQL Server 클릭하고 고급  단추를 클릭하여 데이터베이스 파일 위치에 대한 옵션을 SQL Server. 고급 데이터베이스 파일 배치에 대한 자세한 내용은 [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)를 참조하십시오.

 **뒤로**: 이 단추를 클릭하면 이전 화면으로 돌아갑니다(이 대화 상자를 표시한 방법에 따라 항상 활성화되지는 않을 수도 있음).

 **다음**: 이 단추를 클릭하면 현재 대화 상자의 선택 내용이 커밋되고 추가 정보 구성을 위해 다음 대화 상자로 이동합니다.

 **취소**: 이 단추를 클릭하면 구성이 종료되고 변경 내용이 취소됩니다. 일부 구성 화면(모두는 아님)에서는 구성을 종료하고 변경 내용을 취소할지를 묻는 메시지가 표시됩니다. 예를 **선택하면** 현재 구성이 닫히고 현재 구성이 닫히고 토폴로지 작성기로 돌아오게 됩니다. **아니요** 를 선택하면 현재 구성 대화 상자로 돌아가며 구성을 계속할 수 있습니다.

 **도움말**: **도움말** 단추를 클릭하면 현재 구성 대화 상자와 연결된 이 도움말 정보가 표시됩니다.