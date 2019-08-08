---
title: 비즈니스용 Skype에서 큐 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: 비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 큐를 만들거나 수정 합니다.
ms.openlocfilehash: b58ec9065eea1cc2dd8686b07ea798ac71c460fa
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233677"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>비즈니스용 Skype에서 큐 만들기 또는 수정
 
비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 큐를 만들거나 수정 합니다.
  
큐는 에이전트가 전화를 대답할 때까지 호출자를 보유 합니다. 응답 그룹 응용 프로그램이 사용 가능한 에이전트를 검색 하는 경우 목록에 나열 된 순서 대로 에이전트 그룹을 검색 합니다. 큐에 할당 되는 에이전트 그룹을 선택 하 고 큐에 대기 시킬 수 있는 호출 수를 제한 하는 방법, 에이전트가 전화를 받을 때까지 대기 하는 시간 간격 등의 대기열 동작을 지정할 수 있습니다.
  
다음 절차 중 하나를 사용 하 여 큐를 만들거나 수정 합니다.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>비즈니스용 Skype Server 제어판을 사용 하 여 큐를 만들거나 수정 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.
    
    > [!NOTE]
    > 관리 되는 워크플로에 대 한 위임 된 응답 그룹 관리자 중 하나에 해당 하는 경우 응답 그룹 큐를 만들거나 수정 하 고 관리 하는 워크플로에 할당할 수 있습니다. 
  
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **응답 그룹**을 클릭 한 다음 **대기열**을 클릭 합니다.
    
4. **큐** 페이지에서 다음 중 하나를 수행 합니다.
    
   - 새 큐를 만들려면 **새로 만들기**를 클릭 합니다. **서비스 선택**에서 검색 필드에 큐를 추가 하려는 **applicationserver** 서비스 이름의 일부나 전부를 입력 합니다. 서비스 결과 목록에서 원하는 서비스를 클릭 한 다음 **확인**을 클릭 합니다.
    
   - 기존 대기열을 수정 하려면 검색 필드에 대기열 이름 전체 또는 일부를 입력 합니다. 결과 대기열 목록에서 원하는 대기열을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
5. **이름**에 큐 식별 이름을 입력 합니다.
    
6. **설명**에 대기열에 대 한 설명을 입력 합니다.
    
7. **그룹**에서 큐에 할당 하려는 그룹을 지정 합니다. 다음 중 하나를 수행 합니다. 
    
   - 큐에 그룹을 추가 하려면 **선택을**클릭 합니다. 그룹 검색 **선택** 필드에 큐에 할당할 에이전트 그룹의 이름 전체 또는 일부를 입력 하 고 원하는 에이전트 그룹을 클릭 한 다음 **확인**을 클릭 합니다.
    
   - 큐에서 그룹을 제거 하려면 에이전트 그룹 목록에서 제거 하려는 그룹을 클릭 한 다음 **제거**를 클릭 합니다.
    
   - 에이전트를 검색 하는 순서를 변경 하려면 에이전트 그룹 목록에서 그룹을 클릭 한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭 합니다.
    
     > [!NOTE]
     > 서버에서 큐에 대해 사용 가능한 에이전트를 검색할 때 그룹 순서를 사용 합니다. 즉, 목록의 첫 번째 그룹이 먼저 검색 되 고, 그 다음에 목록의 두 번째 그룹이 표시 됩니다. 
  
8. 에이전트가 전화에 응답 하기 전에 호출자가 대기를 대기할 최대 기간을 지정 하려면 **큐 시간 초과 사용** 확인란을 선택 하 고 다음을 수행 합니다.
    
    에서. **시간 제한 (초)** 에 호출자가 상담원의 전화 응답을 대기할 수 있는 최대 시간 (초)을 지정 합니다.
    
    b. **통화 동작**에서 다음과 같이 통화 시간이 초과 될 때 발생 하는 동작을 선택 합니다.
    
   - 제한 시간 후에 통화 연결을 끊으려면 **연결 끊기를**클릭 합니다.
    
   - 음성 메일로 통화를 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 **sip 주소** 필드에 sip: * \<username (사용자 이름\>**\<\> * @ domainname) 형식으로 음성 메일 주소를 입력 합니다. 예: sip:bob@contoso.com).
    
   - 통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 **sip 주소** 필드에 sip: * \<number\>*@ *\<\>* (예: sip:+14255550121@contoso.com).
    
   - 다른 사용자에 게 통화를 착신 전환 하려면 **sip 주소로 전달을**클릭 한 다음 **sip 주소** 필드에 sip: _ \<username\>_@ _\<domainname\>_ 형식으로 사용자의 URI를 입력 합니다.
    
   - 다른 대기열로 통화를 착신 전환 하려면 **다른 대기열로 전달을**클릭 한 다음 사용 하려는 대기열을 찾습니다.
    
9. 큐에 저장할 수 있는 최대 통화 수를 지정 하려면 **큐 오버플로 사용** 확인란을 선택 하 고 다음을 수행 합니다.
    
    에서. **최대 통화 수**에서 큐에 대기 시킬 최대 통화 수를 선택 합니다. 
    
    b. **통화를 착신 전환**하는 동안 큐가 꽉 차면 착신 전환 되는 통화를 선택 합니다. **최신** 통화 또는 **가장 오래 된 통화**입니다.
    
    c. **통화 동작**에서 오버플로 임계값이 다음과 같이 충족 될 때 발생 하는 작업을 선택 합니다.
    
   - 제한 시간 후에 통화 연결을 끊으려면 **연결 끊기를**클릭 합니다.
    
   - 음성 메일로 통화를 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 **sip 주소** 필드에 sip: * \<username (사용자 이름\>**\<\> * @ domainname) 형식으로 음성 메일 주소를 입력 합니다. 예: sip:bob@contoso.com).
    
   - 통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 **sip 주소** 필드에 sip: * \<number\>*@ *\<\>* (예: sip:+14255550121@contoso.com).
    
   - 다른 사용자에 게 통화를 착신 전환 하려면 **sip 주소로 전달을**클릭 한 다음 **sip 주소** 필드에 sip: _ \<username\>_@ _\<domainname\>_ 형식으로 사용자의 URI를 입력 합니다.
    
   - 다른 대기열로 통화를 착신 전환 하려면 **다른 대기열로 전달을**클릭 한 다음 사용 하려는 대기열을 찾습니다.
    
10. **커밋**을 클릭합니다.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 큐를 만들거나 수정 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.
    
    > [!NOTE]
    > 관리 되는 워크플로에 대해 위임 된 응답 그룹 관리자 중 하나에 해당 하는 경우 에이전트 그룹 및 큐를 만들고 에이전트 그룹을 큐에 할당할 수 있습니다. 
  
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 큐 시간 제한 임계값에 도달 했을 때 재생할 프롬프트를 만들고 변수에 저장 합니다. 명령줄에서 다음을 실행 합니다.
    
   ```
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   예를 들면 다음과 같습니다.
    
   ```
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > 프롬프트에 오디오 파일을 사용 하려면 **CsRgsAudioFile** cmdlet을 사용 합니다. 자세한 내용은 [가져오기-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)을 참조 하세요. 
  
4. 큐 시간 제한 임계값에 도달 했을 때 수행할 작업을 정의 하 고 변수에 저장 합니다. 명령줄에서 다음을 실행 합니다.
    
   ```
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > 사용할 수 있는 동작과 해당 구문에 대 한 자세한 내용은 [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)을 참조 하세요. 
  
    예를 들면 다음과 같습니다.
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. 큐 오버플로 임계값에 도달 했을 때 재생 되는 프롬프트를 만들고 변수에 저장 합니다. 명령줄에서 다음을 실행 합니다.
    
   ```
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   예를 들면 다음과 같습니다.
    
   ```
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > 프롬프트에 오디오 파일을 사용 하려면 **CsRgsAudioFile** cmdlet을 사용 합니다. 자세한 내용은 [가져오기-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)을 참조 하세요. 
  
6. 큐 오버플로 임계값에 도달 했을 때 수행할 작업을 정의 하 고 변수에 저장 합니다. 명령줄에서 다음을 실행 합니다.
    
   ```
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > 사용할 수 있는 동작과 해당 구문에 대 한 자세한 내용은 [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)을 참조 하세요. 
  
    예를 들면 다음과 같습니다.
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. 응답 그룹 서비스의 서비스 이름을 검색 하 고 변수에 할당 합니다. 명령줄에서 다음을 실행 합니다.
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. 큐에 할당할 에이전트 그룹의 id를 가져옵니다. 명령줄에서 다음을 실행 합니다.
    
   ```
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > 에이전트 그룹을 만드는 방법에 대 한 자세한 내용은 [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps) 를 참조 하세요.
  
9. 큐를 만듭니다. 명령줄에서 다음을 실행 합니다.
    
   ```
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   예를 들면 다음과 같습니다.
    
   ```
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. 대기열이 생성 되었는지 확인 합니다. 런
    
    ```
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>참고 항목

[새로운 CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[새로운 CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[새로운 CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[가져오기-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[제거-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
