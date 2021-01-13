---
title: 비즈니스용 Skype 서버에서 영구 채팅 데이터베이스 백업 및 복원
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 데이터베이스를 백업 및 복원하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826378"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버에서 영구 채팅 데이터베이스 백업 및 복원
 
**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 데이터베이스를 백업 및 복원하는 방법에 대해 자세히 알아보습니다.
  
영구 채팅 서버에는 기록 및 SQL Server, 구성, 사용자 프로비전 및 기타 관련 메타데이터와 같은 채팅방 데이터를 저장하기 위해 데이터베이스 소프트웨어가 필요합니다. 또한 조직에 영구 채팅 활동을 보관해야 하는 규정이 있는 경우 선택적 준수 서비스를 사용하도록 설정하면 SQL Server 데이터베이스 소프트웨어를 사용하여 채팅 콘텐츠 및 채팅방 참가 및 나가기 등의 규정 준수 데이터를 저장합니다. 채팅방 콘텐츠는 영구 채팅 데이터베이스(mgc)에 저장됩니다. 준수 데이터는 준수 데이터베이스(mgccomp)에 저장됩니다. 정기적으로 백업해야 하는 업무상 중요한 데이터입니다. 
  
> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. Teams에서 동일한 기능을 사용할 수 있습니다. 자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here) 영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다. 

## <a name="back-up-the-databases"></a>데이터베이스 백업

영구 채팅 데이터를 백업하는 방법에는 두 가지가 있습니다. 
  
- SQL Server 백업
    
- 영구 채팅 데이터를 파일로 내보내는 **Export-CsPersistentChatData** cmdlet
    
SQL Server 백업을 사용하여 만든 데이터에는 **Export-CsPersistentChatData** cmdlet에서 만든 것보다 훨씬 더 많은 디스크 공간이 필요하지만 SQL Server 백업은 익숙한 절차일 수 있습니다.
  
백업 절차를 SQL Server 자세한 내용은 SQL 설명서를 참조하십시오. 
  
**Export-CsPersistentChatData** cmdlet을 사용하려는 경우 명령을 다음과 같이 지정할 수 있습니다.
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

또는
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

예를 들어 다음 명령은 서버에 있는 영구 채팅 데이터베이스에서 영구 채팅 데이터를 atl-sql-001.contoso.com. 내보낼 데이터는 파일 형식에 C:\Logs\PersistentChatData.zip. Level 매개 변수를 지정하지 않은 경우 명령은 영구 채팅 정보를 전체 내보낼 수 있습니다.
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>데이터베이스 복원

영구 채팅 데이터를 복원하는 방법은 백업하는 데 사용한 방법에 따라 달라 습니다. 백업 절차를 SQL Server 복원 절차를 SQL Server 합니다. **Export-CsPersistentChatData** cmdlet을 사용하여 영구 채팅 데이터를 백업한 경우 **Import-CsPersistentChatData** cmdlet을 사용하여 데이터를 복원해야 합니다.
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

또는
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
