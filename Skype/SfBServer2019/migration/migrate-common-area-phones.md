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
description: 공통 영역 전화는 공유 작업 영역이나 공용 영역(로비, 부엌 또는 공장 층)에 가장 자주 상주하는 IP 전화입니다. UC(비즈니스용 Skype 서버 통합 통신) 기능을 제공하기 위해 공통 영역 전화는 컴퓨터에 연결할 필요가 없습니다. 비즈니스용 Skype 서버 2019로 배포를 마이그레이션한 후 레거시 공통 영역 전화와 연결된 연락처 개체도 마이그레이션해야 합니다. 비즈니스용 Skype 서버 관리 셸을 사용하면 먼저 레거시 공통 영역 전화와 연결된 모든 연락처 개체를 검색한 다음 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동하게 됩니다.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752710"
---
# <a name="migrate-common-area-phones"></a>공통 영역 전화 마이그레이션

공통 영역 전화는 공유 작업 영역이나 공용 영역(로비, 부엌 또는 공장 층)에 가장 자주 상주하는 IP 전화입니다. UC(비즈니스용 Skype 서버 통합 통신) 기능을 제공하기 위해 공통 영역 전화는 컴퓨터에 연결할 필요가 없습니다. 비즈니스용 Skype 서버 2019로 배포를 마이그레이션한 후 레거시 공통 영역 전화와 연결된 연락처 개체도 마이그레이션해야 합니다. 먼저 비즈니스용 Skype 서버 관리 셸을 사용하여 레거시 공통 영역 전화와 연결된 모든 연락처 개체를 검색한 다음 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동합니다.
  
### <a name="migrate-common-area-phones"></a>공통 영역 전화 마이그레이션

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 여는 경우
    
2. 명령줄에 다음을 입력합니다.
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. 모든 연락처 개체가 비즈니스용 Skype 서버 2019 풀로 이동된지 확인하려면 비즈니스용 Skype 서버 관리 셸에서 다음을 입력합니다.
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    이제 모든 연락처 개체가 비즈니스용 Skype 서버 2019 풀과 연결되어 있는지 확인해야 합니다.
    

