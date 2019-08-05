---
title: 비즈니스용 Skype 서버에서 기존 PIN 정책 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: '요약: 비즈니스용 Skype 서버에서 기존 PIN 정책을 수정 합니다.'
ms.openlocfilehash: 9aecd7fc48ce2893e1d8e603f7cdc369cde11ec3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191571"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 기존 PIN 정책 수정
 
**요약:** 비즈니스용 Skype 서버에서 기존 PIN 정책을 수정 합니다.
  
**Pin (고정 정책** ) 탭을 사용 하 여 IP 전화와 함께 비즈니스용 Skype에 연결 하는 사용자에 게 pin (개인 식별 번호) 인증을 제공할 수 있습니다. PIN 인증을 사용 하려면 웹 서비스 설정에서 **Pin 인증 사용** 이 선택 되어 있는지 확인 합니다.
  
다음 단계에 따라 사용자 수준 또는 사이트 수준 PIN 정책을 수정 합니다. 
  
### <a name="to-modify-an-existing-pin-policy"></a>기존 PIN 정책 수정

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **고정 정책을**클릭 합니다.
    
4. **고정 정책** 페이지에서 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
5. **Pin 편집 정책**에서 **최소 pin 길이**에 허용 하려는 최소 pin 길이를 입력 하거나 선택 합니다. 기본 최소 길이는 다섯 자리입니다.
    
6. 사용자가 잠길 때까지 허용 되는 최대 로그온 시도 횟수를 지정할 수 있으려면 **최대 로그온 시도 수 지정** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 허용 되는 최대 시도 수는 PIN 길이에 따라 자동으로 결정 됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정 됩니다.
    
7. 최대 로그온 시도 **횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도**에서 허용 하려는 최대 로그온 시도 횟수를 입력 하거나 선택 합니다.
    
8. 핀이 만료 되 게 하려면 **PIN 만료 사용** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 Pin이 만료 되지 않습니다. 기본적으로 Pin은 만료 되지 않습니다.
    
9. **Pin 만료 사용** 확인란을 선택한 경우 **pin이 (일) 후에 만료**되는 경우 해당 pin이 만료 되는 일 수를 입력 하거나 선택 합니다.
    
10. **Pin 기록 개수**에 사용자가 PIN을 다시 사용할 수 있으려면 먼저 사용자가 만들어야 하는 pin의 수를 입력 합니다. 기본적으로 사용자는 Pin을 다시 사용할 수 있습니다.
    
11. 일련 번호와 반복 되는 숫자 집합 등의 일반 숫자 패턴을 허용 하려면 **일반 패턴 허용** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 복잡 한 자릿수의 숫자만 사용할 수 있습니다. 기본적으로 복잡 한 자릿수 패턴만 사용할 수 있습니다.
    
    > [!IMPORTANT]
    > 공통 패턴을 허용 하지 않는 것이 좋습니다. 
  
12. **커밋**을 클릭합니다.
    

