---
title: 'Lync Server 2013: 음성 경로 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e45404dcd280f4c4eb5337ba4e1a8c1337b409f3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501795"
---
# <a name="create-a-voice-route-in-lync-server-2013"></a>Lync Server 2013에서 음성 경로 만들기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

다음 절차에서는 Lync Server 2013 제어판을 사용 하 여 새 음성 경로를 만드는 방법에 대해 설명 합니다. 기존 경로를 편집 하려면이 절차에 대 한 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md) 참조 하십시오.

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 음성 경로를 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **음성 라우팅**을 클릭합니다.

4.  **경로**를 클릭합니다.

5.  **새로 만들기** 를 클릭 하 여 **새 음성 경로** 대화 상자를 표시 합니다.

6.  **이름**에 음성 경로를 설명 하는 이름을 입력 합니다.

7.  반드시 **설명**에 음성 경로에 대 한 추가 설명 정보를 입력 합니다.

8.  이 경로를 포함할 패턴을 지정 하려면 **일치 시킬 패턴 작성** 도구를 사용 하 여 정규식을 생성 하거나 정규식을 수동으로 작성 하면 됩니다.
    
      - **일치 시킬 패턴 작성** 도구를 사용 하 여 정규식을 생성 하려면 다음과 같이 값을 입력 합니다. 다음과 같은 두 가지 유형의 패턴 일치를 지정할 수 있습니다.
        
          - **허용할 숫자의 시작 숫자입니다.** 이 경로를 적용 해야 하는 접두사 값을 입력 합니다 (필요한 경우 선행 + 포함). 예를 들어 **+ 425**를 입력 한 다음 **추가**를 클릭 합니다. 경로에 포함할 각 접두사 값에 대해이를 반복 합니다.
        
          - **예외:** 접두사 값에 대해 하나 이상의 예외를 지정 하려면 접두사를 강조 표시 하 고 **예외**를 클릭 합니다. 이 경로에 적용 *하지* 않을 일치 패턴에 대해 하나 이상의 값을 입력 합니다. 예를 들어 경로에서 + 425237로 시작 하는 숫자를 제외 하려면 **예외** 필드에 **+ 425237** 값을 입력 하 고 **확인**을 클릭 합니다.
    
      - 일치 패턴을 수동으로 정의 하려면 **일치 시킬 패턴 작성** 도구에서 **편집** 을 클릭 한 다음 .net Framework 정규식을 입력 하 여 경로가 적용 되는 대상 전화 번호에 대 한 일치 패턴을 지정 합니다. 정규식을 작성 하는 방법에 대 한 자세한 내용은의 ".NET Framework 정규식"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .

9.  전화의 ID를 통화 수신자에 게 표시 하지 않으려면 **발신자 Id 억제** 를 선택 합니다. 이 옵션을 선택 하는 경우 받는 사람의 발신자 ID 표시에 표시 되는 **대체 발신자 id** 를 지정 해야 합니다.

10. 하나 이상의 트렁크을 음성 경로와 연결 하려면 **추가** 를 클릭 하 고 목록에서 트렁크를 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 배포에 Microsoft Office Communications Server 2007 R2 중재 서버가 포함 되어 있으면 목록 에서도 해당 서버를 사용할 수 있습니다.

    
    </div>

11. 하나 이상의 PSTN (공중 전화망) 사용을 음성 경로와 연결 하려면 **선택을** 클릭 하 고 Enterprise voice 배포에 대해 정의 된 PSTN 사용 레코드 목록에서 레코드를 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 사용 가능한 각 PSTN 사용 레코드의 속성을 보려면 <A href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013에서 PSTN 사용 레코드 보기</A>를 참조 하세요.<BR>PSTN 사용 레코드를 만들거나 편집 하려면 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">음성 정책 만들기 및 Lync server 2013에서 pstn 사용 레코드 구성</A> 또는 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">lync SERVER 2013에서 pstn 사용 레코드 구성</A>을 참조 하십시오.

    
    </div>

12. 최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다. 목록에서 레코드의 위치를 변경 하려면 레코드 이름을 강조 표시 하 고 위쪽 또는 아래쪽 화살표를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > PSTN 사용 레코드가 나열 되는 순서가 중요 한 음성 정책에서와 달리, PSTN 사용 레코드가 음성 경로에 나열 되는 순서는 유효 하지 않습니다. 그러나 사용 빈도에 따라 목록을 구성 하는 것이 좋습니다. 예: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server는 목록을 위에서 아래로 트래버스 합니다.)

    
    </div>

13. 반드시 **테스트할 번역 된 번호 입력** 필드에 값을 입력 하 고 **이동을**클릭 합니다. 테스트 결과가 필드 아래에 표시 됩니다.
    
    <div>
    

    > [!NOTE]  
    > 아직 테스트를 통과 하지 않은 음성 경로를 저장 한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하십시오.

    
    </div>

14. **확인** 을 클릭 하 여 음성 경로를 저장 합니다.

<div>


> [!IMPORTANT]  
> 음성 경로를 만들 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A>를 참조 하십시오.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 경로 수정](lync-server-2013-modify-a-voice-route.md)  
[Lync Server 2013에서 PSTN 사용 레코드 보기](lync-server-2013-view-pstn-usage-records.md)  
[Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013에서 음성 라우팅 테스트](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

