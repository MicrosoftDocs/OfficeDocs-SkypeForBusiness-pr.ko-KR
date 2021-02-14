---
title: 비즈니스용 Skype에서 음성 경로 만들기 또는 수정
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
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: '요약: 비즈니스용 Skype 서버 제어판을 사용하여 비즈니스용 Skype 서버에서 음성 경로를 만들거나 수정하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: c9f1a234bf8aeeb1bfeb05f1464a48eb0e964405
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820458"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>비즈니스용 Skype에서 음성 경로 만들기 또는 수정
 
**요약:** 비즈니스용 Skype 서버 제어판을 사용하여 비즈니스용 Skype 서버에서 음성 경로를 만들거나 수정하는 방법을 배워야 합니다.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 음성 경로를 만들 수 있습니다.

1. RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator,** **CsServerAdministrator 또는 CsAdministrator** 관리  역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭합니다.
    
4. **경로** 를 클릭합니다.
    
5. **새로하기를** 클릭하여 새 음성 경로 대화 **상자를** 표시합니다.
    
6. **이름에** 음성 경로에 대한 설명적인 이름을 입력합니다.
    
7. (선택 사항) **설명에서** 음성 경로에 대한 추가 설명 정보를 입력합니다.
    
8. 이 경로에 수용할 패턴을 지정하려면 패턴 작성 도구를  사용하여 정규식을 생성하거나 정규식을 수동으로 작성할 수 있습니다.
    
   - 패턴 작성 **도구를** 사용하여 정규식을 생성하려면 다음과 같이 값을 입력합니다. 다음 두 가지 유형의 패턴 일치를 지정할 수 있습니다.
    
   - **허용할** 번호의 시작 자릿수: 이 경로에서 수용해야 하는(필요한 경우 선행 + 포함) prefix 값을 입력합니다. 예를 들어 +425를 입력한 다음 추가를 **클릭합니다.** 경로에 포함할 각 prefix 값에 대해 이 작업을 반복합니다.
    
   - **예외:** Prefix 값에 대해 하나 이상의 예외를 지정하려는 경우, 해당 prefix를 강조 표시하고 **Exceptions를 클릭합니다.** 이 경로를 수용하지 않을 일치하는 패턴에  대해 하나 이상의 값을 입력합니다. 예를 들어 경로에서 +425237로 시작하는 번호를 제외하려면 **예외** 필드에 +425237 값을 입력한 다음 **확인을 클릭합니다.**
    
   - 일치 패턴을 수동으로 정의하려면  패턴을 작성하여 일치하는 도구로 편집을 클릭한 다음 .NET Framework 정규식을 입력하여 경로가 적용되는 대상 전화 번호에 대한 일치 패턴을 지정합니다.  정규식을 작성하는 방법에 대한 자세한 내용은 [".NET Framework 정규식"을 참조합니다.](https://go.microsoft.com/fwlink/p/?linkId=140927) 
    
9. **발신자 번호가** 발신자에게 나타나지 못하게 하려는 경우 발신자 번호 표시 안 를 선택합니다. 이 옵션을 선택하는 경우 받는 사람의 발신자 **ID** 표시에 나타나는 대체 발신자 ID를 지정해야 합니다.
    
10. 하나 이상의 트렁크를 음성 경로와 연결하려면  추가를 클릭한 다음 목록에서 트렁크를 선택합니다.
    
11. 하나 이상의 PSTN(Public Switched Telephone Network) 사용법을 음성  경로와 연결하려면 선택한 배포에 대해 정의된 PSTN 사용 레코드 목록에서 레코드 선택을 클릭하고 Enterprise Voice 선택합니다.
    
    > [!NOTE]
    > 사용 가능한 각 PSTN 사용 레코드의 속성을 확인하면 비즈니스용 Skype에서 PSTN 사용 레코드 [보기를 참조하세요.](view-pstn-usage-records.md) > PSTN 사용 레코드를 만들거나 편집하려면 음성 정책 만들기 또는 수정을 참조하고 비즈니스용 [Skype에서 PSTN 사용 레코드를 구성합니다.](voice-policy-and-pstn-usage-records.md)
  
12. 최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다. 목록에서 레코드의 위치를 변경하려면 레코드 이름을 강조 표시하고 위쪽 또는 아래쪽 화살표를 클릭합니다.
    
    > [!NOTE]
    > PSTN 사용 레코드가 나열되는 순서가 중요한 음성 정책과 달리 음성 경로에 PSTN 사용 레코드가 나열되는 순서는 중요하지 않습니다. 그러나 사용 빈도별로 목록을 구성하는 것이 좋습니다. 예: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (비즈니스용 Skype 서버가 목록을 위쪽에서 아래로 트래버스합니다.) 
  
13. (선택 사항) 테스트 필드에  변환된 번호 입력에 값을 입력하고 이동을 **클릭합니다.** 테스트 결과가 필드 아래에 표시됩니다.
    
14. 확인을 **클릭하여** 음성 경로를 저장합니다.
    
    > [!IMPORTANT]
    > 음성 경로를 만들 때마다 모두 커밋  명령을 실행하여 구성 변경을 게시해야 합니다. 자세한 내용은 비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 [게시를 참조하세요.](voice-route-config-changes.md) 
  
### <a name="to-modify-a-voice-route"></a>음성 경로를 수정하려면

1. 비즈니스용 Skype 서버 제어판을 니다.
    
2. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭한 다음 **경로** 를 클릭합니다.
    
3. 경로 **페이지에서** 다음 방법 중 하나를 사용하여 음성 경로를 수정합니다.
    
   - 음성 경로 이름을 클릭하고 **편집을** 클릭한 다음 세부 정보 **표시를 클릭합니다.**
    
   - 음성 경로 이름을 클릭하고 **편집을** 클릭한 다음 **복사를** 클릭한 다음 **붙여넣기 를 클릭합니다.** 방금 만든 음성 경로의 새 복사본을 클릭하고 편집을 클릭한 다음 세부 정보 **표시를 클릭합니다.**
    
4. 음성 **경로** 편집  페이지의 이름 필드에 음성 경로에 대한 설명적인 이름을 입력합니다.
    
5. (선택 사항) 설명 **필드에** 음성 경로에 대한 추가 설명 정보를 입력합니다.
    
6. 이 경로에 수용할 패턴을 지정하려면 패턴 작성  도구를 사용하여 정규식을 생성하거나 정규식을 수동으로 작성할 수 있습니다.
    
   - 패턴 작성 **도구를** 사용하여 정규식을 생성하려면 다음과 같이 값을 입력합니다. 다음 두 가지 유형의 패턴 일치를 지정할 수 있습니다.
    
   - **허용할** 번호의 시작 자릿수: 이 경로에서 수용해야 하는(필요한 경우 선행 + 포함) prefix 값을 입력합니다. 예를 들어 +425를 입력한 다음 추가를 **클릭합니다.** 경로에 포함할 각 prefix 값에 대해 이 작업을 반복합니다.
    
   - **예외:** Prefix 값에 대해 하나 이상의 예외를 지정하려는 경우, 해당 prefix를 강조 표시하고 **Exceptions를 클릭합니다.** 이 경로를 수용하지 않을 일치하는 패턴에  대해 하나 이상의 값을 입력합니다. 예를 들어 경로에서 +425237로 시작하는 번호를 제외하려면 **예외** 필드에 +425237 값을 입력한 다음 **확인을 클릭합니다.**
    
   - 일치 패턴을 수동으로 정의하려면  패턴을 작성하여 일치하는 도구로 편집을 클릭한 다음 .NET Framework 정규식을 입력하여 경로가 적용되는 대상 전화 번호에 대한 일치 패턴을 지정합니다.  정규식을 작성하는 방법에 대한 자세한 내용은 [".NET Framework 정규식"을 참조합니다.](https://go.microsoft.com/fwlink/p/?linkId=140927) 
    
7. 아웃바운드 통화를 하는 전화의 **ID를** 호출 받는 사람에게 표시하지 않을 경우 발신자 번호 표시 안 를 선택합니다. 이 옵션을 선택하는 경우 받는 사람의 발신자 **ID** 표시에 나타나는 대체 발신자 ID를 지정해야 합니다.
    
8. 하나 이상의 PSTN(Public Switched Telephone Network) 트렁크를 음성 경로와 연결하려면 추가를 클릭한 다음 목록에서 트렁크를 선택합니다. 
    
9. 하나 이상의 PSTN 사용법을 음성 경로와  연결하려면 사용자 지정 배포에 대해 정의된 PSTN 사용 레코드 목록에서 레코드 선택을 클릭하고 Enterprise Voice 클릭합니다.
    
    > [!NOTE]
    > 사용 가능한 각 PSTN 사용 레코드의 속성을 확인하면 비즈니스용 Skype에서 PSTN 사용 레코드 [보기를 참조하세요.](view-pstn-usage-records.md) > PSTN 사용 레코드를 만들거나 편집하려면 음성 정책 만들기 또는 수정을 참조하고 비즈니스용 [Skype에서 PSTN](voice-policy-and-pstn-usage-records.md)사용 레코드를 구성합니다. 
  
10. 최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다. 목록에서 레코드의 위치를 변경하려면 레코드 이름을 강조 표시하고 위쪽 또는 아래쪽 화살표를 클릭합니다.
    
    > [!NOTE]
    > PSTN 사용 레코드가 나열되는 순서가 중요한 음성 정책과 달리 음성 경로의 PSTN 사용 레코드 순서는 중요하지 않습니다. 그러나 목록을 사용 빈도별로 구성하는 것이 좋습니다(예: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup). (비즈니스용 Skype 서버가 목록을 위쪽에서 아래로 트래버스합니다.) 
  
11. (선택 사항) 테스트 필드에  변환된 번호 입력에 값을 입력하고 이동을 **클릭합니다.** 테스트 결과가 필드 아래에 표시됩니다.
    
12. **확인** 을 클릭합니다.
    
13. 경로 **페이지에서** 커밋을 클릭한 다음 모두 **커밋을 클릭합니다.**  
    
    > [!NOTE]
    > 음성 경로를 만들거나 수정할 때마다 모든 커밋 명령을 실행하여 구성 변경을 게시해야 합니다.  자세한 내용은 작업 설명서에서 비즈니스용 [Skype의](voice-route-config-changes.md) 음성 라우팅 구성에 보류 중인 변경 내용 게시를 참조하십시오.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype에서 PSTN 사용 레코드 보기](view-pstn-usage-records.md)
  
[음성 정책 만들기 또는 수정 및 비즈니스용 Skype에서 PSTN 사용 레코드 구성](voice-policy-and-pstn-usage-records.md)
  
[비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md)

