---
title: 'Lync Server 2013: 큐 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 672752856d7f36e374646782cc36a031c81a9af0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a>Lync Server 2013에서 큐 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

다음 절차를 사용하여 큐를 만들거나 수정할 수 있습니다.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a>Lync Server 제어판을 사용 하 여 큐를 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.
    
    <div>
    

    > [!NOTE]  
    > 관리 워크플로의 위임된 응답 그룹 관리자 중 하나인 경우 응답 그룹 큐를 만들거나 수정하고 여러분이 관리하는 워크플로에 할당할 수 있습니다.

    
    </div>

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **응답 그룹**을 클릭하고 **큐**를 클릭합니다.

4.  **큐** 페이지에서 다음 중 하나를 수행합니다.
    
      - 새 큐를 만들려면 **새로 만들기**를 클릭합니다. **서비스 선택**에서 검색 필드에 큐를 추가할 **ApplicationServer** 서비스의 이름 일부나 전체를 입력합니다. 서비스 결과 목록에서 원하는 서비스를 클릭하고 **확인**을 클릭합니다.
    
      - 기존 큐를 수정하려면 검색 필드에 큐의 이름을 모두 또는 일부분 입력합니다. 결과 큐 목록에서 원하는 큐를 클릭하고 **편집**을 클릭한 다음 **자세한 정보 표시**를 클릭합니다.

5.  **이름**에 큐를 식별하는 이름을 입력합니다.

6.  **설명**에 큐의 설명을 입력합니다.

7.  **그룹**에서 큐를 할당할 그룹을 지정합니다. 다음 중 하나를 수행합니다.
    
      - 큐에 그룹을 추가하려면 **선택**을 클릭하고 **그룹 선택** 검색 필드에 큐에 할당할 에이전트 그룹의 이름을 일부분 또는 모두 입력한 다음 **찾기**를 클릭합니다.
    
      - 큐에서 그룹을 제거하려면 에이전트 그룹 목록에서 제거할 그룹을 클릭한 다음 **제거**를 클릭합니다.
    
      - 에이전트가 검색되는 순서를 변경하려면 에이전트 그룹 목록에서 그룹을 클릭한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭합니다.
        
        <div>
        

        > [!NOTE]  
        > 서버는 큐에서 사용 가능한 에이전트를 검색할 때 그룹 순서를 사용합니다. 즉, 목록의 첫 번째 그룹이 먼저 검색되고 목록의 두 번째 그룹 등이 차례로 검색됩니다.

        
        </div>

8.  에이전트가 전화를 받을 때까지 발신자가 대기하도록 할 최대 시간을 지정하려면 **큐 시간 초과 사용** 확인란을 선택하고 다음을 수행합니다.
    
    1.  **제한 시간(초)** 에서 에이전트가 전화를 받을 때까지 발신자가 대기하는 최대 시간(초)을 지정합니다.
    
    2.  **통화 작업**에서 통화 시간이 초과되면 수행할 작업을 다음 중에서 선택합니다.
    
    <!-- end list -->
    
      - 제한 시간 이후에 전화를 끊으려면 **연결 끊기**를 클릭합니다.
    
      - 통화를 음성 메일로 착신 전환 하려면 **음성 메일로 착신 전환**을 클릭 한 다음 **sip 주소** 필드에 음성 메일 사용자\<이름\>@\<domainname\> 을 입력 합니다 (예: sip:bob@contoso.com).
    
      - 통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 착신 전환을**클릭 한 다음 **sip 주소** \<필드에 전화 번호를 sip: number\>@\<domainname\> (예: sip:+14255550121@contoso.com) 형식으로 입력 합니다.
    
      - 통화를 다른 사용자에 게 착신 전환 하려면 sip **주소로 전달을**클릭 한 다음 **sip 주소** 필드에 사용자의 URI를 sip\<: username\>@\<도메인\>형식으로 입력 합니다.
    
      - 통화를 다른 큐로 착신 전환하려면 **다른 큐로 착신 전환**을 클릭한 다음 사용할 큐를 찾습니다.

9.  큐에 보관할 최대 통화 수를 지정하려면 **큐 오버플로 사용** 확인란을 선택하고 다음을 수행합니다.
    
    1.  **최대 통화 수**에서 큐에 보관할 최대 통화 수를 선택합니다.
    
    2.  **착신 전환**에서 큐가 가득 차면 착신 전환할 통화를 **가장 최근 통화** 또는 **가장 오래된 통화** 중에서 선택합니다.
    
    3.  **통화 작업**에서 오버플로 임계값에 도달하면 수행할 작업을 다음 중에서 선택합니다.
    
    <!-- end list -->
    
      - 제한 시간 이후에 전화를 끊으려면 **연결 끊기**를 클릭합니다.
    
      - 통화를 음성 메일로 착신 전환 하려면 **음성 메일로 착신 전환**을 클릭 한 다음 **sip 주소** 필드에 음성 메일 사용자\<이름\>@\<domainname\> 을 입력 합니다 (예: sip:bob@contoso.com).
    
      - 통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 착신 전환을**클릭 한 다음 **sip 주소** \<필드에 전화 번호를 sip: number\>@\<domainname\> (예: sip:+14255550121@contoso.com) 형식으로 입력 합니다.
    
      - 통화를 다른 사용자에 게 착신 전환 하려면 sip **주소로 전달을**클릭 한 다음 **sip 주소** 필드에 사용자의 URI를 sip\<: username\>@\<도메인\>형식으로 입력 합니다.
    
      - 통화를 다른 큐로 착신 전환하려면 **다른 큐로 착신 전환**을 클릭한 다음 사용할 큐를 찾습니다.

10. **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a>Windows PowerShell을 사용 하 여 큐를 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.
    
    <div>
    

    > [!NOTE]  
    > 관리 워크플로의 위임된 응답 그룹 관리자 중 하나인 경우 에이전트 그룹을 만들 에이전트 그룹을 큐에 할당할 수 있습니다.

    
    </div>

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에서 다음을 실행하여 큐 시간 초과 임계값에 도달하면 재생할 음성 안내를 만들고 변수에 저장합니다.
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    예:
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > 오디오 파일을 음성 안내에 사용하려면 <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet을 사용합니다. 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">import-csrgsaudiofile</A>를 참조 하십시오.

    
    </div>

4.  명령줄에서 다음을 실행하여 큐 시간 초과 임계값에 도달하면 수행할 동작을 정의하고 변수에 저장합니다.
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > 가능한 작업 및 해당 구문에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">new-csrgscallaction</A>를 참조 하십시오.

    
    </div>
    
    예:
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  명령줄에서 다음을 실행하여 큐 오버플로 임계값에 도달하면 재생할 음성 안내를 만들고 변수에 저장합니다.
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    예:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > 오디오 파일을 음성 안내에 사용하려면 <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet을 사용합니다. 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">import-csrgsaudiofile</A>를 참조 하십시오.

    
    </div>

6.  명령줄에서 다음을 실행하여 큐 오버플로 임계값에 도달하면 수행할 동작을 정의하고 변수에 저장합니다.
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > 가능한 작업 및 해당 구문에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">new-csrgscallaction</A>를 참조 하십시오.

    
    </div>
    
    예를 들면 다음과 같습니다.
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  응답 그룹 서비스의 서비스 이름을 검색하여 변수 하나에 할당합니다. 명령줄에서 다음을 실행합니다.
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  큐에 할당할 에이전트 그룹의 id를 가져옵니다. 명령줄에서 다음을 실행합니다.
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > 에이전트 그룹을 만드는 방법에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">get-csrgsagentgroup</A> 를 참조 하십시오.

    
    </div>

9.  명령줄에서 다음을 실행하여 큐를 만듭니다.
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    예를 들면 다음과 같습니다.
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. 다음을 실행하여 큐가 만들어졌는지 확인합니다.
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-csrgsqueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[Get-csrgsqueue](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[New-csrgsprompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[New-csrgscallaction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[Get-csrgsqueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[Import-csrgsaudiofile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[Get-csrgsqueue을 제거 합니다.](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

