---
title: Skype 룸 시스템 및 비즈니스용 Skype 파트너
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
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 이 항목을 통해 페더러니트 파트너를 위한 Skype 룸 시스템을 설정하는 비즈니스용 Skype 방법을 참조하세요.
ms.openlocfilehash: 57c143559af533e1a2a8ef6577a1fe6e9f9de660
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771670"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 룸 시스템 및 비즈니스용 Skype 파트너
 
이 항목을 통해 페더러니트 파트너를 위한 Skype 룸 시스템을 설정하는 비즈니스용 Skype 방법을 참조하세요.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 룸 시스템 및 비즈니스용 Skype 파트너

Skype 회의실 시스템은 일정 모임 요청의 비즈니스용 Skype 모임 참가 링크를 사용 합니다. 참가 링크는 일반적으로 모임 요청 본문에 있습니다. 그러나 Skype Room System은 이 링크가 메시지의 MAPI 속성에 존재해야 합니다. 이 모임 요청이 원격 조직(비즈니스용 Skype 페더링 파트너)에게 전송되는 경우 기본적으로 원격 조직의 Skype 회의실 시스템에는 일정에 모임 참가 링크가 표시되지 않습니다. 실제로 원격 Outlook 사용자가 일정 항목을 마우스 오른쪽 단추로 클릭하거나 모임 미리 알림 내에서 비즈니스용 Skype 모임에 참가할 수 없습니다. 모임 초대를 열고 메시지 비즈니스용 Skype 모임에 참가를 클릭해야 합니다. 
  
이러한 제한의 이유는 Outlook Microsoft Exchange 특수한 방법을 사용하여 인터넷을 통해 메시지를 보내기 위한 정보를 패키지로 만들지 못하기 위한 것입니다. TNEF(Transport Neutral Encapsulation Format)라고 하는 이 메서드는 조직 외부에서 보낸 메시지에 대해 기본적으로 Exchange 사용하지 않도록 설정됩니다. 모임 참가 링크가 원격 Skype 회의실 시스템에 표시하려면 보내는 조직에서 다음 명령을 사용하여 TNEF를 사용하도록 설정해야 합니다.
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

원격 조직에 대해 TNEF를 사용하도록 설정하면 인터넷을 통해 조직으로 전송된 모든 메시지가 TNEF 형식의 첨부 파일로 전송됩니다. TNEF를 사용하도록 설정하면 비즈니스용 Skype 모임 요청이 비즈니스용 Skype 페더링 파트너에게 전송되면 Skype 회의실 시스템에서 비즈니스용 Skype 모임 참가를 렌더링할 수 있으며 원격 사용자는 비즈니스용 Skype 모임에 참가할 수 있습니다. 
