---
title: 신뢰할 수 있는 응용 프로그램 서버 구성
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
description: 혼합 환경에서 신뢰할 수 있는 새 응용 프로그램 서버를 만드는 경우 다음 홉 풀을 비즈니스용 Skype 서버 2019 풀로 설정 해야 합니다. 혼합 환경에서는 레거시 풀과 비즈니스용 Skype 서버 2019 풀이 모두 드롭다운 목록에 표시 됩니다. 레거시 풀을 선택 하는 것은 지원 되지 않습니다.
ms.openlocfilehash: a853065c8888ce9e160b34d182ec8bde6f4569f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813776"
---
# <a name="configure-trusted-application-servers"></a>신뢰할 수 있는 응용 프로그램 서버 구성

혼합 환경에서 신뢰할 수 있는 새 응용 프로그램 서버를 만드는 경우 다음 홉 풀을 비즈니스용 Skype 서버 2019 풀로 설정 해야 합니다. 혼합 환경에서는 드롭다운 목록에 레거시 풀과 비즈니스용 Skype 서버 2019 풀이 모두 표시 됩니다. 레거시 풀을 선택 하는 것은 지원 되지 않습니다.
  
> [!IMPORTANT]
> 신뢰할 수 있는 응용 프로그램 서버를 마이그레이션하는 경우에는 사용 중인 버전 MA도 업데이트 해야 합니다. 비즈니스용 Skype 서버 2019에 대해 신뢰할 수 있는 새 응용 프로그램 풀을 만드는 경우 비즈니스용 Skype Server 2019에 포함 된 버전 또는 최신 버전으로 업데이트 해야 합니다. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>신뢰할 수 있는 응용 프로그램 서버를 만들 때 다음 홉으로 비즈니스용 Skype 서버 2019을 선택 합니다.

1. 토폴로지 작성기를 엽니다.
    
2. 왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버** 를 마우스 오른쪽 단추로 클릭 하 고 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭 합니다.
    
3. 신뢰할 수 있는 응용 프로그램 풀의 **풀 FQDN** 을 입력 하 고이를 단일 서버 또는 다중 서버 중에서 선택 합니다. 
    
4. **다음**을 클릭 합니다.
    
5. **다음 홉 선택** 페이지의 목록에서 비즈니스용 Skype 서버 2019 프런트 엔드 풀을 선택 합니다. 
    
6. **마침**을 클릭합니다.
    
7. 최상위 노드 **비즈니스용 Skype 서버**를 선택 하 고 **동작** 메뉴에서 **게시**를 선택 합니다.
    
    **신뢰할 수 있는 응용 프로그램 풀이** 성공적으로 만들어지고 올바른 프런트 엔드 풀에 연결 되어 있는지 확인 합니다. 
    

