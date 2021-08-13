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
description: 비즈니스용 Skype 서버 단순 URL을 지원할 수 있습니다.
ms.openlocfilehash: c3d78387ae0bcf16204e2fcaa4ff7db3549334fe814a014a88c80e8ab6658d5b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324727"
---
# <a name="change-simple-urls-after-migration"></a>마이그레이션 후 단순 URL 변경

비즈니스용 Skype 서버 3개의 단순 URL을 지원할 수 있습니다.
  
- **모임** 은 사이트 또는 조직의 모든 전화 회의에 대한 기준 URL로 사용됩니다. 모임 단순 URL을 사용하면 모임에 참가할 링크를 쉽게 이해하고 전달하고 배포할 수 있습니다. 
    
- **전화 접속을** 사용하면 전화 접속 회의 웹 설정 액세스할 수 있습니다. 전화 접속 단순 URL은 모임에 전화 접속하려는 사용자가 필요한 전화 번호 및 PIN 정보에 액세스할 수 있도록 모든 모임 초대에 포함됩니다. 
    
- **관리자는** 관리 제어판에 비즈니스용 Skype 서버 수 있습니다. 관리 단순 URL은 조직의 내부 URL입니다. 
    
마이그레이션 후 비즈니스용 Skype 서버 변경이 단순 URL에 대한 DNS 레코드 및 인증서에 미치는 영향을 알고 있어야 합니다. 레거시 비즈니스용 Skype 서버 계속 토폴로지에서 사용 중이면 단순 URL을 변경할 필요는 없습니다. 마이그레이션 비즈니스용 Skype 서버 토폴로지에서 제거된 경우 단순 URL DNS 레코드를 업데이트하여 해당 풀 중 하나를 비즈니스용 Skype 서버 합니다. 그러나 단순 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 Enable-CsComputer를 실행하여 변경 내용을 등록해야 합니다.

## <a name="to-update-the-meet-simple-url"></a>Meet 단순 URL을 업데이트합니다.

1. 토폴로지 작성기에서 맨 위에 있는 노드인 비즈니스용 Skype 서버 마우스 오른쪽 **단추로 클릭한** 다음 속성 **편집을 클릭합니다.**
    
2. 왼쪽 **창에서** 단순 URL을 선택하고 모임 URL 아래에 **있는** 모임 URL을 선택한 다음 **URL 편집을 클릭합니다.**
    
3. URL을 원하는 값으로 업데이트하고 **확인** 을 클릭하여 편집한 URL을 저장합니다. 
    
## <a name="to-update-the-admin-simple-url"></a>관리 단순 URL을 업데이트하려면

1. 토폴로지 작성기에서 맨 위에 있는 노드인 비즈니스용 Skype 서버 마우스 오른쪽 **단추로 클릭한** 다음 속성 **편집을 클릭합니다.**
    
2. 왼쪽 창에서 단순 **URL을** 선택하고 관리 액세스 **URL** 상자 아래에 관리 제어판에 대한 관리 액세스에 비즈니스용 Skype 서버 입력한 다음 확인을 **클릭합니다.**
    
   > [!TIP]
   > 관리 URL에는 최대한 간단한 URL을 사용하는 것이 좋습니다. 가장 간단한 옵션은 https://admin <em>\<domain\></em> 입니다. 
  
## <a name="see-also"></a>참고 항목

[서버의 단순 URL에 대한 DNS 비즈니스용 Skype 서버](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
