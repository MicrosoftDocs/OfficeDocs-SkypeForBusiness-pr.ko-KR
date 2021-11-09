---
title: 2013에서 변환 규칙 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 비즈니스용 Skype 서버 Enterprise Voice 번호에 따라 E.164 형식으로 정규화된 통화를 라우팅할 수 있습니다. 즉, RNL(역방향 번호 검색)을 수행하기 위해 전화를 거는 모든 문자열을 해당 SIP URI로 변환할 수 있도록 E.164 형식으로 정규화해야 합니다. 비즈니스용 Skype 서버 ID 및 발신자 ID 프레젠테이션을 조작하는 기능을 제공합니다.
ms.openlocfilehash: f7919707e6999c39dfc9a13b7d6b735a31f5e6a9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836300"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>2013에서 변환 규칙 비즈니스용 Skype 서버

비즈니스용 Skype 서버 Enterprise Voice 번호에 따라 E.164 형식으로 정규화된 통화를 라우팅할 수 있습니다. 즉, RNL(역방향 번호 검색)을 수행하기 위해 전화를 거는 모든 문자열을 해당 SIP URI로 변환할 수 있도록 E.164 형식으로 정규화해야 합니다. 비즈니스용 Skype 서버 ID 및 발신자 ID 프레젠테이션을 조작하는 기능을 제공합니다.

비즈니스용 Skype 서버 호출된 사용자 전화 번호(즉, 전화 번호)를 E.164 형식에서 트렁크 피어(즉, 연결된 게이트웨이, PBX(Private Branch Exchange) 또는 SIP 트렁크)에 필요한 로컬 전화 걸기 형식으로 변환할 수 있습니다. 이렇게하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 변환 규칙을 하나 이상 정의해야 합니다.

## <a name="caller-id-presentation"></a>발신자 ID 프레젠테이션

비즈니스용 Skype 서버 E.164 형식에서 발신자 전화 번호(발신자 전화 번호)를 트렁크 피어에 필요한 로컬 전화 걸기 형식으로 변환하는 옵션도 제공합니다. 예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.

**제어판을 사용하여 발신자 비즈니스용 Skype 서버 구성**

1. RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다. 자세한 내용은 [Delegate setup permissions을 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)
2. 브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 Skype 도구 설치 [및 열기 를 참조합니다.](../../management-tools/install-and-open-administrative-tools.md)
3. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭한 다음 **트렁크 구성** 을 클릭합니다.
4. 트렁크 구성 페이지에서 기존 트렁크(예: 전역 트렁크)를 두 번 클릭하여 트렁크 구성 편집 대화 **상자를** 표시합니다. 
5. 발신자 ID 프레젠테이션을 구성하는 경우:
    - Enterprise Voice 배포에서 사용 가능한 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택하려면 **선택** 을 클릭합니다. 호출 **번호 변환 규칙에서** 트렁크와 연결하려는 규칙을 클릭한 다음 확인 을 **클릭합니다.**
    - 새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기** 를 클릭합니다. 
    - 트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.
    - 새 규칙을 정의하기 위한 시작점으로 사용할 기존 변환 규칙을 복사하려면 규칙 이름을 클릭하고 **복사를** 클릭한 다음 붙여넣기 **를 클릭합니다.**
    - 트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거** 를 클릭합니다.

> [!Warning] 
> 연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오. 

## <a name="called-id-presentation"></a>호출된 ID 프레젠테이션

> [!Important]
> 트렁크 피어에서 변환 규칙을 구성하는 *대신*, 하나 이상의 변환 규칙을 Enterprise Voice 트렁크 구성에 연결하는 기능을 사용할 수 있습니다. 트렁크 피어에 대한 변환 규칙을 구성한 경우 변환 규칙을 Enterprise Voice 트렁크 구성과 연결하지 마십시오. 두 규칙이 충돌할 수 있기 때문입니다. 

다음 방법 중 하나를 사용하여 변환 규칙을 만들거나 수정할 수 있습니다.

- [변환](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) 규칙 작성 도구를 사용하여 시작 자릿수, 길이, 제거할 자릿수 및 추가할 자릿수 값을 지정한 다음 비즈니스용 Skype 서버 제어판에서 해당 일치 패턴 및 변환 규칙을 생성할 수 있습니다.
- [정규식을 수동으로](#create-or-modify-a-translation-rule-manually) 작성하여 일치 패턴 및 변환 규칙을 정의합니다.

> [!Note]
> 정규식을 작성하는 방법에 대한 자세한 내용은 [정규식 .NET Framework 참조하세요.](/dotnet/standard/base-types/regular-expressions) 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>변환 규칙 작성 도구를 사용하여 변환 규칙 만들기 또는 수정

변환 규칙 작성 도구에 값 집합을 입력하고 비즈니스용 Skype 서버 제어판에서 해당 일치 패턴 및 변환 규칙을 생성하도록 설정하여 변환 규칙을 정의하려면 다음 단계를 수행합니다. 

**변환 규칙 작성 도구를 사용하여 규칙을 정의하려면**

1. RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다. 자세한 내용은 [Delegate setup permissions을 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)
2. 브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 Skype 도구 설치 [및 열기 를 참조합니다.](../../management-tools/install-and-open-administrative-tools.md)
3. 변환 규칙 정의를 시작하고 10단계를 통해 미디어 우회를 통해 트렁크 구성 또는 9단계까지 미디어 우회 없이 트렁크 구성의 단계를 따릅니다. [](GET LINK AFTER MIGRATION) [](GET LINK AFTER MIGRATION)
4. **새 변환 규칙** 또는 **변환 규칙 편집** 페이지의 **이름** 아래에서 변환 대상 숫자 패턴을 설명하는 이름을 입력합니다.
5. (선택 사항) 설명 **아래에서** 변환 규칙에 대한 설명을 입력합니다(예: 미국 국제 장거리 전화 **걸기).**
6. 대화 상자의 **변환 규칙 작성** 섹션에 있는 다음 필드에 값을 입력합니다.
    - **시작 숫자**: (선택 사항) 패턴을 일치시킬 선행 자릿수를 지정합니다. 예를 들어 이 필드에 +를 입력하면 +로 시작하는 E.164 형식의 번호가 일치됩니다.
    - **길이**: 일치하는 패턴의 자릿수를 지정하고 패턴을 이 길이와 정확히 일치하는 번호와 일치시킬지 또는 이 길이 이상인 번호와 일치시킬지 또는 길이에 상관없이 일치시킬지 여부를 선택합니다 예를 들어 **11** 을 입력하고 드롭다운 목록에서 **최소** 를 선택하면 길이가 11자리 이상인 번호와 일치하게 됩니다.
    - **제거할 숫자**: (선택 사항) 제거할 시작 자릿수를 지정합니다. 예를 들어 **1** 을 입력하면 번호 앞부분에서 +가 제거됩니다.
    - **추가할 숫자**: (선택 사항) 변환된 번호의 앞에 추가할 자릿수를 지정합니다. 예를 들어 **011** 을 입력하면 규칙이 적용될 때 변환된 번호 앞에 011이 추가됩니다.
    
    이러한 필드에 입력하는 값은 일치할 **패턴** 및 변환 규칙 **필드에** 반영됩니다. 예를 들어 앞의 예제 값을 지정하는 경우 Pattern **to matc** h 필드의 결과 정규식은 다음과 같습니다.
    
    **^\+(\d {9} \d+)$** 

    **변환 규칙** 필드에서는 변환된 번호 형식에 대한 패턴이 지정됩니다. 이 패턴은 두 부분으로 되어 있습니다.
    - 일치하는 패턴의 자릿수를 나타내는 값(예: **$1**)
    - (선택 사항) **추가할 숫자** 필드에 입력하여 번호 앞에 추가할 수 있는 값

    위의 예 값을 사용하면 **변환 규칙** 필드에 **011$1** 이 나타납니다.
    
    이 변환 규칙이 적용되면 +441235551010이 011441235551010이 됩니다.
7. **확인** 을 클릭하여 변환 규칙을 저장합니다.
8. **확인** 을 클릭하여 트렁크 구성을 저장합니다.
9. **트렁크 구성** n 페이지에서 커밋을 **클릭한** 다음 모두 **커밋을 클릭합니다.** 

> [!Note]
> 변환 규칙을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 음성 라우팅 [구성에 보류 중인 변경 내용 게시를 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration) 

### <a name="create-or-modify-a-translation-rule-manually"></a>수동으로 변환 규칙 만들기 또는 수정

일치하는 패턴 및 변환 규칙에 대한 정규식을 작성하여 변환 규칙을 정의하려면 다음 단계를 따르십시오. 

**변환 규칙을 수동으로 정의하려면**

1. RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다. 자세한 내용은 [Delegate setup permissions을 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)
2. 브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 Skype 도구 설치 [및 열기 를 참조합니다.](../../management-tools/install-and-open-administrative-tools.md)
3. 변환 규칙 정의를 시작하고 10단계를 통해 미디어 우회를 통해 트렁크 구성 또는 9단계까지 미디어 우회 없이 트렁크 구성의 단계를 따릅니다. [](GET LINK AFTER MIGRATION) [](GET LINK AFTER MIGRATION)
4. **새 변환 규칙** 또는 **변환 규칙 편집** 페이지의 **이름** 필드에 변환 대상 숫자 패턴을 설명하는 이름을 입력합니다.
5. (선택 사항) **설명에** 변환 규칙에 대한 설명을 입력합니다. 예를 들어 미국 국제 장거리 전화 **걸기입니다.**
6. **변환 규칙 작성** 섹션 아래쪽의 **편집** 을 클릭합니다.
7. 정규식 입력에 **다음을 입력합니다.**
    - **다음 패턴과 일치시킴** 에 변환할 숫자와 일치시키는 데 사용할 패턴을 지정합니다.
    - **변환 규칙** 에 변환된 숫자 형식의 패턴을 지정합니다.

    예를 들어 이 패턴 일치에 **^ \+ (\d {9} \d+)$를** 입력하고 **변환** 규칙에 **011$1을** 입력하면 규칙은 +441235551010 변환하여 011441235551010. 
8. **확인** 을 클릭하여 변환 규칙을 저장합니다.
9. **확인** 을 클릭하여 트렁크 구성을 저장합니다.
10. **트렁크 구성** 페이지에서 **커밋** 을 클릭하고 **모두 커밋** 을 클릭합니다. 

> [!Note] 
> 변환 규칙을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 음성 라우팅 [구성에 보류 중인 변경 내용 게시를 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration)