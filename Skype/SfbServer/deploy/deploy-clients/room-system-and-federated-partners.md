---
title: Skype 실 시스템 및 비즈니스용 Skype 페더레이션 파트너
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
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 이 항목에서는 비즈니스용 Skype 페더레이션 파트너를 위해 Skype 대화방 시스템을 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d5ee83857aa439791e2a31ef201e0f365dbb8408
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768721"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 실 시스템 및 비즈니스용 Skype 페더레이션 파트너
 
이 항목에서는 비즈니스용 Skype 페더레이션 파트너를 위해 Skype 대화방 시스템을 설정 하는 방법에 대해 알아봅니다.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 실 시스템 및 비즈니스용 Skype 페더레이션 파트너

Skype 대화방 시스템은 일정 모임 요청에서 비즈니스용 Skype 모임 참가 링크에 의존 합니다. 참가 링크는 일반적으로 모임 요청 본문에 있습니다. 그러나, Skype 룸 시스템은 메시지의 MAPI 속성에이 링크를 통해 제공 됩니다. 이 모임 요청이 원격 조직에 전송 되는 경우 (비즈니스용 Skype 페더레이션 파트너) 기본적으로 원격 조직의 Skype 대화방 시스템에는 일정의 모임 참가 링크가 표시 되지 않습니다. 사실, 원격 조직의 Outlook 사용자는 일정 항목을 마우스 오른쪽 단추로 클릭 하거나 모임 미리 알림에서 내 비즈니스용 Skype 모임에 참가할 수 없습니다. 모임 초대를 열고 메시지 본문에서 비즈니스용 Skype 모임 참가를 클릭 해야 합니다. 
  
이는 Outlook과 Microsoft Exchange에서 인터넷을 통해 메시지를 보내는 데 필요한 정보를 패키지 하는 데 특별 한 방법을 사용 하지 않기 때문에 제한 사항이 있습니다. 이 메서드는 Exchange 조직에서 외부적으로 보낸 메시지에 대해 기본적으로 사용 하지 않도록 설정 되어 전송 중립 캡슐화 형식 (TNEF) 이라고 합니다. 원격 Skype 채팅방 시스템에 모임 참가 링크가 표시 되려면 다음 명령을 사용 하 여 보내는 조직이 TNEF를 사용 하도록 설정 해야 합니다.
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

원격 조직에 TNEF를 사용 하도록 설정 하면 인터넷을 통해 조직에 게 보내는 모든 메시지가 TNEF 형식의 첨부 파일로 전송 됩니다. TNEF를 사용 하도록 설정 하면 비즈니스용 skype 모임 요청이 비즈니스용 skype 페더레이션 파트너로 전송 될 때 Skype 대화방 시스템에서 비즈니스용 Skype 모임에 참가할 수 있으며, 원격 사용자는 비즈니스용 Skype 모임에 참가할 수 있습니다. 
