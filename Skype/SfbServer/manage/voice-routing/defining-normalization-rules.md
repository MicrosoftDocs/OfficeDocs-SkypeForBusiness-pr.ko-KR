---
title: 비즈니스용 Skype 서버에서 정규화 규칙 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype 서버 정규화 규칙은 .NET Framework 정규식을 사용 하 여 전화를 거는 전화 번호를 전자 164 형식으로 변환 합니다. 즉, 정규화 규칙은 사용자가 거는 전화 번호를 사용 하 여 비즈니스용 Skype 서버에서 내부적으로 사용 하는 형식으로 변환 합니다. 각 다이얼 플랜에는 하나 이상의 정규화 규칙을 할당해야 합니다.
ms.openlocfilehash: e5156816de13a8d59e3e6eea4890046d5b4f586a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187041"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 정규화 규칙 정의

비즈니스용 Skype 서버 정규화 규칙은 .NET Framework 정규식을 사용 하 여 전화를 거는 전화 번호를 전자 164 형식으로 변환 합니다. 즉, 정규화 규칙은 사용자가 거는 전화 번호를 사용 하 여 비즈니스용 Skype 서버에서 내부적으로 사용 하는 형식으로 변환 합니다. 각 다이얼 플랜에는 하나 이상의 정규화 규칙을 할당해야 합니다.

정규화 규칙에 대 한 자세한 내용은 [다이얼 플랜 및 정규화 규칙](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx)을 참조 하세요.

정규식을 작성 하는 방법에 대 한 자세한 내용은 [.Net Framework 정규식](http://go.microsoft.com/fwlink/p/?linkId=140927)을 참조 하세요.

다음 방법 중 하나를 사용 하 여 정규화 규칙을 정의 하거나 편집할 수 있습니다.
- [ **정규화 규칙 작성** 도구를 사용](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) 하 여 시작 숫자, 길이, 추가할 숫자에 대 한 값을 지정한 다음 비즈니스용 Skype 서버 제어판에서 해당 하는 일치 패턴 및 번역 규칙을 생성 하도록 합니다. 너를 위해.
- [정규식을 수동으로 작성](#create-or-modify-a-normalization-rule-manually) 하 여 일치 패턴 및 번역 규칙을 정의 합니다. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정

비즈니스용 Skype Server 제어판에서 정규화 규칙을 만들거나 수정 하려면 다음 단계를 완료 합니다. 

**정규화 규칙 빌드를 사용 하 여 규칙을 정의 하려면**

1. RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [대리인 설정 사용](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)을 참조 하세요.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 제어판을 엽니다. 비즈니스용 Skype 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [관리 도구 설치 및 열기](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. ) 11 단계 또는 10 단계를 통해 다이얼 [플랜 수정을](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) 통해 [다이얼 플랜 만들기](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) 의 단계를 따릅니다. 
4. **새 정규화 규칙** 또는 **정규화 규칙 편집**에서 **이름** 에 정규화 되는 번호 패턴을 설명 하는 이름 (예: **5DigitExtension**)을 입력 합니다.
5. ) **설명**에 정규화 규칙에 대 한 설명을 입력 합니다 (예: "5 자리 확장명 변환").
6. **정규화 규칙 작성**에서 다음 필드에 값을 입력 합니다.
    - **시작 번호**: (선택 사항) 패턴을 일치 시킬 전화 거는 번호의 선행 자릿수를 지정 합니다. 예를 들어 패턴에서 425로 시작 하는 전화 번호를 일치 시키려면 **425** 을 입력 합니다.
    - **길이**: 일치 패턴의 자릿수를 지정 하 고 패턴을이 길이와 정확히 일치 시킬 것인지 아니면 최소이 길이의 전화 접속 번호와 일치 하거나 길이에 관계 없이 번호를 선택할 수 있습니다.
    - **제거할 자릿수**: (선택 사항) 패턴을 일치 시킬 전화 번호에서 제거할 시작 자릿수를 지정 합니다.
    - **더할 자릿수**: (선택 사항) 패턴을 일치 시킬 전화 번호에 추가할 숫자를 지정 합니다.
    
    이러한 필드에 입력 하는 값은 일치 및 **번역 규칙** **에 따라 패턴** 에 반영 됩니다. 예를 들어 **시작 자릿수** **** 를 비워 두면 **길이** 필드에 **7** 을 입력 하 고 **제거할 자리**에 **0** 을 지정 하 고 일치 시킬 **패턴** 의 정규식은 다음과 같습니다.

    **^ (\d{7}) $**

7. **번역 규칙**에서 다음과 같이 변환 된 전자 164 전화번호의 형식에 대 한 패턴을 지정 합니다.
    - 일치 패턴에 지정 된 자릿수를 나타내는 값입니다. 예를 들어 일치 하는 패턴이 **^ (\d{7}) $** 인 경우 번역 규칙의 $1에서 7 자리 전화 번호를 나타냅니다.
    - ) 숫자를 **추가할** 숫자 필드에 값을 입력 하 여 앞으로 변환할 숫자를 지정 합니다 (예: **+ 1425**).
    
    예를 들어 **일치 하는 패턴** 에 **^ (\d{7}) $** 가 있는 경우, 전화를 걸고 **** 있는 번호의 패턴으로 **+ 1425 $1** 이 포함 된 경우이 규칙은 5550100에서 + 14255550100로 정규화 됩니다.

8. ) 정규화 규칙이 조직 내부의 전화 번호를 반환 하는 경우 **내부 확장**을 선택 합니다.
9. ) 번호를 입력 하 여 정규화 규칙을 테스트 한 다음 **이동을**클릭 합니다. 테스트 결과가 **테스트에 대 한 숫자 입력**아래에 표시 됩니다.
    > [!Note] 
    > 아직 테스트를 통과 하지 않은 정규화 규칙을 저장 한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 [음성 라우팅 테스트](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx)를 참조 하세요. 

10. **확인** 을 클릭 하 여 정규화 규칙을 저장 합니다.
11. **확인** 을 클릭 하 여 다이얼 플랜을 저장 합니다.
12. **다이얼 플랜** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다. 
    > [!Note]
    > 정규화 규칙을 만들거나 변경할 때마다 모두 커밋 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 [음성 라우팅 구성에 보류 중인 변경 내용 게시](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx)를 참조 하세요. 

## <a name="create-or-modify-a-normalization-rule-manually"></a>수동으로 정규화 규칙 만들기 또는 수정

정규화 규칙을 수동으로 만들거나 수정 하려면 다음 단계를 완료 합니다.

**정규화 규칙을 수동으로 정의 하려면**

1. RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [대리인 설정 사용](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)을 참조 하세요.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 제어판을 엽니다. 비즈니스용 Skype 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [관리 도구 설치 및 열기](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. ) 11 단계 또는 10 단계를 통해 다이얼 [플랜 수정을](GET LINK AFTER MIGRATION) 통해 [다이얼 플랜 만들기](GET LINK AFTER MIGRATION) 의 단계를 따릅니다.  
4. **새 정규화 규칙** 또는 **정규화 규칙 편집**에서 **이름** 에 정규화 되는 번호 패턴을 설명 하는 이름 (예: 정규화 규칙 **5DigitExtension**의 이름)을 입력 합니다.
5. ) **설명**에 정규화 규칙에 대 한 설명을 입력 합니다 (예: "5 자리 확장명 변환").
6. **정규화 규칙 작성**에서 **편집**을 클릭 합니다.
7. 정규식 입력에 다음을 입력 합니다.
    - **이 패턴과 일치**하는 경우 전화를 거는 전화 번호와 일치 하는 데 사용할 패턴을 지정 합니다.
    - **번역 규칙**에서 번역 된 전자 전화번호의 형식에 대 한 패턴을 지정 합니다.

    예를 들어 **이 패턴과 일치** 하는 **^{7}(\d) $** 를 입력 하 고 **번역 규칙**에 **+ 1425 $1** 을 입력할 경우 규칙은 5550100에서 + 14255550100로 정규화 됩니다.

8. ) 정규화 규칙이 조직 내부의 전화 번호를 반환 하는 경우 **내부 확장**을 선택 합니다.
9. ) 번호를 입력 하 여 정규화 규칙을 테스트 한 다음 **이동을**클릭 합니다. 테스트 결과가 **테스트에 대 한 숫자 입력**아래에 표시 됩니다.

    > [!Note]
    > 아직 테스트를 통과 하지 않은 정규화 규칙을 저장 한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 [음성 라우팅 테스트](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx)를 참조 하세요. 

10. **확인** 을 클릭 하 여 정규화 규칙을 저장 합니다.
11. **확인** 을 클릭 하 여 다이얼 플랜을 저장 합니다.
12. **다이얼 플랜** 페이지에서 **commi**t를 클릭 한 다음 **모두 커밋을**클릭 합니다. 
