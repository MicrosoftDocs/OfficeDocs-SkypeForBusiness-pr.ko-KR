---
title: 비즈니스용 Skype 서버에서 변환 규칙 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버 Enterprise Voice는 전자 164 형식으로 정규화 된 전화 번호를 기반으로 통화를 라우팅합니다. 즉, RNL (역방향 번호 조회)를 수행 하 여 일치 하는 SIP URI로 변환할 수 있도록 모든 전화 건 문자열을 E. 164 형식으로 정규화 해야 합니다. 비즈니스용 Skype 서버는 호출 된 ID 및 발신자 번호 프레젠테이션을 조작할 수 있는 기능을 제공 합니다.
ms.openlocfilehash: dddeee5ef7784d9c2c433763da4c8b6145611e49
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045070"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 변환 규칙 정의

비즈니스용 Skype 서버 Enterprise Voice는 전자 164 형식으로 정규화 된 전화 번호를 기반으로 통화를 라우팅합니다. 즉, RNL (역방향 번호 조회)를 수행 하 여 일치 하는 SIP URI로 변환할 수 있도록 모든 전화 건 문자열을 E. 164 형식으로 정규화 해야 합니다. 비즈니스용 Skype 서버는 호출 된 ID 및 발신자 번호 프레젠테이션을 조작할 수 있는 기능을 제공 합니다.

비즈니스용 Skype 서버를 사용 하는 경우 호출 된 당사자의 전화 번호 (전화 번호)는 E. 164에서 트렁크 피어에 필요한 로컬 전화 걸기 형식 (즉, 관련 게이트웨이, PBX (private branch exchange) 또는 SIP)으로 변환 될 수 있습니다. 트렁크) 이 작업을 수행 하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 변환 하는 변환 규칙을 하나 이상 정의 해야 합니다.

## <a name="caller-id-presentation"></a>발신자 번호 표시

비즈니스용 Skype 서버는 통화 당사자의 전화 번호 (즉, 발신자가 통화 하는 전화 번호)를 트렁크 피어에 필요한 로컬 전화 걸기 형식으로 변환 하는 옵션을 제공 합니다. 예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.

**비즈니스용 Skype 서버 제어판을 사용 하 여 발신자 ID를 구성 하려면**

1. RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [대리인 설치 권한을](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)참조 하십시오.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 제어판을 엽니다. 비즈니스용 Skype 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Install and open the 관리 도구](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. 왼쪽 탐색 모음에서 **음성 라우팅**을 클릭한 다음 **트렁크 구성**을 클릭합니다.
4. 트렁크 구성 페이지에서 기존 트렁크 (예: **전역** 트렁크)를 두 번 클릭 하 여 **트렁크 구성 편집** 대화 상자를 표시 합니다.
5. 발신자 번호를 구성 하려면 다음을 수행 합니다.
    - Enterprise Voice 배포에서 사용 가능한 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택하려면 **선택**을 클릭합니다. **통화 번호 변환 규칙**에서 트렁크와 연결할 규칙을 클릭 하 고 **확인**을 클릭 합니다.
    - 새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기**를 클릭합니다. 
    - 트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시**를 클릭합니다.
    - 기존 변환 규칙을 복사 하 여 새 규칙을 정의 하는 시작 점으로 사용 하려면 규칙 이름을 클릭 하 고 **복사**를 클릭 한 다음 **붙여넣기**를 클릭 합니다.
    - 트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거**를 클릭합니다.

> [!Warning] 
> 연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오. 

## <a name="called-id-presentation"></a>호출 되는 ID 프레젠테이션

> [!Important]
> 트렁크 피어에서 변환 규칙을 구성하는 *대신*, 하나 이상의 변환 규칙을 Enterprise Voice 트렁크 구성에 연결하는 기능을 사용할 수 있습니다. 트렁크 피어에 대한 변환 규칙을 구성한 경우 변환 규칙을 Enterprise Voice 트렁크 구성과 연결하지 마십시오. 두 규칙이 충돌할 수 있기 때문입니다. 

다음 방법 중 하나를 사용하여 변환 규칙을 만들거나 수정할 수 있습니다.

- [변환 규칙 작성 도구를 사용](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) 하 여 시작 번호, 길이, 제거할 숫자 및 추가할 숫자에 대 한 값을 지정한 다음 비즈니스용 Skype 서버 제어판에서 해당 일치 패턴 및 변환 규칙을 생성 하도록 합니다.
- [정규식을 수동으로 작성](#create-or-modify-a-translation-rule-manually) 하 여 일치 패턴 및 변환 규칙을 정의 합니다.

> [!Note]
> 정규식을 작성 하는 방법에 대 한 자세한 내용은 [.Net Framework 정규식](http://go.microsoft.com/fwlink/p/?linkId=140927)을 참조 하십시오. 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>변환 규칙 작성 도구를 사용 하 여 변환 규칙 만들기 또는 수정

변환 규칙 작성 도구에 값 집합을 입력 하 여 변환 규칙을 정의 하 고 비즈니스용 Skype 서버 제어판을 사용 하도록 설정 하 여 해당 일치 패턴 및 변환 규칙을 생성 하려면 다음 단계를 수행 합니다. 

**변환 규칙 작성 도구를 사용하여 규칙을 정의하려면**

1. RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [대리인 설치 권한을](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)참조 하십시오.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 제어판을 엽니다. 비즈니스용 Skype 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Install and open the 관리 도구](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. 변환 규칙 정의를 시작 하려면 [configure a 트렁크 with 미디어 바이패스를 사용 하 여 구성](GET LINK AFTER MIGRATION), 10 단계 또는 [미디어 바이패스 없이 트렁크 구성](GET LINK AFTER MIGRATION) 의 단계 9를 실행 합니다.
4. **새 변환 규칙** 또는 **변환 규칙 편집** 페이지의 **이름** 아래에서 변환 대상 숫자 패턴을 설명하는 이름을 입력합니다.
5. 반드시 **설명**에 변환 규칙에 대 한 설명을 입력 합니다 (예: **US 국제 시외 전화 걸기**).
6. 대화 상자의 **변환 규칙 작성** 섹션에 있는 다음 필드에 값을 입력합니다.
    - **시작 숫자**: (선택 사항) 패턴을 일치시킬 선행 자릿수를 지정합니다. 예를 들어 이 필드에 +를 입력하면 +로 시작하는 E.164 형식의 번호가 일치됩니다.
    - **길이**: 일치하는 패턴의 자릿수를 지정하고 패턴을 이 길이와 정확히 일치하는 번호와 일치시킬지 또는 이 길이 이상인 번호와 일치시킬지 또는 길이에 상관없이 일치시킬지 여부를 선택합니다 예를 들어 **11**을 입력하고 드롭다운 목록에서 **최소**를 선택하면 길이가 11자리 이상인 번호와 일치하게 됩니다.
    - **제거할 숫자**: (선택 사항) 제거할 시작 자릿수를 지정합니다. 예를 들어 **1**을 입력하면 번호 앞부분에서 +가 제거됩니다.
    - **추가할 숫자**: (선택 사항) 변환된 번호의 앞에 추가할 자릿수를 지정합니다. 예를 들어 **011**을 입력하면 규칙이 적용될 때 변환된 번호 앞에 011이 추가됩니다.
    
    이러한 필드에 입력 하는 값은 일치 및 **변환** 규칙 필드에 **패턴** 에 반영 됩니다. 예를 들어 위의 예제 값을 지정 하는 경우 matc h 필드에 대 한 **패턴**의 결과 정규식은 다음과 같습니다.
    
    **^\+(\d{9}\d +) $** 

    **변환 규칙** 필드에서는 변환된 번호 형식에 대한 패턴이 지정됩니다. 이 패턴은 두 부분으로 되어 있습니다.
    - 일치하는 패턴의 자릿수를 나타내는 값(예: **$1**)
    - (선택 사항) **추가할 숫자** 필드에 입력하여 번호 앞에 추가할 수 있는 값

    위의 예 값을 사용하면 **변환 규칙** 필드에 **011$1**이 나타납니다.
    
    이 변환 규칙이 적용되면 +441235551010이 011441235551010이 됩니다.
7. **확인**을 클릭하여 변환 규칙을 저장합니다.
8. **확인**을 클릭하여 트렁크 구성을 저장합니다.
9. **트렁크 Configuratio**n 페이지에서 **커밋을**클릭 하 고 **모두 커밋을**클릭 합니다. 

> [!Note]
> 변환 규칙을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 [음성 라우팅 구성에 보류 중인 변경 내용 게시](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx)를 참조 하십시오. 

### <a name="create-or-modify-a-translation-rule-manually"></a>수동으로 변환 규칙 만들기 또는 수정

일치하는 패턴 및 변환 규칙에 대한 정규식을 작성하여 변환 규칙을 정의하려면 다음 단계를 따르십시오. 

**변환 규칙을 수동으로 정의하려면**

1. RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [대리인 설치 권한을](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)참조 하십시오.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 제어판을 엽니다. 비즈니스용 Skype 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Install and open the 관리 도구](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. 변환 규칙 정의를 시작 하려면 [configure a 트렁크 with 미디어 바이패스를 사용 하 여 구성](GET LINK AFTER MIGRATION), 10 단계 또는 [미디어 바이패스 없이 트렁크 구성](GET LINK AFTER MIGRATION) 의 단계 9를 실행 합니다.
4. **새 변환 규칙** 또는 **변환 규칙 편집** 페이지의 **이름** 필드에 변환 대상 숫자 패턴을 설명하는 이름을 입력합니다.
5. 반드시 **설명**에 변환 규칙에 대 한 설명을 입력 합니다. 예를 들면 **US 국제 시외 전화 걸기**입니다.
6. **변환 규칙 작성** 섹션 아래쪽의 **편집**을 클릭합니다.
7. **정규식**입력에 다음을 입력 합니다.
    - **다음 패턴과 일치시킴**에 변환할 숫자와 일치시키는 데 사용할 패턴을 지정합니다.
    - **변환 규칙**에 변환된 숫자 형식의 패턴을 지정합니다.

    예를 들어 **이 패턴과 일치** 하 고 **변환 규칙**에서 **011 $1** 을 입력 ** ^ \+하면 (\d{9}\d +) $** 가 + 441235551010을 011441235551010으로 변환 합니다.
8. **확인**을 클릭하여 변환 규칙을 저장합니다.
9. **확인**을 클릭하여 트렁크 구성을 저장합니다.
10. **트렁크 구성** 페이지에서 **커밋**을 클릭하고 **모두 커밋**을 클릭합니다. 

> [!Note] 
> 변환 규칙을 만들거나 수정할 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 [음성 라우팅 구성에 보류 중인 변경 내용 게시](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx)를 참조 하십시오. 
