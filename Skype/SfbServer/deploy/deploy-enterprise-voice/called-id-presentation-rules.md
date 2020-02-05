---
title: 비즈니스용 Skype 서버에서 호출 된 ID 프레젠테이션에 대 한 번역 규칙 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: '요약: 비즈니스용 Skype 서버에서 번역 규칙 작성 도구를 사용 하 여 번역 규칙을 정의 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 1a1f363ad157775395f77ef3e3c2915e9226bfd5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768201"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 호출 된 ID 프레젠테이션에 대 한 번역 규칙 만들기 또는 수정

**요약:** 비즈니스용 Skype 서버에서 번역 규칙 작성 도구를 사용 하 여 번역 규칙을 정의 하는 방법에 대해 알아봅니다.

**번역 규칙 작성** 도구에 값 집합을 입력 하 고 비즈니스용 Skype 서버 제어판에서 해당 하는 일치 패턴 및 번역 규칙을 생성할 수 있도록 하려면 다음 단계를 따르세요. 또는 정규식을 수동으로 작성 하 여 일치 패턴 및 번역 규칙을 정의할 수 있습니다. 자세한 내용은 [수동으로 번역 규칙 만들기 또는 수정을](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)참조 하세요.

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>번역 규칙 작성 도구를 사용 하 여 규칙을 정의 하려면

1. 비즈니스용 Skype Server 제어판을 엽니다.

2. 번역 규칙 정의를 시작 하려면 비즈니스용 [Skype server에서 미디어 바이패스를 사용 하 여 트렁크 구성](configure-trunk-with-media-bypass.md) 의 단계를 따르세요. 10 단계에서 비즈니스용 [skype 서버에서 미디어 바이패스 없이 트렁크를 구성](configure-trunk-without-media-bypass.md) 하려면 9 단계를 통과 합니다.

3. **새 번역 규칙** 또는 **번역 규칙 편집** 페이지의 **이름** 아래에서 번역할 번호 패턴을 설명 하는 이름을 입력 합니다.

4. ) **설명**아래에 번역 규칙에 대 한 설명 (예: US 국제 장거리 전화 걸기)을 입력 합니다.

5. 대화 상자의 **번역 규칙 작성** 섹션에서 다음 필드에 값을 입력 합니다.

   - **시작 번호**: (선택 사항) 패턴을 일치 시킬 숫자의 선행 자릿수를 지정 합니다. 예를 들어이 필드에 +를 입력 하 여 전자 164 형식의 숫자와 일치 시킵니다 (+로 시작).

   - **길이**: 일치 하는 패턴의 자릿수를 지정 하 고 해당 패턴이이 길이의 정확한 숫자, 최소 길이 또는 길이 중 어느 것을 일치 시킬 것인지 선택 합니다. 예를 들어 11 자리 이상 길이의 숫자와 일치 시키려면 11을 입력 하 고 드롭다운 목록에서 최소한을 표시 합니다.

   - **제거할 자릿수**: (선택 사항) 제거할 시작 숫자의 수를 지정 합니다. 예를 들어 숫자의 시작 부분에서 +를 제거 하려면 1을 입력 합니다.

   - **더할 자릿수**: (선택 사항) 번역 된 숫자 앞에 추가할 숫자를 지정 합니다. 예를 들어 규칙을 적용할 때 이진수를 번역 된 번호로 앞에 표시 하려면 011을 입력 합니다.

     이러한 필드에 입력 하는 값은 일치 및 **번역 규칙** 필드에 따라 **패턴** 에 반영 됩니다. 예를 들어 앞의 예제 값을 지정 하는 경우 **일치 하는 패턴** 필드의 결과 정규식은 다음과 같습니다.

     ^\+(\d{9}\d +) $

     **번역 규칙** 필드는 번역 된 숫자의 형식에 대 한 패턴을 지정 합니다. 이 패턴은 두 부분으로 구성 됩니다.

   - 일치 하는 패턴의 자릿수를 나타내는 값 (예: $1)

   - ) **추가할 숫자** 필드에 입력 하 여 앞에 입력할 수 있는 값

     앞의 예제 값을 사용 하 여 **번역 규칙** 필드에 011 $1이 표시 됩니다.

     이 번역 규칙이 적용 되 면 + 441235551010이 011441235551010.

6. **확인** 을 클릭 하 여 번역 규칙을 저장 합니다.

7. **확인** 을 클릭 하 여 트렁크 구성을 저장 합니다.

8. **트렁크 구성** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.

   > [!NOTE]
   > 번역 규칙을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.

### <a name="to-define-a-translation-rule-manually"></a>수동으로 번역 규칙 정의

1. 비즈니스용 Skype Server 제어판 열기

2. 번역 규칙 정의를 시작 하려면 비즈니스용 [Skype server에서 미디어 바이패스를 사용 하 여 트렁크 구성](configure-trunk-with-media-bypass.md) 의 단계를 따르세요. 10 단계에서 비즈니스용 [skype 서버에서 미디어 바이패스 없이 트렁크를 구성](configure-trunk-without-media-bypass.md) 하려면 9 단계를 통과 합니다.

3. **새 번역 규칙** 또는 **번역 규칙 편집** 페이지의 **이름** 필드에 번역할 번호 패턴을 설명 하는 이름을 입력 합니다.

4. ) **설명**에 번역 규칙에 대 한 설명 (예: US 국제 장거리 전화 걸기)을 입력 합니다.

5. **번역 규칙 작성** 섹션의 아래쪽에서 **편집** 을 클릭 합니다.

6. **정규식 입력**에 다음을 입력 합니다.

   - **이 패턴과 일치**하는 경우 번역할 숫자와 일치 시키는 데 사용할 패턴을 지정 합니다.

   - **번역 규칙**에서 번역 된 숫자의 형식에 대 한 패턴을 지정 합니다.

     예를 들어 **번역 규칙**에서이\+패턴 And011{9}$1 **과 일치** 하는 ^ (\d \d +) $를 입력 하는 경우 규칙은 + 441235551010를 011441235551010로 변환 합니다.

7. **확인** 을 클릭 하 여 번역 규칙을 저장 합니다.

8. **확인** 을 클릭 하 여 트렁크 구성을 저장 합니다.

9. **트렁크 구성** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.

    > [!NOTE]
    > 번역 규칙을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 미디어 바이패스를 사용 하 여 트렁크 구성](configure-trunk-with-media-bypass.md)

[비즈니스용 Skype 서버에서 미디어 바이패스 없이 트렁크 구성](configure-trunk-without-media-bypass.md)

[비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md)

[비즈니스용 Skype 서버에서 미디어 바이패스 배포](deploy-media-bypass.md)

