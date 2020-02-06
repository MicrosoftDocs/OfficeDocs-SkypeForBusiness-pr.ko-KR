---
title: SQL 저장소 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: SQL Server 데이터베이스의 속성을 편집 하려면 SQL Server 데이터베이스 인스턴스를 변경 해야 합니다. 속성 편집 대화 상자를 사용 하 여 보관 서버 데이터베이스를 한 컴퓨터에서 다른 컴퓨터로 이동 하는 등의 작업을 수행할 수는 없습니다. 또한 속성 편집 대화 상자를 사용 하 여 중앙 관리 저장소를 호스트 하는 SQL Server 인스턴스를 변경할 수 없습니다.
ms.openlocfilehash: 654b1727badf9c0f08bcab9e181b301b72bd1299
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819200"
---
# <a name="sql-store-settings-expander"></a>SQL 저장소 설정 확장기
 
SQL Server 데이터베이스의 속성을 편집 하려면 SQL Server 데이터베이스 인스턴스를 변경 해야 합니다. **속성 편집** 대화 상자를 사용 하 여 보관 서버 데이터베이스를 한 컴퓨터에서 다른 컴퓨터로 이동 하는 등의 작업을 수행할 수는 없습니다. 또한 **속성 편집** 대화 상자를 사용 하 여 중앙 관리 저장소를 호스트 하는 SQL Server 인스턴스를 변경할 수 없습니다.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>SQL Server 데이터베이스의 속성 편집

중앙 관리 저장소 이외의 다른 데이터베이스에서 사용 하는 SQL Server 인스턴스를 변경 하려면 토폴로지 작성기에서 다음 절차를 완료 합니다.
  
### <a name="to-modify-an-instance-of-sql-server"></a>SQL Server 인스턴스를 수정 하려면

1. **SQL 저장소** 노드에서 해당 데이터베이스를 선택한 다음 **속성 편집**을 클릭 합니다.
    
2. **속성 편집** 대화 상자에서 다음 중 하나를 수행 합니다.
    
   - 기본 SQL Server 인스턴스를 사용 하려면 **기본 인스턴스** 를 선택 하 고 **확인**을 클릭 합니다.
    
   - 명명 된 데이터베이스 인스턴스를 사용 하려면 **명명 된 인스턴스**를 선택 하 고 텍스트 상자에 인스턴스 이름을 입력 한 다음 **확인**을 클릭 합니다. 전체 SQL Server 경로가 아닌 인스턴스 이름 (예: ArchivingInstance)만 입력 해야 합니다.
    
**속성 편집** 대화 상자에서 작업 하는 경우 토폴로지 작성기는 입력 한 데이터베이스 인스턴스가 유효한 인스턴스인지 확인 하지 않습니다. 예를 들어 실수로 인스턴스 이름을 typeArchivingInstanec **확인**을 클릭 하면 토폴로지 작성기에서 해당 잘못 된 인스턴스를 허용 합니다. 이 토폴로지를 게시 하기 전에이 오류를 수정 해야 합니다. SQL Server 인스턴스를 찾을 수 없는 경우에는 토폴로지 작성기가 해당 인스턴스를 만들지 않습니다.
  

