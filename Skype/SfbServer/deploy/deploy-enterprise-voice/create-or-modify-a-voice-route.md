---
title: 2013에서 음성 경로를 만들거나 비즈니스용 Skype
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
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: '요약: 제어판을 사용하여 비즈니스용 Skype 서버 음성 경로를 만들거나 수정하는 비즈니스용 Skype 서버 방법을 설명하는 방법을 제공합니다.'
ms.openlocfilehash: 8b1ca3dc6120fb4e8432736672ee4821e894da56
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611243"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>2013에서 음성 경로를 만들거나 비즈니스용 Skype
 
**요약:** 비즈니스용 Skype 서버 제어판을 사용하여 음성 경로를 만들거나 수정하는 비즈니스용 Skype 서버 대해 자세히 알아보습니다.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>제어판을 사용하여 음성 비즈니스용 Skype 서버 만들 수 있습니다.

1. RTCUniversalServerAdmins 그룹의 구성원이나 **CsVoiceAdministrator, CsServerAdministrator** 또는 **CsAdministrator** 관리  역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭합니다.
    
4. **경로** 를 클릭합니다.
    
5. 새로 **추가를** 클릭하여 새 음성 경로 **대화 상자를** 표시합니다.
    
6. **이름에** 음성 경로에 대한 설명적인 이름을 입력합니다.
    
7. (선택 사항) **설명에** 음성 경로에 대한 추가 설명 정보를 입력합니다.
    
8. 이 경로에 수용할 패턴을 지정하려면 패턴 작성 도구를  사용하여 정규식을 생성하거나 정규식을 수동으로 작성할 수 있습니다.
    
   - 일치하도록 **패턴** 작성 도구를 사용하여 정규식을 생성하려면 다음과 같이 값을 입력합니다. 다음 두 가지 유형의 패턴 일치를 지정할 수 있습니다.
    
   - **허용할** 번호의 시작 자릿수: 이 경로에서 수용해야 하는 prefix 값(필요한 경우 선행 + 포함)을 입력합니다. 예를 들어 +425를 입력한 다음 추가 를 **클릭합니다.** 경로에 포함할 각 prefix 값에 대해 이 작업을 반복합니다.
    
   - **예외:** prefix 값에 대해 하나 이상의 예외를 지정하려면, prefix를 강조 표시하고 **예외 를 클릭합니다.** 이 경로를 수용하지 않을 일치하는 패턴에  대해 하나 이상의 값을 입력합니다. 예를 들어 경로에서 +425237 번호를 제외하려면 예외 필드에 +425237 값을 입력한  다음 확인을 **클릭합니다.**
    
   - 일치 패턴을 수동으로 정의하려면  일치할  패턴 작성 도구에서 편집을 클릭한 다음 .NET Framework 정규식을 입력하여 경로가 적용되는 대상 전화 번호에 대한 일치 패턴을 지정합니다. 정규식을 작성하는 방법에 대한 자세한 내용은 [".NET Framework 정규식"을 참조합니다.](/dotnet/standard/base-types/regular-expressions) 
    
9. 아웃바운드 호출을 하는 전화의 **ID가** 호출 받는 사람에게 나타나지 못하게 하려는 경우 발신자 번호 표시 안 를 선택합니다. 이 옵션을 선택하는 경우 받는 사람의 발신자 **ID** 표시에 나타나는 대체 발신자 ID를 지정해야 합니다.
    
10. 하나 이상의 트렁크를 음성 경로와 연결하려면  추가를 클릭한 다음 목록에서 트렁크를 선택합니다.
    
11. 하나 이상의 PSTN(Public Switched Telephone Network) 사용법을 음성  경로와 연결하려면 선택을 클릭하고 배포에 대해 정의된 PSTN 사용 레코드 목록에서 Enterprise Voice 선택합니다.
    
    > [!NOTE]
    > 사용 가능한 각 PSTN 사용 레코드의 속성을 확인 내용은 [View PSTN usage records in 비즈니스용 Skype.](view-pstn-usage-records.md) > PSTN 사용 레코드를 만들거나 편집하려면 Create [or modify a voice policy and configure PSTN usage records in 비즈니스용 Skype](voice-policy-and-pstn-usage-records.md)
  
12. 최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다. 목록에서 레코드의 위치를 변경하려면 레코드 이름을 강조 표시하고 위쪽 또는 아래쪽 화살표를 클릭합니다.
    
    > [!NOTE]
    > PSTN 사용 레코드가 나열되는 순서가 중요한 음성 정책과 달리 음성 경로에 PSTN 사용 레코드가 나열되는 순서는 중요하지 않습니다. 그러나 목록을 사용 빈도별로 구성하는 것이 좋습니다. 예: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (비즈니스용 Skype 서버 맨 아래에서 목록을 트래버스합니다.) 
  
13. (선택 사항) 테스트할 변환된 번호 입력 필드에 값을 **입력하고** 이동을 **클릭합니다.** 테스트 결과가 필드 아래에 표시됩니다.
    
14. 확인을 **클릭하여** 음성 경로를 저장합니다.
    
    > [!IMPORTANT]
    > 음성 경로를 만들 때마다 모두 커밋  명령을 실행하여 구성 변경을 게시해야 합니다. 자세한 내용은 음성 라우팅 [구성에](voice-route-config-changes.md)보류 중인 변경 내용 게시를 비즈니스용 Skype. 
  
### <a name="to-modify-a-voice-route"></a>음성 경로를 수정하려면

1. 제어판을 비즈니스용 Skype 서버 를 니다.
    
2. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭한 다음 **경로** 를 클릭합니다.
    
3. 경로 **페이지에서** 다음 방법 중 하나를 사용하여 음성 경로를 수정합니다.
    
   - 음성 경로 이름을 클릭하고 편집 **을** 클릭한 다음 자세한 정보 **표시를 클릭합니다.**
    
   - 음성 경로 이름을 클릭하고 **편집,** 복사를 **클릭한** 다음 **붙여넣기 를 클릭합니다.** 방금 만든 음성 경로의 새 복사본을 클릭하고 편집, 자세한 정보 **표시를 클릭합니다.**
    
4. 음성 **경로** 편집 페이지의 이름 **필드에** 음성 경로에 대한 설명적인 이름을 입력합니다.
    
5. (선택 사항) 설명 **필드에** 음성 경로에 대한 추가 설명 정보를 입력합니다.
    
6. 이 경로에 수용할 패턴을 지정하려면 패턴 작성  도구를 사용하여 정규식을 생성하거나 정규식을 수동으로 작성할 수 있습니다.
    
   - 일치하도록 **패턴** 작성 도구를 사용하여 정규식을 생성하려면 다음과 같이 값을 입력합니다. 다음 두 가지 유형의 패턴 일치를 지정할 수 있습니다.
    
   - **허용할** 번호의 시작 자릿수: 이 경로에서 수용해야 하는 prefix 값(필요한 경우 선행 + 포함)을 입력합니다. 예를 들어 +425를 입력한 다음 추가 를 **클릭합니다.** 경로에 포함할 각 prefix 값에 대해 이 작업을 반복합니다.
    
   - **예외:** prefix 값에 대해 하나 이상의 예외를 지정하려면, prefix를 강조 표시하고 **예외 를 클릭합니다.** 이 경로를 수용하지 않을 일치하는 패턴에  대해 하나 이상의 값을 입력합니다. 예를 들어 경로에서 +425237 번호를 제외하려면 예외 필드에 +425237 값을 입력한  다음 확인을 **클릭합니다.**
    
   - 일치 패턴을 수동으로 정의하려면  일치할  패턴 작성 도구에서 편집을 클릭한 다음 .NET Framework 정규식을 입력하여 경로가 적용되는 대상 전화 번호에 대한 일치 패턴을 지정합니다. 정규식을 작성하는 방법에 대한 자세한 내용은 [".NET Framework 정규식"을 참조합니다.](/dotnet/standard/base-types/regular-expressions) 
    
7. 아웃바운드 통화를 하는 전화의 **ID가** 호출 받는 사람에게 나타나지 못하게 하려는 경우 발신자 번호 표시 안 를 선택합니다. 이 옵션을 선택하는 경우 받는 사람의 발신자 **ID** 표시에 나타나는 대체 발신자 ID를 지정해야 합니다.
    
8. 하나 이상의 PSTN(Public Switched Telephone Network) 트렁크를 음성 경로와 연결하려면 추가를 클릭하고 목록에서 트렁크를 선택합니다. 
    
9. 하나 이상의 PSTN 사용법을 음성 경로와  연결하려면 선택을 클릭하고 해당 배포에 대해 정의된 PSTN 사용 레코드 목록에서 Enterprise Voice 선택합니다.
    
    > [!NOTE]
    > 사용 가능한 각 PSTN 사용 레코드의 속성을 확인 내용은 [View PSTN usage records in 비즈니스용 Skype.](view-pstn-usage-records.md) > PSTN 사용 레코드를 만들거나 편집하려면 [Create or modify a voice policy and configure PSTN usage records in 비즈니스용 Skype.](voice-policy-and-pstn-usage-records.md) 
  
10. 최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다. 목록에서 레코드의 위치를 변경하려면 레코드 이름을 강조 표시하고 위쪽 또는 아래쪽 화살표를 클릭합니다.
    
    > [!NOTE]
    > PSTN 사용 레코드가 나열되는 순서가 중요한 음성 정책과 달리 음성 경로의 PSTN 사용 레코드 순서는 중요하지 않습니다. 그러나 RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup과 같은 사용 빈도별로 목록을 구성하는 것이 좋습니다. (비즈니스용 Skype 서버 맨 아래에서 목록을 트래버스합니다.) 
  
11. (선택 사항) 테스트할 변환된 번호 입력 필드에 값을 **입력하고** 이동을 **클릭합니다.** 테스트 결과가 필드 아래에 표시됩니다.
    
12. **확인** 을 클릭합니다.
    
13. 경로 **페이지에서** **커밋을** 클릭한 다음 모두 **커밋을 클릭합니다.** 
    
    > [!NOTE]
    > 음성 경로를 만들거나 수정할 때마다 모두 커밋 명령을 실행하여 구성 변경을 게시해야 합니다.  자세한 내용은 작업 설명서에서 [Publish pending changes to the voice routing configuration in 비즈니스용 Skype](voice-route-config-changes.md) 참조하십시오.
  
## <a name="see-also"></a>참고 항목

[PSTN 사용 레코드 보기 비즈니스용 Skype](view-pstn-usage-records.md)
  
[음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 비즈니스용 Skype](voice-policy-and-pstn-usage-records.md)
  
[음성 라우팅 구성에 보류 중인 변경 내용을 비즈니스용 Skype](voice-route-config-changes.md)