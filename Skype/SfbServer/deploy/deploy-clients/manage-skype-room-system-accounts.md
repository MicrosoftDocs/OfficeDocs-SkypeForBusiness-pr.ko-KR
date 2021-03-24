---
title: Skype 룸 시스템 계정 관리
ms.author: v-cichur
author: cichur
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
description: 이 항목을 읽고 Skype 채팅방 시스템 계정을 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: e6b905b065badb729ccc9281d63ba050fc032ef2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093296"
---
# <a name="manage-skype-room-system-accounts"></a>Skype 룸 시스템 계정 관리
 
이 항목을 읽고 Skype 채팅방 시스템 계정을 관리하는 방법을 배워야 합니다. 

> [!NOTE]
> Microsoft Teams 룸은 종속성 및 배포 절차가 서로 다른 제품입니다. Microsoft Teams 룸에 대한 자세한 내용은 Microsoft Teams 룸 관리 [개요 를 참조하세요.](/microsoftteams/rooms/rooms-manage)
  
## <a name="move-the-skype-room-system-account-between-pools"></a>풀 간에 Skype 룸 시스템 계정 이동

업그레이드 중과 같이 비즈니스용 Skype 서버 풀에서 다른 풀로 Skype 룸 시스템 계정을 이동해야 하는 경우 다음 명령을 사용하여 Skype 룸 시스템 계정 풀을 이동합니다. 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>비즈니스용 Skype 서비스에 대해 Skype 룸 시스템 계정을 사용하지 않도록 설정

비즈니스용 Skype 서버 풀의 비즈니스용 Skype 서비스에서 기존 Skype 룸 시스템 계정을 사용하지 않도록 설정해야 하는 경우 다음 명령을 사용하여 계정을 사용하지 않도록 설정합니다. 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>선택 사항: Active Directory에서 Skype 룸 시스템 관리자 그룹 만들기

도메인에 가입하는 각 Skype 룸 시스템 클라이언트는 Skype 룸 시스템 어플라이언스 PC에서 로컬 관리자 권한이 있는 도메인 사용자가 완전히 관리할 수 있습니다. 따라서 Active Directory에서 전용 관리자 그룹을 만들고 새 Skype 룸 시스템 컴퓨터 설정 중에 이 그룹에 관리 권한을 줄 수 있습니다.
