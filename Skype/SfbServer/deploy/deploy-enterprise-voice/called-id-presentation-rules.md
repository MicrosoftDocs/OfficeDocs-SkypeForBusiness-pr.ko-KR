---
title: 비즈니스용 Skype 서버에서 호출된 ID 프레젠테이션에 대한 변환 규칙 만들기 또는 수정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '요약: 비즈니스용 Skype 서버에서 번역 규칙 작성 도구를 사용하여 변환 규칙을 정의하는 방법을 설명하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: b93d271abd0ade1b178e859f2a0599464a6759e5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804198"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 호출된 ID 프레젠테이션에 대한 변환 규칙 만들기 또는 수정

**요약:** 비즈니스용 Skype 서버에서 변환 규칙 작성 도구를 사용하여 변환 규칙을 정의하는 방법을 자세히 알아보습니다.

변환 규칙 작성 도구에 값 집합을 입력하고 비즈니스용  Skype 서버 제어판에서 해당 일치 패턴 및 변환 규칙을 생성하도록 설정하여 변환 규칙을 정의하려면 다음 단계를 수행합니다. 또는 정규 표현식을 수동으로 작성하여 일치 패턴과 변환 규칙을 정의할 수 있습니다. 자세한 내용은 [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)을 참조하십시오.

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>변환 규칙 작성 도구를 사용하여 규칙을 정의하려면

1. 비즈니스용 Skype 서버 제어판을 니다.

2. 변환 규칙 정의를 시작하고 10단계를 통해 비즈니스용 [Skype](configure-trunk-with-media-bypass.md) 서버에서 미디어 우회를 통해 트렁크를 구성하거나 9단계를 통해 비즈니스용 [Skype](configure-trunk-without-media-bypass.md) 서버에서 미디어 우회 없이 트렁크를 구성합니다.

3. **새 변환 규칙** 또는 **변환 규칙 편집** 페이지의 **이름** 아래에서 변환 대상 숫자 패턴을 설명하는 이름을 입력합니다.

4. (선택 사항) 설명 **아래에** 변환 규칙에 대한 설명을 입력합니다(예: 미국 국제 장거리 전화 걸기).

5. 대화 상자의 **변환 규칙 작성** 섹션에 있는 다음 필드에 값을 입력합니다.

   - **시작 숫자**: (선택 사항) 패턴을 일치시킬 선행 자릿수를 지정합니다. 예를 들어 이 필드에 +를 입력하면 +로 시작하는 E.164 형식의 번호가 일치됩니다.

   - **길이**: 일치 패턴의 자릿수와 해당 길이의 숫자를 일치할지, 적어도 이 길이인지 또는 길이와 일치할지 여부를 선택합니다. 예를 들어 11을 입력하고 드롭다운 목록에서 최소 11자리 길이의 숫자와 일치하게 선택합니다.

   - **제거할 숫자**: (선택 사항) 제거할 시작 자릿수를 지정합니다. 예를 들어 숫자의 시작점에서 +를 제거하기 위해 1을 입력합니다.

   - **추가할 숫자**: (선택 사항) 변환된 번호의 앞에 추가할 자릿수를 지정합니다. 예를 들어 011을 입력하면 규칙이 적용될 때 변환된 번호 앞에 011이 추가됩니다.

     이 필드에 입력한 값은 **일치시킬 패턴** 및 **변환 규칙** 필드에 적용됩니다. 예를 들어 위의 예 값을 지정한 경우 **일치시킬 패턴** 필드의 정규식 결과는 다음과 같습니다.

     ^\+(\d {9} \d+)$

     **변환 규칙** 필드에서는 변환된 번호 형식에 대한 패턴이 지정됩니다. 이 패턴은 두 부분으로 되어 있습니다.

   - 일치하는 패턴의 자릿수를 나타내는 값(예: $1)

   - (선택 사항) **추가할 숫자** 필드에 입력하여 번호 앞에 추가할 수 있는 값

     위의 예 값을 사용하면 변환 규칙 필드에 **011$1** 이 나타납니다.

     이 변환 규칙이 적용되면 +441235551010이 011441235551010이 됩니다.

6. **확인** 을 클릭하여 변환 규칙을 저장합니다.

7. **확인** 을 클릭하여 트렁크 구성을 저장합니다.

8. **트렁크 구성** 페이지에서 **커밋** 을 클릭하고 **모두 커밋** 을 클릭합니다.

   > [!NOTE]
   > 변환 규칙을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 작업 설명서에서 비즈니스용 [Skype의](voice-route-config-changes.md) 음성 라우팅 구성에 보류 중인 변경 내용 게시를 참조하십시오.

### <a name="to-define-a-translation-rule-manually"></a>변환 규칙을 수동으로 정의하려면

1. 비즈니스용 Skype 서버 제어판 열기

2. 변환 규칙 정의를 시작하고 10단계를 통해 비즈니스용 [Skype](configure-trunk-with-media-bypass.md) 서버에서 미디어 우회를 통해 트렁크를 구성하거나 9단계를 통해 비즈니스용 [Skype](configure-trunk-without-media-bypass.md) 서버에서 미디어 우회 없이 트렁크를 구성합니다.

3. **새 변환 규칙** 또는 **변환 규칙 편집** 페이지의 **이름** 필드에 변환 대상 숫자 패턴을 설명하는 이름을 입력합니다.

4. (선택 사항) **설명에서** 변환 규칙에 대한 설명을 입력합니다(예: 미국 국제 장거리 전화 걸기).

5. **변환 규칙 작성** 섹션 아래쪽의 **편집** 을 클릭합니다.

6. **정규식 입력** 에 다음을 입력합니다.

   - **다음 패턴과 일치시킴** 에 변환할 숫자와 일치시키는 데 사용할 패턴을 지정합니다.

   - **변환 규칙** 에 변환된 숫자 형식의 패턴을 지정합니다.

     예를 들어 이 패턴 일치에 ^ \+ (\d \d+)$을 입력하고 변환 규칙에서 {9} 1011$1을 입력하면 규칙은 +441235551010을  011441235551010으로 변환합니다. 

7. **확인** 을 클릭하여 변환 규칙을 저장합니다.

8. **확인** 을 클릭하여 트렁크 구성을 저장합니다.

9. **트렁크 구성** 페이지에서 **커밋** 을 클릭하고 **모두 커밋** 을 클릭합니다.

    > [!NOTE]
    > 변환 규칙을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 작업 설명서에서 비즈니스용 [Skype의](voice-route-config-changes.md) 음성 라우팅 구성에 보류 중인 변경 내용 게시를 참조하십시오.

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 미디어 우회를 통해 트렁크 구성](configure-trunk-with-media-bypass.md)

[비즈니스용 Skype 서버에서 미디어 우회 없이 트렁크 구성](configure-trunk-without-media-bypass.md)

[비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md)

[비즈니스용 Skype 서버에서 미디어 우회 배포](deploy-media-bypass.md)

