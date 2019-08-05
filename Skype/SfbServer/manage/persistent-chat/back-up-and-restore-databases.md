---
title: 영구 채팅 데이터베이스 백업 및 복원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 데이터베이스를 백업 하 고 복원 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 0bb4895ef85ac9f38f2f9ef414769efcac6894b4
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "36197873"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>영구 채팅 데이터베이스 백업 및 복원
 
**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 데이터베이스를 백업 하 고 복원 하는 방법에 대해 알아봅니다.
  
영구 채팅 서버에는 기록 및 콘텐츠, 구성, 사용자 프로비저닝, 기타 관련 메타 데이터 등의 채팅방 데이터를 저장 하는 SQL Server 데이터베이스 소프트웨어가 필요 합니다. 또한 조직에 영구 채팅 작업을 보관 해야 하는 규정이 있고 선택적 준수 서비스를 사용 하는 경우 SQL Server 데이터베이스 소프트웨어를 사용 하 여 다음과 같은 채팅 콘텐츠 및 이벤트를 비롯 한 규정 준수 데이터를 저장 합니다. 회의실에 가입/탈퇴 채팅방 콘텐츠는 mgc (영구 채팅 데이터베이스)에 저장 됩니다. 준수 데이터는 준수 데이터베이스 (mgccomp)에 저장 됩니다. 정기적으로 백업 해야 하는 비즈니스에 중요 한 데이터입니다. 
  
> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다. 

## <a name="back-up-the-databases"></a>데이터베이스 백업

영구 채팅 데이터를 백업 하는 방법에는 두 가지가 있습니다. 
  
- SQL Server 백업
    
- 영구 채팅 데이터를 파일로 내보내는 **Export-CsPersistentChatData** cmdlet
    
SQL Server 백업을 사용 하 여 만든 데이터에는 **내보내기-CsPersistentChatData** cmdlet에서 만든 것 보다 훨씬 더 많은 디스크 공간이 필요 하지만, sql server 백업은 사용자가 익숙한 프로시저인 일 수 있습니다.
  
SQL Server 백업 절차를 사용 하려는 경우 자세한 내용은 SQL 설명서를 참조 하세요. 
  
**Export-CsPersistentChatData** cmdlet을 사용 하려는 경우 다음과 같이 명령을 지정할 수 있습니다.
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

또는
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

예를 들어 다음 명령은 서버 atl-sql-001.contoso.com에 있는 영구 채팅 데이터베이스에서 영구 채팅 데이터를 내보냅니다. 내보낸 데이터는 파일 C:\Logs\PersistentChatData.zip.에 저장 됩니다. Level 매개 변수가 지정 되지 않았으므로이 명령은 영구 채팅 정보를 전체적으로 내보냅니다.
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>데이터베이스 복원

영구 채팅 데이터를 복원 하는 방법은 백업 하는 데 사용한 방법에 따라 다릅니다. SQL Server 백업 절차를 사용 하는 경우 SQL Server restore 프로시저를 사용 해야 합니다. **CsPersistentChatData** cmdlet을 사용 하 여 영구 채팅 데이터를 백업한 경우 **CsPersistentChatData** cmdlet을 사용 하 여 데이터를 복원 해야 합니다.
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

또는
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
