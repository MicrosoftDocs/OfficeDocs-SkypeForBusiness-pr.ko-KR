---
title: 마이그레이션 후 단순 URL 변경
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
description: 비즈니스용 Skype 서버는 단순 Url을 지원 합니다.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753908"
---
# <a name="change-simple-urls-after-migration"></a>마이그레이션 후 단순 URL 변경

비즈니스용 Skype 서버에서는 다음과 같은 세 가지 단순 Url을 지원 합니다.
  
- **모임**은 사이트 또는 조직의 모든 전화 회의에 대한 기준 URL로 사용됩니다. 모임 단순 URL을 사용하면 모임에 참가할 링크를 쉽게 이해하고 전달하고 배포할 수 있습니다. 
    
- **전화 접속** 을 사용 하면 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다. 전화 접속 단순 URL은 모임에 전화를 거는 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 모든 모임 초대에 포함 됩니다. 
    
- **관리자** 는 비즈니스용 Skype 서버 제어판에 빠르게 액세스할 수 있도록 합니다. 관리 단순 URL은 조직의 내부 URL입니다. 
    
비즈니스용 Skype 서버로 마이그레이션한 후에는 변경 내용이 단순 Url에 대 한 DNS 레코드 및 인증서에 미치는 영향을 알고 있어야 합니다. 레거시 비즈니스용 Skype 서버 디렉터를 토폴로지에서 계속 사용 중인 경우에는 단순 Url을 변경할 필요가 없습니다. 마이그레이션 후 비즈니스용 Skype 서버 디렉터를 토폴로지에서 제거한 경우에는 비즈니스용 Skype 서버 풀 중 하나를 가리키도록 단순 URL DNS 레코드를 업데이트 해야 합니다. 그러나 단순 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 Enable-CsComputer를 실행하여 변경 내용을 등록해야 합니다.

## <a name="to-update-the-meet-simple-url"></a>모임 단순 URL을 업데이트 하려면

1. 토폴로지 작성기에서 최상위 노드 **비즈니스용 Skype 서버**를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.
    
2. 왼쪽 창에서 **단순 url** 을 선택한 다음 **모임 Url** 아래에서 회의 url을 선택 하 고 **url 편집**을 클릭 합니다.
    
3. URL을 원하는 값으로 업데이트하고 **확인**을 클릭하여 편집한 URL을 저장합니다. 
    
## <a name="to-update-the-admin-simple-url"></a>관리 단순 URL을 업데이트 하려면

1. 토폴로지 작성기에서 최상위 노드 **비즈니스용 Skype 서버**를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.
    
2. 왼쪽 창에서 **단순 url** 을 선택한 다음 **관리 액세스 URL** 상자 아래에 있는 비즈니스용 Skype 서버 제어판에 대 한 관리 액세스용으로 사용할 단순 url을 입력 하 고 **확인**을 클릭 합니다.
    
   > [!TIP]
   > 관리 URL에는 최대한 간단한 URL을 사용하는 것이 좋습니다. 가장 간단한 방법은 https://admin 입니다. <em>\<domain\></em> 
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버의 단순 Url에 대 한 DNS 요구 사항](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
