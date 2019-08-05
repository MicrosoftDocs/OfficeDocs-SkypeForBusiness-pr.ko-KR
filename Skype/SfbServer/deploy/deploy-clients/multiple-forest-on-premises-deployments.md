---
title: Skype 대화방 시스템 다중 포리스트 온-프레미스 배포
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: 이 항목에서는 다중 포리스트 온-프레미스 환경에서 Skype 대화방 시스템을 배포 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: ae51ac035ef618464f408cb3f068e142eb67f2f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196385"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype 대화방 시스템 다중 포리스트 온-프레미스 배포
 
이 항목에서는 다중 포리스트 온-프레미스 환경에서 Skype 대화방 시스템을 배포 하는 방법에 대해 알아봅니다.
  
> [!NOTE]
> 여러 포리스트에 배포 하기 위해 Skype 채팅방 시스템에는 2014 년 8 월 26 일에 릴리스된 Exchange Server 2013 CU6이 필요 합니다. Skype 채팅방 시스템용 기존 사서함을 다시 사용 하지 마세요. Skype 대화방 시스템용 새 (이전 사서함 삭제 및 다시 만들기) 리소스 사서함을 사용 합니다. 사서함을 삭제 하 여 손실 된 모임을 복원 하려면 [삭제 된 사서함 연결 또는 복원을](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)참조 하세요. 
  
사서함을 만든 후에는 설정-CalendarProcessing을 사용 하 여 사서함을 구성할 수 있습니다. 자세한 내용은 단일 포리스트 온-프레미스 배포에서 3 ~ 6 단계를 참조 하세요. Skype 채팅방 시스템에 대 한 Exchange 리소스 사서함을 만든 후 비즈니스용 skype의 skype 대화방 시스템 계정 활성화의 단계에 따라 단일 포리스트 온-프레미스 배포 아래에서 비즈니스용 Skype에 대 한 계정을 사용 하도록 설정 합니다.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>옵션 1: 새 리소스 사서함 만들기

다중 포리스트 환경에서 Skype 실 시스템을 배포 하려면 다음을 수행 합니다.
  
1. Active Directory (인증 포리스트)에서 연결 된 사용자 (LinkedRoomTest)를 만듭니다.
    
2. Exchange Server Management Shell에서 다음 명령을 실행 합니다.
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>옵션 2: 기존 회의실 사서함을 Skype 대화방 시스템 (연결) 리소스 사서함으로 변경

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


