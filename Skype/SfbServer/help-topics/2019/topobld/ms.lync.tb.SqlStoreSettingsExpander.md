---
title: SQL 저장소 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: 데이터베이스 데이터베이스의 속성을 SQL Server 데이터베이스 인스턴스를 SQL Server 합니다. 속성 편집 대화 상자를 사용하여 컴퓨터 간에 보관 서버 데이터베이스를 이동하는 등의 작업을 수행할 수는 없습니다. 또한 속성 편집 대화 상자를 사용하여 중앙 관리 저장소를 호스팅하는 SQL Server 인스턴스를 변경할 수 없습니다.
ms.openlocfilehash: 96eeb4302bd904fe3622e7135d34d374f56766e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805518"
---
# <a name="sql-store-settings-expander"></a>SQL 저장소 설정 확장기
 
데이터베이스 데이터베이스의 속성을 편집하려면 SQL Server 데이터베이스 인스턴스를 SQL Server 합니다. **속성 편집** 대화 상자를 사용하여 컴퓨터 간에 보관 서버 데이터베이스를 이동하는 등의 작업을 수행할 수는 없습니다. 또한 속성 편집 대화  상자를 사용하여 중앙 관리 저장소를 호스팅하는 SQL Server 인스턴스를 변경할 수 없습니다.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>데이터베이스의 속성 SQL Server 편집

중앙 관리 저장소가 SQL Server 데이터베이스 인스턴스를 변경하려면 토폴로지 작성기에서 다음 절차를 완료합니다.
  
### <a name="to-modify-an-instance-of-sql-server"></a>인스턴스를 수정하려면 SQL Server

1. **SQL 저장소** 노드 아래에서 적절한 데이터베이스를 선택한 다음 **속성 편집** 을 클릭합니다.
    
2. **속성 편집** 대화 상자에서 다음 중 하나를 수행합니다.
    
   - 기본 인스턴스를 SQL Server 기본 인스턴스를 선택하고 확인을 **클릭합니다.** 
    
   - 명명된 데이터베이스 인스턴스를 사용하려면 **명명된 인스턴스** 를 선택하고 텍스트 상자에 인스턴스 이름을 입력한 다음 **확인** 을 클릭합니다. 전체 인스턴스 이름(예: ArchivingInstance)만 입력해야 합니다. 전체 인스턴스 경로는 SQL Server 않습니다.
    
속성 편집 대화  상자에서 작업하는 경우 토폴로지 작성기에서 입력한 데이터베이스 인스턴스가 유효한 인스턴스가 아닌지 확인하지 않습니다. 예를 들어 잘못 인스턴스 이름으로ArchivingInstanec를 입력한 다음 확인을 클릭하면 토폴로지 작성기에서 해당 잘못된 인스턴스를 허용합니다. 이 토폴로지 게시를 위해 먼저 이 실수를 수정해야 합니다. SQL Server 인스턴스를 찾을 수 없는 경우 토폴로지 작성기에서 해당 인스턴스를 만들지 않습니다.
  

