---
title: XMPP 게이트웨이 액세스 정책 및 인증서 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: XMPP federation는 XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜)를 기반으로 외부 배포를 정의 합니다. XMPP 구성을 사용 하면 사용자가 다음과 같은 방법으로 XMPP 도메인 사용자에 게 액세스할 수 있습니다.
ms.openlocfilehash: 8182153bf3633b2392969f5870a7d5b96471d4fb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813766"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>XMPP 게이트웨이 액세스 정책 및 인증서 구성

XMPP federation는 XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜)를 기반으로 외부 배포를 정의 합니다. XMPP 구성을 사용 하면 사용자가 다음과 같은 방법으로 XMPP 도메인 사용자에 게 액세스할 수 있습니다.
  
- 메신저 대화 및 현재 상태-사람 에게만
    
- 비즈니스용 Skype 클라이언트에서 XMPP 페더레이션 대화 상대 만들기
    
XMPP 페더레이션 파트너에 대 한 지원을 위해 정책을 구성할 때 정책은 XMPP 페더레이션 도메인의 사용자에 게 적용 되지만 SIP (세션 초기화 프로토콜) 서비스 공급자 또는 SIP 페더레이션 도메인의 사용자에 게는 적용 되지 않습니다. 사용자가 연락처를 추가 하 고 통신 하는 데 사용할 각 XMPP 페더레이션 도메인에 대해 XMPP 페더레이션 파트너를 구성 합니다. 정책이 설정 되 면 XMPP 게이트웨이 인증서를 구성 해야 합니다. 
  
> [!NOTE]
> XMPP 기능은 비즈니스용 Skype 서버 2019에서 사용 되지 않지만 비즈니스용 Skype Server 2019와 함께 사용할 경우 레거시 서버에서 계속 될 수 있습니다. 레거시 서버 (비즈니스용 Skype Server 2015/Lync Server 2013) XMPP 게이트웨이를 이미 배포 했으며, 레거시 XMPP 게이트웨이에 대 한 사용자를 사용할 수 있도록 액세스 정책을 구성 했는지 확인 합니다. 자세한 내용은 [XMPP 페더레이션 마이그레이션을](migrating-xmpp-federation.md)참조 하세요. 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>레거시 XMPP 게이트웨이에 대 한 사용자를 사용할 수 있도록 외부 액세스 정책 구성

1. 레거시 비즈니스용 Skype Server 제어판을 엽니다.
    
2. 왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.
    
3. **새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다.
    
4. 외부 액세스 사용자 정책의 이름을 입력 합니다.
    
5. 외부 액세스 사용자 정책에 대 한 설명을 입력 합니다.
    
6. **페더레이션 사용자와의 통신 사용**을 선택 합니다.
    
7. **XMPP 페더레이션 사용자와 통신 사용을**선택 합니다.
    
8. **커밋을** 클릭 하 여 사이트 또는 사용자 정책의 변경 내용을 저장 합니다. 
    

