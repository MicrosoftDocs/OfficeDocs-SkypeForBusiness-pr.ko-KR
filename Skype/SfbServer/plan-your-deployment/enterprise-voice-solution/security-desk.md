---
title: 보안 데스크를 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: 조직의 보안 데스크를 E9-1-1 배포에 포함하는 방법을 계획하는 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 63c54bb5cec1b81cfd8783a77ea3a685982a1b9e2e6040bf78880d32c9d1ab56
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290016"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>보안 데스크를 비즈니스용 Skype 서버
 
조직의 보안 데스크를 E9-1-1 배포에 포함하는 방법을 계획하는 비즈니스용 Skype 서버 Enterprise Voice.
  
회사에서 긴급 통화를 처리하기 위한 보안 데스크가 필요한 경우가 있습니다. E9-1-1 배포에 보안 데스크를 통합하는 방법을 결정하려면 다음과 같은 사항을 고려해야 합니다.
  
**긴급 통화가 있는 경우 보안 데스크에 알림을 보낼지 여부**
  
하나 이상의 보안 비즈니스용 Skype 서버 SIP 주소로 IM(인스턴트 메시징) 비즈니스용 Skype 보내도록 위치 정책을 구성할 수 있습니다. 이러한 경고는 긴급 통화를 거는 사용자의 이름, 번호 및 위치를 포함하며 보안 담당자가 긴급 상황을 지원하는 데 도움이 됩니다.
    
**각 긴급 통화에 대해 보안 데스크와 전화 회의를 할지 여부**
  
긴급 서비스 공급자에서 지원되는 경우 각 긴급 통화에 콜백 번호를 포함하도록 위치 정책을 구성할 수 있습니다. 이 번호는 공급자가 조직의 보안 담당자를 긴급 통화에 참조로 포함하는 데 사용됩니다. 이러한 참조는 위치 정책에서 단방향(듣기만) 또는 양방향으로 구성할 수 있습니다.
    
> [!NOTE]
> 필요에 따라 각 위치 정책에 대해 서로 다른 긴급 담당자를 구성할 수 있습니다. 이렇게 하면 회사 내 여러 영역에 대한 응답성을 사용자 지정하거나, 내부의 긴급 통화와 네트워크 외부의 긴급 통화에 대해 서로 다른 동작을 만들 수 있습니다. 메일 그룹을 사용해서 알림을 제공할 담당자를 지정할 수 있습니다. 
  

