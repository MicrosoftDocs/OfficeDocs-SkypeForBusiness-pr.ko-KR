---
title: XMPP 게이트웨이 액세스 정책 및 인증서 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: XMPP 페더레이션은 XMPP(eXtensible Messaging and Presence Protocol)에 따라 외부 배포를 정의합니다. XMPP 구성을 사용하면 사용자가 XMPP 도메인 사용자에 액세스할 수 있습니다.
ms.openlocfilehash: c442d0c4f5b5443e378be5afc031f7489860e42a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594308"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>XMPP 게이트웨이 액세스 정책 및 인증서 구성

XMPP 페더레이션은 XMPP(eXtensible Messaging and Presence Protocol)에 따라 외부 배포를 정의합니다. XMPP 구성을 사용하면 사용자가 XMPP 도메인 사용자에 액세스할 수 있습니다.
  
- IM 및 현재 상태 - 개인만
    
- 비즈니스용 Skype 클라이언트에서 XMPP 페더러드 연락처 만들기
    
XMPP 페더럴 파트너 지원 정책을 구성하면 해당 정책은 XMPP 페더임 도메인의 사용자에게는 적용되지만 SIP(Session Initiation Protocol) IM(인스턴트 메시징) 서비스 공급자 또는 SIP 페더럴 도메인의 사용자에게는 적용되지 않습니다. 사용자가 연락처를 추가하고 통신할 수 있도록 허용할 각 XMPP 페더럴 도메인에 대해 XMPP 페더럴 파트너를 구성합니다. 정책을 만들었으면 XMPP 게이트웨이 인증서를 구성해야 합니다. 
  
> [!NOTE]
> XMPP 기능은 비즈니스용 Skype 서버 2019에서 더 이상 사용되지 않지만 레거시 서버에서는 비즈니스용 Skype 서버 2019와 함께 사용할 수 있습니다. 레거시 서버(비즈니스용 Skype 서버 2015/Lync Server 2013) XMPP 게이트웨이를 이미 배포하고 사용자가 레거시 XMPP 게이트웨이를 사용할 수 있도록 액세스 정책을 구성해야 합니다. 자세한 내용은 [Migrating XMPP Federation 을 참조합니다.](migrating-xmpp-federation.md) 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>사용자가 레거시 XMPP 게이트웨이를 사용할 수 있도록 외부 액세스 정책 구성

1. 레거시 제어판을 비즈니스용 Skype 서버 를 니다.
    
2. 왼쪽 탐색 모음에서 **Federation and External Access(페더레이션 및 외부 액세스)** 를 클릭하고 **외부 액세스 정책** 을 클릭합니다.
    
3. **새로 만들기** 를 클릭하고 **사용자 정책** 을 클릭합니다.
    
4. 외부 액세스 사용자 정책의 이름을 입력합니다.
    
5. 외부 액세스 사용자 정책에 대한 설명을 입력합니다.
    
6. **페더레이션 사용자와의 통신 사용** 을 선택합니다.
    
7. Select **Enable communications with XMPP federated users(XMPP 페더레이션 사용자와의 통신 사용)** 을 선택합니다.
    
8. **커밋** 을 클릭하여 사이트 또는 사용자 정책에 대한 변경 내용을 저장합니다. 
    

