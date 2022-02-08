---
title: 2016년 8월에 기존 PIN 정책 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: '요약: 정책에서 기존 PIN 정책을 비즈니스용 Skype 서버.'
ms.openlocfilehash: b38ffa3f5ef8d858b93e6844a8aba46a92538b9d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384356"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a>2016년 8월에 기존 PIN 정책 비즈니스용 Skype 서버
 
**요약:** 정책에서 기존 PIN 정책을 비즈니스용 Skype 서버.
  
**PIN** 정책 탭을 사용하여 IP 전화를 사용하여 PIN에 연결하는 사용자에게 개인식별번호(PIN) 인증을 비즈니스용 Skype 수 있습니다. PIN 인증을 사용하려면 웹 서비스 설정에서 **PIN 인증 사용** 이 선택되어 있는지 확인합니다.
  
사용자 수준 또는 사이트 수준 PIN 정책을 수정하려면 다음 단계를 수행합니다. 
  
### <a name="to-modify-an-existing-pin-policy"></a>기존 PIN 정책을 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다. 
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭하고 **PIN 정책** 을 클릭합니다.
    
4. **PIN 정책** 페이지에서 정책을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.
    
5. **PIN 정책 편집** 의 **최소 PIN 길이** 에서 허용할 최소 PIN 길이를 입력하거나 선택합니다. 기본 최소 길이는 5자리입니다.
    
6. 사용자가 잠길 때까지의 최대 로그온 시도 횟수를 지정하려면 **최대 로그온 시도 횟수 지정** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN 길이에 따라 최대 로그온 시도 횟수가 자동으로 결정됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정됩니다.
    
7. **최대 로그온 시도 횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도 횟수** 에 허용할 최대 로그온 시도 횟수를 입력하거나 선택합니다.
    
8. PIN이 만료되도록 하려면 **PIN 만료 사용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN이 만료되지 않습니다. 기본적으로 PIN은 만료되지 않습니다.
    
9. **PIN 만료 사용** 확인란을 선택한 경우 **다음 이후 PIN 만료(일)** 에 PIN이 만료될 때까지의 기간(일)을 입력하거나 선택합니다.
    
10. **PIN 기록 카운트** 에 사용자가 PIN을 다시 사용할 수 있을 때까지 만들어야 하는 PIN의 개수를 입력합니다. 기본적으로 사용자는 PIN을 다시 사용할 수 있습니다.
    
11. PIN에서 연속하는 숫자, 반복되는 숫자 집합 등의 공통 숫자 패턴을 허용하려면 **공통 패턴 허용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 복잡한 숫자 패턴만 허용됩니다. 기본적으로는 복잡한 숫자 패턴만 허용됩니다.
    
    > [!IMPORTANT]
    > 공통 패턴은 허용하지 않는 것이 좋습니다. 
  
12. **커밋** 을 클릭합니다.
    

