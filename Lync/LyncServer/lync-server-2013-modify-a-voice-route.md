---
title: 'Lync Server 2013: 음성 경로 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47a138fd0ffa1556ea4f6f80c53f7357137a7661
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a>Lync Server 2013에서 음성 경로 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

이 항목에서는 음성 경로를 편집 하는 방법에 대해 설명 합니다. 새 경로를 만들려면 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하세요.

<div>

## <a name="to-modify-a-voice-route"></a>음성 경로를 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **경로**를 클릭 합니다.

4.  **경로** 페이지에서 다음 방법 중 하나를 사용 하 여 음성 경로를 수정 합니다.
    
      - 음성 경로 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
      - 음성 경로 이름을 클릭 하 고 **편집**을 클릭 한 다음 **복사**를 클릭 하 고 **붙여넣기**를 클릭 합니다. 방금 만든 음성 경로의 새 복사본을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **음성 경로 편집** 페이지의 **이름** 필드에 음성 경로를 설명 하는 이름을 입력 합니다.

6.  ) **설명** 필드에 음성 경로에 대 한 추가 설명 정보를 입력 합니다.

7.  이 경로에 적용할 패턴을 지정 하려면 **일치 하는 패턴 빌드** 도구를 사용 하 여 정규식을 생성 하거나 수동으로 정규식을 작성 하면 됩니다.
    
      - **일치 하는 패턴 빌드** 도구를 사용 하 여 정규식을 생성 하려면 다음과 같이 값을 입력 합니다. 두 가지 패턴 일치 유형을 지정할 수 있습니다.
        
          - **허용 하려는 숫자의 시작 숫자:** 이 경로에 대해 수용 해야 하는 접두사 값을 입력 합니다 (필요한 경우 선행 + 포함). 예를 들어 **+ 425** 을 입력 한 다음 **추가**를 클릭 합니다. 경로에 포함 하려는 각 접두사 값에 대해이를 반복 합니다.
        
          - **예외:** 접두사 값에 하나 이상의 예외를 지정 하려는 경우 접두사를 강조 표시 하 고 **예외**를 클릭 합니다. 이 경로에 적용 *하지* 않으려는 일치 패턴에 대 한 값을 하나 이상 입력 합니다. 예를 들어 경로에서 + 425237으로 시작 하는 숫자를 제외 하려면 **예외** 필드에 **+ 425237** 값을 입력 한 다음 **확인**을 클릭 합니다.
    
      - 일치 패턴을 수동으로 정의 하려면 **일치 하는 패턴 빌드** 도구에서 **편집** 을 클릭 한 다음 .net Framework 정규식을 입력 하 여 경로가 적용 되는 대상 전화 번호에 해당 하는 패턴을 지정 합니다. 정규식을 작성 하는 방법에 대 한 자세한 내용은의 ".NET Framework 정규식" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)을 참조 하세요.

8.  발신 전화를 거는 전화 ID를 통화 수신자에 게 표시 하지 않으려면 **발신자 Id 표시 안** 함을 선택 합니다. 이 옵션을 선택 하는 경우 받는 사람의 발신자 ID 표시에 표시 되는 **대체 발신자 ID** 를 지정 해야 합니다.

9.  하나 이상의 PSTN (공개 교환 전화 네트워크) trunks를 음성 경로에 연결 하려면 **추가**를 클릭 한 다음 목록에서 트렁크를 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 배포에 Microsoft Office Communications Server 2007 R2 중재 서버가 포함 된 경우 목록 에서도 사용할 수 있습니다.

    
    </div>

10. 하나 이상의 PSTN 용도를 음성 경로에 연결 하려면 **선택을** 클릭 하 고 엔터프라이즈 음성 배포에 대해 정의 된 PSTN 사용 레코드 목록에서 레코드를 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 사용할 수 있는 각 PSTN 사용 레코드의 속성을 보려면 <A href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013에서 PSTN 사용 레코드 보기</A>를 참조 하세요.<BR>PSTN 사용 레코드를 만들거나 편집 하려면 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Lync server 2013에서 음성 정책 만들기 및 pstn 사용 레코드 구성</A> 또는 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">lync server 2013에서 음성 정책 수정 및 pstn 사용 레코드 구성을</A>참조 하세요.

    
    </div>

11. 최적의 성능을 위해 PSTN 사용 레코드를 정렬 합니다. 목록에서 레코드의 위치를 변경 하려면 레코드 이름을 강조 표시 하 고 위쪽 또는 아래쪽 화살표를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > PSTN 사용 레코드가 나열 되는 순서와는 달리, 음성 경로에 있는 PSTN 사용 레코드의 순서는 중요 하지 않습니다. 그러나 RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup 등의 사용 빈도 별로 목록을 구성 하는 것이 좋습니다. (Lync Server는 목록을 위에서 아래로 트래버스 합니다.)

    
    </div>

12. ) **번역 번호 입력** 필드에 값을 입력 하 고 **이동을**클릭 합니다. 필드 아래에 테스트 결과가 표시 됩니다.
    
    <div>
    

    > [!NOTE]  
    > 아직 테스트를 통과 하지 않은 음성 경로를 저장 한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하세요.

    
    </div>

13. **확인**을 클릭합니다.

14. **라우팅** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 음성 경로를 만들거나 수정할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)  
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

