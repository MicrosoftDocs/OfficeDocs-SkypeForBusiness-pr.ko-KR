---
title: 공통 영역 전화 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 공통 영역 전화는 공유 작업 영역 또는 일반적인 영역 (예를 들어, 로비, 주방 또는 공장 바닥)에 있는 IP 전화입니다. 공통 영역 전화를 컴퓨터에 연결 하 여 비즈니스용 Skype UC (통합 통신) 기능을 제공할 필요는 없습니다. 배포를 비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 레거시 공통 영역 전화와 연결 된 대화 상대 개체도 마이그레이션해야 합니다. 비즈니스용 Skype 서버 관리 셸을 사용 하 여 먼저 레거시 공통 영역 전화와 연결 된 모든 대화 상대 개체를 검색 한 후 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752710"
---
# <a name="migrate-common-area-phones"></a>공통 영역 전화 마이그레이션

공통 영역 전화는 공유 작업 영역 또는 일반적인 영역 (예를 들어, 로비, 주방 또는 공장 바닥)에 있는 IP 전화입니다. 공통 영역 전화를 컴퓨터에 연결 하 여 비즈니스용 Skype UC (통합 통신) 기능을 제공할 필요는 없습니다. 배포를 비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 레거시 공통 영역 전화와 연결 된 대화 상대 개체도 마이그레이션해야 합니다. 비즈니스용 Skype 서버 관리 셸을 사용 하 여 먼저 레거시 공통 영역 전화와 연결 된 모든 대화 상대 개체를 검색 한 후 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.
  
### <a name="migrate-common-area-phones"></a>공통 영역 전화 마이그레이션

1. 비즈니스용 skype 서버 2019 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
2. 명령줄에 다음을 입력합니다.
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. 비즈니스용 Skype 서버 관리 셸에서 모든 대화 상대 개체가 비즈니스용 Skype 서버 2019 풀로 이동 되었는지 확인 하려면 다음을 입력 합니다.
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    모든 대화 상대 개체가 이제 비즈니스용 Skype 서버 2019 풀과 연결 되어 있는지 확인 합니다.
    

