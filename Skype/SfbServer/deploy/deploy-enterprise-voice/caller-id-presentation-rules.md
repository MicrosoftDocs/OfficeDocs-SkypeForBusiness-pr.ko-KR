---
title: 발신자 ID 프레젠테이션에 대한 변환 규칙을 만들거나 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: '요약: 비즈니스용 Skype 서버 제어판을 사용하여 발신자 비즈니스용 SKYPE 서버 방법을 학습합니다.'
ms.openlocfilehash: 7accfe11c22a8b453ac767c80a0c9269fe638c45
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605597"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>발신자 ID 프레젠테이션에 대한 변환 규칙을 만들거나 비즈니스용 Skype 서버

**요약:** 제어판을 사용하여 발신자 비즈니스용 SKYPE 서버 방법을 학습합니다.

비즈니스용 Skype 서버 호출된 사용자 전화 번호(즉, 전화 _번호)를_ E.164 형식에서 트렁크 피어(즉, 연결된 게이트웨이, PBX(Private Branch Exchange) 또는 SIP 트렁크)에 필요한 로컬 전화 걸기 형식으로 변환할 수 있습니다. 이렇게하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 변환 규칙을 하나 이상 정의해야 합니다.

비즈니스용 Skype 서버 또한 발신자 전화 번호(즉, 발신자에서 전화를 걸고 있는 전화 번호)를 E.164 형식에서 트렁크 피어에 필요한 로컬 전화 걸기 형식으로 변환하는 옵션도 제공합니다. 예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 발신자 비즈니스용 Skype 서버 구성

1. 제어판을 비즈니스용 Skype 서버 를 니다.

2. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭한 다음 **트렁크 구성** 을 클릭합니다.

3. **트렁크** 구성 페이지에서 기존 트렁크(예: 전역 트렁크)를 두 번 클릭하여 트렁크 구성 편집 대화 **상자를** 표시합니다. 

4. 발신자 ID 프레젠테이션을 구성하는 경우:

   - Enterprise Voice 배포에서 사용 가능한 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택하려면 **선택** 을 클릭합니다. 호출 **번호 변환 규칙에서** 트렁크와 연결하려는 규칙을 클릭한 다음 확인 을 **클릭합니다.**

   - 새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기** 를 클릭합니다. 새 규칙을 정의하는 데 대한 자세한 내용은 배포 설명서에서  [Defining Translation Rules를](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) 참조하십시오.

   - 트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다. 자세한 내용은 배포 설명서에서 [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)를 참조하십시오.

   - 기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사** 를 클릭한 다음 **붙여넣기** 를 클릭합니다. 자세한 내용은 [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)를 참조하십시오.

   - 트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거** 를 클릭합니다.

     > [!CAUTION]
     > 연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.