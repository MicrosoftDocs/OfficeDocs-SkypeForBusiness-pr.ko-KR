---
title: Skype 대화방 시스템 계정 관리
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Skype 대화방 시스템 계정을 관리 하는 방법에 대해 알아보려면이 항목을 읽으십시오.
ms.openlocfilehash: b6d61f4ddc9fe5e296ffd98b685e1000151d5db2
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768661"
---
# <a name="manage-skype-room-system-accounts"></a>Skype 대화방 시스템 계정 관리
 
Skype 대화방 시스템 계정을 관리 하는 방법에 대해 알아보려면이 항목을 읽으십시오. 

> [!NOTE]
> Microsoft 팀 대화방은 서로 다른 종속성 및 배포 절차와 다른 제품입니다. Microsoft 팀 대화방에 대 한 자세한 내용은 Microsoft 팀 대화방 [관리 개요](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)를 참조 하세요.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>풀 간에 Skype 대화방 시스템 계정 이동

Skype 대화방 시스템 계정을 한 대의 비즈니스용 Skype 서버 풀에서 다른 서버로 이동 해야 하는 경우 (예: 업그레이드 중) 다음 명령을 사용 하 여 Skype 대화방 시스템 계정 풀을 이동 합니다. 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>비즈니스용 Skype 서비스의 Skype 대화방 시스템 계정 사용 중지

비즈니스용 skype Server 풀의 비즈니스용 Skype 서비스에서 기존 Skype 대화방 시스템 계정을 사용 하지 않도록 설정 해야 하는 경우 다음 명령을 사용 하 여 계정을 사용 하지 않도록 설정 합니다. 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>선택 사항: Active Directory에서 Skype 채팅방 시스템 관리자 그룹 만들기

도메인에 가입한 각 Skype 룸 시스템 클라이언트는 Skype 룸 시스템 기기 PC에 대 한 로컬 관리자 권한이 있는 도메인 사용자에 의해 완전히 관리 될 수 있습니다. 따라서 Active Directory에 전용 관리자 그룹을 만들고 새 Skype 채팅방 시스템 시스템 설정 중에이 그룹의 관리자 권한을 부여할 수 있습니다.
  

