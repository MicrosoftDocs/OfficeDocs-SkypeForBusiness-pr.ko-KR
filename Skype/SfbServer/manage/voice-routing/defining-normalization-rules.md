---
title: 2013에서 정규화 규칙 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 비즈니스용 Skype 서버 정규화 규칙은 .NET Framework 정규식을 사용하여 전화 걸기 번호를 E.164 형식으로 변환합니다. 즉, 정규화 규칙은 사용자가 전화를 걸고 해당 번호를 전화 번호가 내부적으로 사용되는 형식으로 비즈니스용 Skype 서버. 각 다이얼 플랜에는 하나 이상의 정규화 규칙을 할당해야 합니다.
ms.openlocfilehash: 97e3cada0ab95cbd3a457e2c5f71b1ead9d9ce23
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398852"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>2013에서 정규화 규칙 비즈니스용 Skype 서버

비즈니스용 Skype 서버 정규화 규칙은 .NET Framework 정규식을 사용하여 전화 걸기 번호를 E.164 형식으로 변환합니다. 즉, 정규화 규칙은 사용자가 전화를 걸고 해당 번호를 전화 번호가 내부적으로 사용되는 형식으로 비즈니스용 Skype 서버. 각 다이얼 플랜에는 하나 이상의 정규화 규칙을 할당해야 합니다.

정규화 규칙에 대한 자세한 내용은 다이얼 플랜 [및 정규화 규칙을 참조합니다](/previous-versions/office/lync-server-2013/lync-server-2013-dial-plans-and-normalization-rules).

정규식을 작성하는 방법에 대한 자세한 내용은 정규식 .NET Framework [참조합니다](/dotnet/standard/base-types/regular-expressions).

다음 방법 중 하나를 사용하여 정규화 규칙을 정의하거나 편집할 수 있습니다.
- [**정규**](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule)화 규칙 작성 도구를 사용하여 시작 자릿수, 길이, 제거할 자릿수 및 추가할 자릿수 값을 지정한 다음 비즈니스용 Skype 서버 제어판에서 해당 일치 패턴 및 변환 규칙을 생성할 수 있습니다.
- [정규식을 수동으로](#create-or-modify-a-normalization-rule-manually) 작성하여 일치 패턴 및 변환 규칙을 정의합니다. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>정규화 규칙 작성을 사용하여 정규화 규칙 만들기 또는 수정

제어판에서 정규화 규칙을 만들거나 수정하려면 다음 비즈니스용 Skype 서버 완료합니다. 

**정규화 규칙 작성을 사용하여 규칙을 정의**

1. RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다. 자세한 내용은 [Delegate setup permissions을 참조합니다](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. 브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 Skype 도구 설치 [및 열기를 참조합니다](../../management-tools/install-and-open-administrative-tools.md).
3. (선택 사항) 11단계까지 [](../../deploy/deploy-enterprise-voice/dial-plans.md#to-create-a-dial-plan) 의 다이얼 플랜 만들기 또는 10단계까지 다이얼 플랜 [수정](../../deploy/deploy-enterprise-voice/dial-plans.md#to-modify-a-dial-plan)의 단계를 따릅니다. 
4. 새 **정규** 화 규칙 또는 정규화 규칙 편집에서 **이름** 에 정규화되는 숫자 패턴을 설명하는 이름을 입력합니다(예: **5DigitExtension**).
5. (선택 사항) 설명 **에** 정규화 규칙에 대한 설명을 입력합니다(예: "5자리 내선 번호 변환").
6. 정규 **화 규칙 작성에서** 다음 필드에 값을 입력합니다.
    - **시작 숫자**: (선택 사항) 패턴이 일치할 전화 걸기 번호의 앞 자릿수 지정 예를 들어 **425** 로 시작되는 전화 걸기 번호와 패턴이 일치하게 하려는 경우 425를 입력합니다.
    - **길이**: 일치 패턴의 자릿수를 지정하고 패턴이 이 길이와 정확히 일치할지, 적어도 이 길이의 전화 걸기 번호와 일치하는지 또는 모든 길이의 전화 걸기 번호를 일치할지 여부를 선택합니다.
    - **제거할 숫자**: (선택 사항) 패턴이 일치할 전화 걸기 번호에서 제거할 시작 자릿수 지정.
    - **추가할 숫자**: (선택 사항) 패턴이 일치할 전화 걸기 번호에 추가할 숫자를 지정합니다.
    
    이러한 필드에 입력하는 값은 일치하기 **위해 패턴** 및 변환 규칙 **에 반영됩니다**. 예를 들어 시작 숫자를 비  워 두면 길이 필드에 **정확히 7** 을 입력하고  제거할 숫자에 **0** 을 지정하면 일치 **할 패턴** 의 결과 정규식은 다음과 같습니다.

    **^(\d{7})$**

7. 변환 **규칙에서** 다음과 같이 변환된 E.164 전화 번호 형식의 패턴을 지정합니다.
    - 일치 패턴에 지정된 자릿수 값을 나타내는 값입니다. 예를 들어 일치 패턴이 **^(\d)$이면{7}** 변환 규칙의 $1은 7자리 전화 걸기 번호를 나타냈습니다.
    - (선택 사항) 숫자 필드에 값을 입력  하여 변환된 번호에 추가할 숫자를 지정합니다(예: **+1425**).
    
    예를 들어 일치시키  면 패턴에 전화 걸기 번호의 패턴으로 **^(\d{7})$** 가 포함되어  있으며 변환 규칙에 E.164 전화 번호에 대한 패턴으로 **+1425$** 1이 포함되어 있는 경우 규칙은 5550100을 +14255550100.

8. (선택 사항) 정규화 규칙의 결과가 조직 내부의 전화 번호가 되는 경우 **내부 확장** 을 선택합니다.
9. (선택 사항) 정규화 규칙을 테스트할 번호를 입력한 다음 이동을 **클릭합니다**. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.
    > [!Note] 
    > 아직 테스트를 통과하지 않는 정규화 규칙을 저장한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 [음성 라우팅 테스트를 참조합니다](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing). 

10. 정규화 규칙을 저장하려면 **확인** 을 클릭합니다.
11. 다이얼 플랜을 저장하려면 **확인** 을 클릭합니다.
12. **다이얼 플랜** 페이지에서 **커밋** 을 클릭한 다음 **모두 커밋** 을 클릭합니다. 
    > [!Note]
    > 정규화 규칙을 만들거나 변경할 때마다 모두 커밋 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 음성 라우팅 구성에 보 [류 중인 변경 내용 게시를 참조합니다](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>수동으로 정규화 규칙 만들기 또는 수정

정규화 규칙을 수동으로 만들거나 수정하려면 다음 단계를 수행합니다.

**정규화 규칙을 수동으로 정의하려면**

1. RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다. 자세한 내용은 [Delegate setup permissions을 참조합니다](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. 브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 Skype 도구 설치 [및 열기를 참조합니다](../../management-tools/install-and-open-administrative-tools.md).
3. (선택 사항) 11단계까지 [](GET LINK AFTER MIGRATION) 의 다이얼 플랜 만들기 또는 10단계까지 다이얼 플랜 [수정](GET LINK AFTER MIGRATION)의 단계를 따릅니다.  
4. **새 정규화 규칙** 또는 **정규화 규칙 편집** 의 **이름** 에 정규화 중인 숫자 패턴을 설명하는 이름을 입력합니다(예: 정규화 규칙의 이름을 **5DigitExtension** 으로 지정).
5. (선택 사항) 설명 **에** 정규화 규칙에 대한 설명을 입력합니다(예: "5자리 내선 번호 변환").
6. **정규화 규칙 작성** 에서 **편집** 을 클릭합니다.
7. 정규식 입력에 다음을 입력합니다.
    - **다음 패턴과 일치시킴** 에서 전화 건 전화 번호와 일치시키는 데 사용할 패턴을 지정합니다.
    - **변환 규칙** 에서 변환된 E.164 전화 번호 형식에 대한 패턴을 지정합니다.

    예를 들어 이 패턴 일치에 **^(\d{7})$** 를  입력하고 **변환** 규칙에 **+1425$1** 을 입력하면 규칙은 5550100에서 +14255550100.

8. (선택 사항) 정규화 규칙의 결과가 조직 내부의 전화 번호가 되는 경우 **내부 확장** 을 선택합니다.
9. (선택 사항) 정규화 규칙을 테스트할 번호를 입력한 다음 이동을 **클릭합니다**. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.

    > [!Note]
    > 아직 테스트를 통과하지 않는 정규화 규칙을 저장한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 [음성 라우팅 테스트를 참조합니다](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing). 

10. 정규화 규칙을 저장하려면 **확인** 을 클릭합니다.
11. 다이얼 플랜을 저장하려면 **확인** 을 클릭합니다.
12. 다이얼 **플랜 페이지에서** 커밋을 클릭한 다음 모두 커밋 **을 클릭합니다**.