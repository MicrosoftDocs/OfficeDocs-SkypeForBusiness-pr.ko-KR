---
title: 외부 사용자에 대한 페더레이션 및 원격 액세스 확인
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
description: 페더레이션 경로를 비즈니스용 Skype 서버 2019 Edge 서버로 전환 하 고 나면 일부 기능적 테스트를 수행 하 여 페더레이션이 예상 대로 수행 되는지 확인 해야 합니다. 외부 사용자 액세스에 대 한 테스트에는 조직에서 지 원하는 각 외부 사용자 유형 (다음의 일부 또는 모두 포함)이 포함 되어야 합니다.
ms.openlocfilehash: 7f27fa853c8af2ba5e97835ad1e0dd893c9128e0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812686"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>외부 사용자에 대한 페더레이션 및 원격 액세스 확인

페더레이션 경로를 비즈니스용 Skype 서버 2019 Edge 서버로 전환 하 고 나면 일부 기능적 테스트를 수행 하 여 페더레이션이 예상 대로 수행 되는지 확인 해야 합니다. 외부 사용자 액세스에 대 한 테스트에는 조직에서 지 원하는 각 외부 사용자 유형 (다음의 일부 또는 모두 포함)이 포함 되어야 합니다.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>외부 사용자 및 외부 액세스 연결 테스트

- 적어도 하나 이상의 페더레이션 도메인, 비즈니스용 Skype 서버 2019의 내부 사용자, 그리고 레거시 설치의 사용자입니다. 인스턴트 메시지 (IM), 현재 상태, 오디오/비디오 (A/V) 및 데스크톱 공유를 테스트 합니다.
    
- 조직에서 지 원하는 각 공용 IM 서비스 공급자의 사용자 (그리고 프로 비전이 완료 된 경우)는 비즈니스용 Skype 서버 2019와 레거시 설치 사용자에 대 한 사용자와 통신 합니다. 
    
- 익명 사용자가 회의에 참가할 수 있는지 확인 합니다.
    
- 비즈니스용 Skype Server 2019의 사용자와 레거시 설치의 사용자에 대 한 원격 사용자 액세스를 사용 하 여 레거시 설치에 호스팅되는 사용자 (VPN을 제외한 인트라넷 외부에서는 Lync Server/비즈니스용 Skype의 경우)를 기록 합니다. IM, 현재 상태, A/V, 데스크톱 공유를 테스트 합니다.
    
- 비즈니스용 skype server 2019에는 원격 사용자 액세스를 사용 하 여 (인트라넷 외부에서는 비즈니스용 Skype 서버에 로그인 하 고 VPN 제외), 레거시 설치에 대 2019 한 사용자를 포함 하 여 사용자를 2019 호스트 합니다. IM, 현재 상태, A/V, 데스크톱 공유를 테스트 합니다.
    

