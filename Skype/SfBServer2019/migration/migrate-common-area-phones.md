---
title: 공통 지역 전화 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '일반적인 지역 전화는 가장 자주 공유 작업 영역 또는 일반 영역에 거주 하는 IP 전화기입니다 (예: 대기실, 주방 또는 공장 바닥). 일반적인 지역 전화는 비즈니스용 Skype for UC (통합 커뮤니케이션) 기능을 제공 하기 위해 컴퓨터에 연결 되어 있지 않아도 됩니다. 배포를 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 레거시 공통 영역 휴대폰과 연결 된 연락처 개체도 마이그레이션해야 합니다. 비즈니스용 Skype Server Management Shell을 사용 하 여 먼저 레거시 공통 영역 휴대폰과 연결 된 모든 contact 개체를 검색 한 다음 해당 개체를 비즈니스용 Skype Server 2019 풀로 이동 합니다.'
ms.openlocfilehash: f268c22f1d1132b3b5b8c1c1676e5b3a0182cf3f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991153"
---
# <a name="migrate-common-area-phones"></a>공통 지역 전화 마이그레이션

일반적인 지역 전화는 가장 자주 공유 작업 영역 또는 일반 영역에 거주 하는 IP 전화기입니다 (예: 대기실, 주방 또는 공장 바닥). 일반적인 지역 전화는 비즈니스용 Skype for UC (통합 커뮤니케이션) 기능을 제공 하기 위해 컴퓨터에 연결 되어 있지 않아도 됩니다. 배포를 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 레거시 공통 영역 휴대폰과 연결 된 연락처 개체도 마이그레이션해야 합니다. 비즈니스용 Skype Server Management Shell을 사용 하 여 먼저 레거시 공통 영역 휴대폰과 연결 된 모든 contact 개체를 검색 한 다음 해당 개체를 비즈니스용 Skype Server 2019 풀로 이동 합니다.
  
### <a name="migrate-common-area-phones"></a>공통 지역 전화 마이그레이션

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
2. 명령줄에서 다음을 입력 합니다.
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Skype for Business 서버 관리 셸에서 모든 연락처 개체가 비즈니스용 Skype Server 2019 풀로 이동 되었는지 확인 하려면 다음을 입력 합니다.
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    모든 연락처 개체가 비즈니스용 Skype 서버 2019 풀에 연결 되어 있는지 확인 합니다.
    

