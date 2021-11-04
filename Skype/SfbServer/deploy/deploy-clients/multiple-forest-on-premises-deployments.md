---
title: Skype Room System 다중 포리스트 사내 배포
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: 이 항목을 통해 다중 포리스트 Skype 환경에서 룸 시스템을 배포하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 49885d1e64c40f161eb0fc07ec79187b5ea3bdb1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761586"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype Room System 다중 포리스트 사내 배포
 
이 항목을 통해 다중 포리스트 Skype 환경에서 룸 시스템을 배포하는 방법을 배울 수 있습니다.
  
> [!NOTE]
> 여러 포리스트에 배포하려면 Skype Room System을 사용하려면 2014년 8월 26일 Exchange Server 2013 CU6이 필요합니다. 기존 사서함을 Room System에 다시 Skype 않습니다. Room System에 대해 새(이전 사서함 삭제 및 다시 만들기) 리소스 Skype 사용 사서함을 삭제하여 손실된 모임을 복원하려면 [삭제된 커넥트 복원을 참조합니다.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
사서함을 만들고 나면 사서함을 Set-CalendarProcessing 수 있습니다. 자세한 내용은 Single forest on-premises deployments에서 3-6단계를 참조하세요. Exchange Room System에 Exchange Skype 리소스 사서함을 만들고 나면 단일 포리스트 비즈니스용 Skype 배포에서 Skype Room System 계정 사용의 단계에 따라 비즈니스용 Skype 계정을 사용하도록 설정하십시오.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>옵션 1: 새 리소스 사서함 만들기

다중 Skype Room System을 배포하는 경우:
  
1. Active Directory(인증 포리스트)에서 연결된 사용자(LinkedRoomTest)를 만들 수 있습니다.
    
2. 관리 셸의 Exchange Server 실행합니다.
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>옵션 2: 기존 방 사서함을 연결된 Skype 사서함으로 변경

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```