---
title: 비즈니스용 Skype 서버에서 발신자 ID 프레젠테이션의 번역 규칙 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: '요약: 비즈니스용 Skype 서버 제어판을 사용 하 여 발신자 ID를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: a305d420171fa10253f387e1fcbcfa2a50d72753
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190092"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 발신자 ID 프레젠테이션의 번역 규칙 만들기 또는 수정

**요약:** 비즈니스용 Skype 서버 제어판을 사용 하 여 발신자 ID를 구성 하는 방법에 대해 알아봅니다.

비즈니스용 Skype 서버를 사용 하는 경우, 호출 된 상대방의 전화 번호 (전화 번호)를 _트렁크 피어_ 에 필요한 로컬 전화 걸기 형식으로 변환할 수 있습니다 (즉, 연결 된 게이트웨이, 사설 분기 교환 ( PBX) 또는 SIP 트렁크). 이렇게 하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 변환 하는 하나 이상의 번역 규칙을 정의 해야 합니다.

비즈니스용 Skype 서버는 또한 전화 상대의 전화 번호 (즉, 발신자가 통화 하는 전화 번호)를 트렁크 피어에 필요한 지역 전화 걸기 형식으로 변환 하는 옵션도 제공 합니다. 예를 들어 다이얼 문자열의 시작 부분에서 + 44을 제거 하 고 0144으로 바꾸는 번역 규칙을 작성할 수 있습니다.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 발신자 ID를 구성 하려면

1. 비즈니스용 Skype Server 제어판을 엽니다.

2. 왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.

3. **트렁크 구성** 페이지에서 기존 트렁크 (예: **전역** 트렁크)를 두 번 클릭 하 여 **트렁크 구성 편집** 대화 상자를 표시 합니다.

4. 발신자 ID 프레젠테이션을 구성 하려면 다음을 수행 합니다.

   - 엔터프라이즈 음성 배포에서 사용할 수 있는 모든 번역 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다. **전화 번호 번역 규칙**에서 트렁크와 연결할 규칙을 클릭 한 다음 **확인**을 클릭 합니다.

   - 새 번역 규칙을 정의 하 고 트렁크에 연결 하려면 **새로 만들기**를 클릭 합니다. 새 규칙을 정의 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [번역 규칙 정의](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 를 참조 하세요.

   - 트렁크에 이미 연결 된 번역 규칙을 편집 하려면 규칙 이름을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다. 자세한 내용은 배포 설명서에서 [번역 규칙 정의](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 를 참조 하세요.

   - 기존 번역 규칙을 복사 하 여 새 규칙을 정의 하는 출발점으로 사용 하려면 규칙 이름을 클릭 하 고 **복사**를 클릭 한 다음 **붙여넣기**를 클릭 합니다. 자세한 내용은 [번역 규칙 정의](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)를 참조 하세요.

   - 트렁크에서 번역 규칙을 제거 하려면 규칙 이름을 강조 표시 하 고 **제거**를 클릭 합니다.

     > [!CAUTION]
     > 두 규칙이 충돌할 수 있으므로 연결 된 트렁크 피어에서 번역 규칙을 구성한 경우에는 번역 규칙과 트렁크를 연결 하지 마세요.


