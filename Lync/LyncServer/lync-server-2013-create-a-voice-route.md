---
title: 'Lync Server 2013: 음성 경로 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe4c6a9492cbbecafff95a1f6e626087e79f62d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a>Lync Server 2013에서 음성 경로 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

다음 절차에서는 Lync Server 2013 제어판을 사용 하 여 새 음성 경로를 만드는 방법에 대해 설명 합니다. 기존 경로를 편집 하려면이 절차에 대 한 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md) 참조 하세요.

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 음성 경로를 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.

4.  **회람**을 클릭 합니다.

5.  **새로 만들기** 를 클릭 하 여 **새 음성 경로** 대화 상자를 표시 합니다.

6.  **Name (이름**)에 음성 경로를 설명 하는 이름을 입력 합니다.

7.  ) **설명**에 음성 경로에 대 한 추가 설명 정보를 입력 합니다.

8.  이 경로에 적용할 패턴을 지정 하려면 **일치 하는 패턴 빌드** 도구를 사용 하 여 정규식을 생성 하거나 수동으로 정규식을 작성 하면 됩니다.
    
      - **일치 하는 패턴 빌드** 도구를 사용 하 여 정규식을 생성 하려면 다음과 같이 값을 입력 합니다. 두 가지 패턴 일치 유형을 지정할 수 있습니다.
        
          - **허용 하려는 숫자의 시작 숫자:** 이 경로에 대해 수용 해야 하는 접두사 값을 입력 합니다 (필요한 경우 선행 + 포함). 예를 들어 **+ 425**을 입력 한 다음 **추가**를 클릭 합니다. 경로에 포함 하려는 각 접두사 값에 대해이를 반복 합니다.
        
          - **예외:** 접두사 값에 하나 이상의 예외를 지정 하려는 경우 접두사를 강조 표시 하 고 **예외**를 클릭 합니다. 이 경로에 적용 *하지* 않으려는 일치 패턴에 대 한 값을 하나 이상 입력 합니다. 예를 들어 경로에서 + 425237으로 시작 하는 숫자를 제외 하려면 **예외** 필드에 **+ 425237** 값을 입력 한 다음 **확인**을 클릭 합니다.
    
      - 일치 패턴을 수동으로 정의 하려면 **일치 하는 패턴 빌드** 도구에서 **편집** 을 클릭 한 다음 .net Framework 정규식을 입력 하 여 경로가 적용 되는 대상 전화 번호에 해당 하는 패턴을 지정 합니다. 정규식을 작성 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)".Net Framework 정규식"을 참조 하세요.

9.  전화의 ID가 통화 수신자에 게 표시 되지 않도록 하려면 **발신자 Id 표시 안 함** 을 선택 합니다. 이 옵션을 선택 하는 경우 받는 사람의 발신자 ID 표시에 표시 되는 **대체 발신자 ID** 를 지정 해야 합니다.

10. 하나 이상의 trunks 음성 경로에 연결 하려면 **추가** 를 클릭 한 다음 목록에서 트렁크를 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 배포에 Microsoft Office Communications Server 2007 R2 중재 서버가 포함 된 경우 목록 에서도 사용할 수 있습니다.

    
    </div>

11. 하나 이상의 PSTN (공개 전환 전화 네트워크)을 음성 경로에 연결 하려면 **선택을** 클릭 하 고 엔터프라이즈 음성 배포에 대해 정의 된 PSTN 사용 레코드 목록에서 레코드를 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 사용할 수 있는 각 PSTN 사용 레코드의 속성을 보려면 <A href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013에서 PSTN 사용 레코드 보기</A>를 참조 하세요.<BR>PSTN 사용 레코드를 만들거나 편집 하려면 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Lync server 2013에서 음성 정책 만들기 및 pstn 사용 레코드 구성</A> 또는 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">lync server 2013에서 음성 정책 수정 및 pstn 사용 레코드 구성을</A>참조 하세요.

    
    </div>

12. 최적의 성능을 위해 PSTN 사용 레코드를 정렬 합니다. 목록에서 레코드의 위치를 변경 하려면 레코드 이름을 강조 표시 하 고 위쪽 또는 아래쪽 화살표를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > PSTN 사용 레코드가 나열 되는 순서와는 대조적으로, PSTN 사용 레코드가 음성 경로에 나열 되는 순서는 중요 하지 않습니다. 그러나 사용 빈도에 따라 목록을 구성 하는 것이 좋습니다. 예: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server는 목록을 위에서 아래로 트래버스 합니다.)

    
    </div>

13. ) **번역 번호 입력** 필드에 값을 입력 하 고 **이동을**클릭 합니다. 필드 아래에 테스트 결과가 표시 됩니다.
    
    <div>
    

    > [!NOTE]  
    > 아직 테스트를 통과 하지 않은 음성 경로를 저장 한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하세요.

    
    </div>

14. **확인** 을 클릭 하 여 음성 경로를 저장 합니다.

<div>


> [!IMPORTANT]  
> 음성 경로를 만들 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시</A>를 참조 하세요.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 경로 수정](lync-server-2013-modify-a-voice-route.md)  
[Lync Server 2013에서 PSTN 사용 레코드 보기](lync-server-2013-view-pstn-usage-records.md)  
[Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013에서 음성 라우팅 테스트](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

