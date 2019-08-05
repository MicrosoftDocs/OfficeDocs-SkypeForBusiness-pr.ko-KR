---
title: 비즈니스용 Skype 서버에서 AlwaysOn 가용성 그룹을 사용 하 여 데이터베이스 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '요약: 기존 AlwaysOn 가용성 그룹에 비즈니스용 Skype 서버 데이터베이스를 추가 하는 방법에 대해 알아보고, Skype에서 AlwaysOn 가용성 그룹의 일부인 백 엔드 서버를 패치 또는 업그레이드 한 후 필요한 추가 단계에 대해 알아보세요. 비즈니스 서버.'
ms.openlocfilehash: c6d8877448a68aa2331f3c290170418f6dca08ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187107"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 AlwaysOn 가용성 그룹을 사용 하 여 데이터베이스 관리

비즈니스용 Skype Server의 기존 AlwaysOn 가용성 그룹에 비즈니스용 Skype 서버 데이터베이스를 추가 하 고 AlwaysOn의 일부인 백 엔드 서버를 패치 또는 업그레이드 한 후 필요한 추가 단계에 대 한 자세한 내용을 보려면이 문서의 단계를 사용 합니다. 비즈니스용 Skype 서버의 가용성 그룹.

## <a name="add-databases-to-an-alwayson-availability-group"></a>AlwaysOn 가용성 그룹에 데이터베이스 추가 

1. SQL Server Management Studio를 열고 AlwaysOn 가용성 그룹으로 이동 합니다. 주 복제본으로 장애 조치를 수행 합니다.
    
2. 토폴로지 작성기에서 AlwaysOn 가용성 그룹의 SQL Server FQDN을 해당 그룹의 주 노드의 FQDN으로 설정 합니다.
    
   - 토폴로지 작성기를 열고 **기존 배포에서 토폴로지 다운로드**를 선택한 다음 **확인**을 클릭 합니다.
    
   - 비즈니스용 Skype 서버를 확장 하 고, 토폴로지를 확장 하 고, **SQL Server 스토어**를 확장 합니다. 새 AlwaysOn 가용성 그룹의 SQL 저장소를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.
    
   - 페이지의 맨 아래에 있는 **SQL SERVER FQDN** 상자에 AlwaysOn 가용성 그룹의 기본 노드에 대 한 FQDN을 입력 합니다.
    
3. 토폴로지를 게시 합니다. **작업** 메뉴에서 **토폴로지** , **게시**를 차례로 클릭 합니다. 확인 페이지에서 **다음**을 클릭 합니다.
    
4. SQL Server Management Studio를 사용 하 여 AlwaysOn 가용성 그룹에 새 데이터베이스를 추가 합니다.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>AlwaysOn 가용성 그룹에서 SQL Server 패치 또는 업데이트

AlwaysOn 가용성 그룹의 일부인 백 엔드 서버를 패치 한 후에는 토폴로지를 다시 게시 해야 합니다.

1. 비즈니스용 Skype 서버 또는 서버에 업데이트를 설치 합니다.
    
2. 다음과 같이 비즈니스용 Skype 관리 셸에서 다음 PowerShell 명령을 실행 합니다 (SQL AlwaysOn 데이터베이스에 변경 내용을 적용 하도록 적절 하 게 permissioned 된 계정으로 로그인).
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    여기서 [sqlpool.contoso.com]는 AlwaysOn 가용성 그룹의 FQDN (정규화 된 도메인 이름)으로 대체 됩니다.
