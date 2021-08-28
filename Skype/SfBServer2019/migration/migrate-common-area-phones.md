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
ms.localizationpriority: medium
description: 공통 영역 전화는 가장 자주 공유 작업 영역이나 공용 영역에 있는 IP 전화(로비, 부엌 또는 공장 층)입니다. UC(통합 통신) 기능을 제공하기 위해 공통 영역 비즈니스용 Skype 서버 연결할 필요가 없습니다. 2019년 비즈니스용 Skype 서버 마이그레이션한 후 레거시 공통 영역 및 연결된 연락처 개체도 마이그레이션해야 전화. 비즈니스용 Skype 서버 관리 셸을 사용하면 먼저 레거시 공통 영역 전화와 연결된 모든 연락처 개체를 검색한 다음 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동하게 됩니다.
ms.openlocfilehash: dabb91925b2d5271ba2760f62dd962ed7fa7a24c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579532"
---
# <a name="migrate-common-area-phones"></a>공통 영역 전화 마이그레이션

공통 영역 전화는 가장 자주 공유 작업 영역이나 공용 영역에 있는 IP 전화(로비, 부엌 또는 공장 층)입니다. UC(통합 통신) 기능을 제공하기 위해 공통 영역 비즈니스용 Skype 서버 연결할 필요가 없습니다. 2019년 비즈니스용 Skype 서버 마이그레이션한 후 레거시 공통 영역 및 연결된 연락처 개체도 마이그레이션해야 전화. 비즈니스용 Skype 서버 관리 셸을 사용하면 먼저 레거시 공통 영역 전화와 연결된 모든 연락처 개체를 검색한 다음 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동합니다.
  
### <a name="migrate-common-area-phones"></a>공통 영역 전화 마이그레이션

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 비즈니스용 Skype 서버 셸을 열 수 있습니다.
    
2. 명령줄에 다음을 입력합니다.
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. 모든 연락처 개체가 비즈니스용 Skype 서버 2019 풀로 이동되어 있는지 확인하려면 비즈니스용 Skype 서버 관리 셸에서 다음을 입력합니다.
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    이제 모든 연락처 개체가 2019 풀과 비즈니스용 Skype 서버 있는지 확인해야 합니다.
    

