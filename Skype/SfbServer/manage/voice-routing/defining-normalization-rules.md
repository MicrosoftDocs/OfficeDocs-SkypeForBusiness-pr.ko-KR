---
title: 비즈니스용 Skype 서버에서 정규화 규칙 정의
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
description: 비즈니스용 Skype 서버 정규화 규칙은 .NET Framework 정규식을 사용 하 여 전화 건 번호를 E. 164 형식으로 변환 합니다. 즉, 정규화 규칙은 사용자가 건 전화 번호를 받아이 번호를 비즈니스용 Skype 서버에서 내부적으로 사용 하는 형식으로 변환 합니다. 각 다이얼 플랜에는 하나 이상의 정규화 규칙을 할당해야 합니다.
ms.openlocfilehash: 42ec43a08d1c155f61869bdfebf07e94ac040e56
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028849"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 정규화 규칙 정의

비즈니스용 Skype 서버 정규화 규칙은 .NET Framework 정규식을 사용 하 여 전화 건 번호를 E. 164 형식으로 변환 합니다. 즉, 정규화 규칙은 사용자가 건 전화 번호를 받아이 번호를 비즈니스용 Skype 서버에서 내부적으로 사용 하는 형식으로 변환 합니다. 각 다이얼 플랜에는 하나 이상의 정규화 규칙을 할당해야 합니다.

정규화 규칙에 대 한 자세한 내용은 [다이얼 플랜 및 정규화 규칙](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx)을 참조 하십시오.

정규식을 작성 하는 방법에 대 한 자세한 내용은 [.Net Framework 정규식](http://go.microsoft.com/fwlink/p/?linkId=140927)을 참조 하십시오.

다음 방법 중 하나를 사용하여 정규화 규칙을 정의하거나 편집할 수 있습니다.
- [ **정규화 규칙 작성** 도구를 사용](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) 하 여 시작 번호, 길이, 제거할 숫자 및 추가할 숫자에 대 한 값을 지정한 다음 비즈니스용 Skype 서버 제어판에서 해당 일치 패턴 및 변환 규칙을 생성 하도록 합니다.
- [정규식을 수동으로 작성](#create-or-modify-a-normalization-rule-manually) 하 여 일치 패턴 및 변환 규칙을 정의 합니다. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정

비즈니스용 Skype 서버 제어판에서 정규화 규칙을 만들거나 수정 하려면 다음 단계를 완료 합니다. 

**정규화 규칙 작성을 사용 하 여 규칙을 정의 하려면**

1. RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [대리인 설치 권한을](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)참조 하십시오.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 제어판을 엽니다. 비즈니스용 Skype 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Install and open the 관리 도구](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. 반드시 11 단계 또는 10 단계 [를 통해 다이얼 플랜 수정을](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) 통해 [다이얼 플랜 만들기](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) 의 단계를 수행 합니다. 
4. **새 정규화 규칙** 또는 **정규화 규칙 편집**에서 **이름** 으로 정규화 되는 번호 패턴을 설명 하는 이름 (예: **: 5digitextension**)을 입력 합니다.
5. 반드시 **설명**에 정규화 규칙에 대 한 설명을 입력 합니다 (예: "5 자리 내선 번호 변환").
6. **정규화 규칙 작성**의 다음 필드에 값을 입력 합니다.
    - **시작 숫자**: (선택 사항) 패턴을 일치 시킬 전화 건 번호의 앞에 오는 숫자를 지정 합니다. 예를 들어 425로 시작 하는 전화 번호를 패턴으로 일치 시키려면 **425** 을 입력 합니다.
    - **길이**: 일치 패턴의 자릿수를 지정 하 고 패턴을이 길이와 정확히 일치 시킬 것인지, 아니면 적어도이 길이에 해당 하는 전화 건 번호 인지 또는 전화 건 번호와 일치 하는지 여부를 선택 합니다.
    - **제거할 숫자**: (선택 사항) 패턴을 일치 시킬 전화 건 번호에서 제거할 시작 자릿수를 지정 합니다.
    - **추가할 숫자**: (선택 사항) 패턴을 일치 시킬 전화 건 번호에 추가할 숫자를 지정 합니다.
    
    이러한 필드에 입력 하는 값은 일치 및 **변환 규칙** **에 대 한 패턴** 에 반영 됩니다. 예를 들어 **시작 자리** 를 비워 두면 **길이** 필드에 **7** **을 입력**하 고 **제거할 자리**에 **0** 을 지정 하 여 **일치 시킬 패턴** 의 정규식을 찾습니다.

    **^ (\d{7}) $**

7. **변환 규칙**에서 다음과 같이 변환 된 E. 164 전화 번호 형식에 대 한 패턴을 지정 합니다.
    - 일치 패턴에 지정 된 자릿수를 나타내는 값입니다. 예를 들어 일치 하는 패턴이 **^ (\d{7}) $** 인 경우 변환 규칙에서 $1는 7 자리 전화 걸기 번호를 나타냅니다.
    - 반드시 숫자를 **추가할** 숫자 필드에 값을 입력 하 여 변환 된 번호 앞에 추가할 자릿수를 지정 합니다 (예: **+ 1425**).
    
    예를 들어 **일치 시킬 패턴이** **{7}^ (\d) $** 를 포함 하는 경우 전화 건 번호의 패턴으로 **+ 1425 $1** 을 전자 164로 포함 하면 규칙은 5550100에서 + 14255550100로 정규화 됩니다. ****

8. (선택 사항) 정규화 규칙의 결과가 조직 내부의 전화 번호가 되는 경우 **내부 확장**을 선택합니다.
9. 반드시 숫자를 입력 하 여 정규화 규칙을 테스트 한 다음 **이동을**클릭 합니다. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.
    > [!Note] 
    > 아직 테스트를 통과하지 않는 정규화 규칙을 저장한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 [음성 라우팅 테스트](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx)를 참조 하십시오. 

10. 정규화 규칙을 저장하려면 **확인**을 클릭합니다.
11. 다이얼 플랜을 저장하려면 **확인**을 클릭합니다.
12. **다이얼 플랜** 페이지에서 **커밋**을 클릭한 다음 **모두 커밋**을 클릭합니다. 
    > [!Note]
    > 정규화 규칙을 만들거나 변경할 때마다 모두 커밋 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 [음성 라우팅 구성에 보류 중인 변경 내용 게시](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx)를 참조 하십시오. 

## <a name="create-or-modify-a-normalization-rule-manually"></a>수동으로 정규화 규칙 만들기 또는 수정

정규화 규칙을 수동으로 만들거나 수정하려면 다음 단계를 수행합니다.

**정규화 규칙을 수동으로 정의하려면**

1. RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [대리인 설치 권한을](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)참조 하십시오.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 제어판을 엽니다. 비즈니스용 Skype 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Install and open the 관리 도구](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. 반드시 11 단계 또는 10 단계 [를 통해 다이얼 플랜 수정을](GET LINK AFTER MIGRATION) 통해 [다이얼 플랜 만들기](GET LINK AFTER MIGRATION) 의 단계를 수행 합니다.  
4. **새 정규화 규칙** 또는 **정규화 규칙 편집**의 **이름**에 정규화 중인 숫자 패턴을 설명하는 이름을 입력합니다(예: 정규화 규칙의 이름을 **5DigitExtension**으로 지정).
5. 반드시 **설명**에 정규화 규칙에 대 한 설명을 입력 합니다 (예: "5 자리 내선 번호 변환").
6. **정규화 규칙 작성**에서 **편집**을 클릭합니다.
7. 정규식 입력에 다음을 입력합니다.
    - **다음 패턴과 일치시킴**에서 전화 건 전화 번호와 일치시키는 데 사용할 패턴을 지정합니다.
    - **변환 규칙**에서 변환된 E.164 전화 번호 형식에 대한 패턴을 지정합니다.

    예를 들어 **이 패턴과 일치** 하는 **^{7}(\d) $** 를 입력 하 고 **변환 규칙**에서 **+ 1425 $1** 을 입력할 경우 규칙은 5550100에서 + 14255550100로 정규화 합니다.

8. (선택 사항) 정규화 규칙의 결과가 조직 내부의 전화 번호가 되는 경우 **내부 확장**을 선택합니다.
9. 반드시 숫자를 입력 하 여 정규화 규칙을 테스트 한 다음 **이동을**클릭 합니다. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.

    > [!Note]
    > 아직 테스트를 통과하지 않는 정규화 규칙을 저장한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 [음성 라우팅 테스트](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx)를 참조 하십시오. 

10. 정규화 규칙을 저장하려면 **확인**을 클릭합니다.
11. 다이얼 플랜을 저장하려면 **확인**을 클릭합니다.
12. **다이얼 플랜** 페이지에서 **commi**t를 클릭 하 고 **모두 커밋을**클릭 합니다. 
