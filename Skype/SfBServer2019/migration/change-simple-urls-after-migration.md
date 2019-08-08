---
title: 마이그레이션 후 간단한 Url 변경
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype 서버는 간단한 Url을 지원 합니다.
ms.openlocfilehash: 806003a2639d3861c066248657521ceb58a4e986
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239705"
---
# <a name="change-simple-urls-after-migration"></a>마이그레이션 후 간단한 Url 변경

비즈니스용 Skype 서버는 다음과 같은 세 가지 간단한 Url을 지원 합니다.
  
- **회의** 는 사이트 또는 조직의 모든 컨퍼런스에 대 한 기본 URL로 사용 됩니다. 모임에 참여 하는 간단한 URL을 사용 하 여 모임을 연결 하는 링크는 이해 하기 쉬우며, 의사 소통 및 배포 하기가 쉽습니다. 
    
- **전화 접속-** 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다. 모임에 전화를 걸려면 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 전화 접속 간단한 URL이 모든 모임 초대에 포함 되어 있습니다. 
    
- **관리자** 는 비즈니스용 Skype Server 제어판에 빠르게 액세스할 수 있습니다. 관리 단순 URL은 조직 내부입니다. 
    
비즈니스용 Skype 서버를 마이그레이션한 후에는 변경 내용이 간단한 Url에 대 한 DNS 레코드 및 인증서에 어떤 영향을 미치는지 알아야 합니다. 레거시 비즈니스용 Skype Server Director가 토폴로지에서 사용 중인 경우에는 간단한 Url을 변경할 필요가 없습니다. 마이그레이션 후에 비즈니스용 Skype 서버 디렉터가 토폴로지에서 제거 되는 경우 간단한 URL DNS 레코드를 비즈니스용 Skype 서버 풀 중 하나를 가리키도록 업데이트 해야 합니다. 그러나 간단한 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서-CsComputer를 실행 하 여 변경 내용을 등록 해야 합니다.

## <a name="to-update-the-meet-simple-url"></a>기본 모임 URL을 업데이트 하려면

1. 토폴로지 작성기에서 상위 노드 **비즈니스용 Skype 서버**를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.
    
2. 왼쪽 창에서 **간단한 url** 을 선택 하 고 모임 url 아래에 있는 url을 선택한 다음 **url 편집**을 클릭 합니다 **.**
    
3. URL을 원하는 값으로 업데이트 한 다음 **확인** 을 클릭 하 여 편집한 url을 저장 합니다. 
    
## <a name="to-update-the-admin-simple-url"></a>관리 간단한 URL을 업데이트 하려면

1. 토폴로지 작성기에서 상위 노드 **비즈니스용 Skype 서버**를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.
    
2. 왼쪽 창에서 **간단한 url** 을 선택 하 고 **관리 액세스 URL** 상자 아래에 있는 비즈니스용 Skype Server 제어판의 관리 액세스에 사용할 간단한 url을 입력 한 다음 **확인**을 클릭 합니다.
    
   > [!TIP]
   > 관리 URL에 가장 간단한 URL을 사용 하는 것이 좋습니다. 가장 간단한 방법은 https://admin입니다. <em> \<도메인\></em>. 
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버의 간단한 Url에 대 한 DNS 요구 사항](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
