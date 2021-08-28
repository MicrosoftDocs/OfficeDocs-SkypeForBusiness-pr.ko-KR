---
title: 사용자 지정에서 정규화 규칙을 만들거나 비즈니스용 Skype
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
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: '요약: 이 문서에서 정규화 규칙을 정의, 생성 및 수정하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 3e06aa9821761803c033255c4da3f636ba296dda
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626210"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>사용자 지정에서 정규화 규칙을 만들거나 비즈니스용 Skype

**요약:** 사용자 지정 규칙에서 정규화 규칙을 정의, 생성 및 수정하는 비즈니스용 Skype 서버.

규칙에서 정규화 규칙을 정의, 작성 및 비즈니스용 Skype 서버.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>정규화 규칙 작성을 사용하여 정규화 규칙을 정의

1. Open 비즈니스용 Skype 서버 제어판

2. (선택 사항) Create or [modify a dial plan in 비즈니스용 Skype 서버](dial-plans.md) through step 11 or Modify a Dial [Plan](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan) through step 10의 단계를 따릅니다.

3. 새 **정규화** 규칙 또는 정규화 규칙 편집에서 **이름에서** 정규화되는 번호 패턴을 설명하는 이름을 입력합니다(예: 5DigitExtension).

4. (선택 사항) **설명에** 정규화 규칙에 대한 설명을 입력합니다(예: "5자리 내선 번호 변환").

5. 정규화 **규칙 작성에서** 다음 필드에 값을 입력합니다.

   - **시작 숫자(선택** 사항) 패턴이 일치할 전화 걸기 번호의 선행 숫자를 지정합니다. 예를 들어 패턴을 425로 시작하여 전화 걸기 번호와 일치하게 하려는 경우 425를 입력합니다.

   - **Length** 일치 패턴의 숫자 수를 지정하고 패턴이 이 길이와 정확히 일치할지, 적어도 이 길이의 전화 걸기 번호와 일치하는지 또는 모든 길이의 전화 걸기 번호와 일치할지 여부를 선택합니다.

   - **제거할 숫자(선택** 사항) 패턴이 일치할 전화 걸기 번호에서 제거할 시작 자릿수(선택 사항)를 지정합니다.

   - **추가할 숫자(선택** 사항) 패턴을 일치하려는 전화 걸기 번호에 추가할 숫자를 지정합니다.

     이러한 필드에 입력하는 값은 일치하기 **위해 패턴** 및 변환 규칙 **에 반영됩니다.** 예를 들어 시작  숫자를 비워 두면 길이 필드에 7을 입력하고 정확히 를 선택하고 제거할 **숫자에** 0을 지정하면  **일치할 패턴의** 결과 정규식은 다음과 같습니다.

     ^(\d{7})$

6. 변환 **규칙에서** 다음과 같이 변환된 E.164 전화 번호 형식의 패턴을 지정합니다.

   - 일치 패턴에 지정된 자릿수 값을 나타내는 값입니다. 예를 들어 일치 패턴이 ^(\d )$이면 변환 규칙의 $1은 7자리 전화 걸기 번호를 {7} 나타냈습니다.

   - (선택 사항) 숫자 필드에 값을 **입력하여** 변환된 숫자(예: +1425)에 추가할 숫자를 지정합니다.

     예를 들어  일치시키면 패턴에 전화 걸기 번호에 대한 패턴으로^(\d )$가 포함되어 있으며 변환 규칙에 E.164 전화 번호에 대한 패턴으로 {7} +1425$1이 포함되어 있는 경우 규칙은 5550100을 +14255550100. 

7. (선택 사항) 정규화 규칙의 결과가 조직 내부의 전화 번호가 되는 경우 **내부 확장** 을 선택합니다.

8. (선택 사항) 정규화 규칙을 테스트할 숫자를 입력한 다음 이동을 **클릭합니다.** 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.

    > [!NOTE]
    > 아직 테스트를 통과하지 않는 정규화 규칙을 저장한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 [Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing)를 참조하십시오.

9. 정규화 규칙을 저장하려면 **확인** 을 클릭합니다.

10. 다이얼 플랜을 저장하려면 **확인** 을 클릭합니다.

11. **다이얼 플랜** 페이지에서 **커밋** 을 클릭한 다음 **모두 커밋** 을 클릭합니다.

    > [!NOTE]
    > 정규화 규칙을 만들거나 변경할 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 작업 설명서에서 [Publish pending changes to the voice routing configuration in 비즈니스용 Skype](voice-route-config-changes.md) 참조하십시오.

### <a name="to-define-a-normalization-rule-manually"></a>정규화 규칙을 수동으로 정의하려면

1. Open 비즈니스용 Skype 서버 제어판

2. (선택 사항) 에서 [다이얼](dial-plans.md)플랜 만들기 또는 수정의 단계를 비즈니스용 Skype 서버.

3. **새 정규화** 규칙 또는 정규화 규칙 편집에서 **이름에** 정규화되는 번호 패턴을 설명하는 이름을 입력합니다(예: 정규화 규칙5DigitExtension).

4. (선택 사항) **설명** 필드에 정규화 규칙에 대한 설명을 입력합니다(예: "Translates 5-digit extensions").

5. **정규화 규칙 작성** 에서 **편집** 을 클릭합니다.

6. **정규식 입력** 에 다음을 입력합니다.

   - **다음 패턴과 일치시킴** 에서 전화 건 전화 번호와 일치시키는 데 사용할 패턴을 지정합니다.

   - **변환 규칙** 에서 변환된 E.164 전화 번호 형식에 대한 패턴을 지정합니다.

     예를 들어 이 패턴 일치에 ^(\d )$를 입력하고 변환 규칙에 {7} +1425$1을 입력하면 규칙은 5550100에서 +14255550100.  

7. (선택 사항) 정규화 규칙의 결과가 조직 내부의 전화 번호가 되는 경우 **내부 확장** 을 선택합니다.

8. (선택 사항) 정규화 규칙을 테스트할 번호를 입력한 다음 **이동** 을 클릭합니다. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.

9. 정규화 규칙을 저장하려면 **확인** 을 클릭합니다.

10. 다이얼 플랜을 저장하려면 **확인** 을 클릭합니다.

11. **다이얼 플랜** 페이지에서 **커밋** 을 클릭한 다음 **모두 커밋** 을 클릭합니다.

    > [!NOTE]
    > 정규화 규칙을 만들거나 변경할 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 작업 설명서에서 [Publish pending changes to the voice routing configuration in 비즈니스용 Skype](voice-route-config-changes.md) 참조하십시오.