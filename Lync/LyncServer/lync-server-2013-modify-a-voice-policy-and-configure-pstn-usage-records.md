---
title: 'Lync Server 2013: 음성 정책 수정 및 PSTN 사용 레코드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ed1aa2d0d08a0f10c9b8b5a6e46e0401cddc61a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

음성 정책을 수정 하려면 다음 단계를 수행 합니다. 새 음성 정책을 만들려는 경우이 절차를 수행 하려면 [음성 정책 만들기 및 Lync Server 2013에서 PSTN 사용 레코드 구성을](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) 참조 하십시오.

<div>


> [!NOTE]  
> 음성 정책에 할당 된 사용자에 게는 PSTN (공중 전화망) 사용 레코드가 연결 되어 있지 않으면 사용자가 아웃 바운드 호출을 수행할 수 없습니다. Enterprise Voice 배포에서 사용할 수 있는 모든 PSTN 사용 레코드를 나열 하 고 해당 속성을 보려면 <A href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013에서 pstn 사용 레코드 보기</A>를 참조 하세요.



</div>

<div>

## <a name="to-modify-a-voice-policy"></a>음성 정책을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **음성 정책을**클릭 합니다.

4.  **음성 정책** 페이지에서 음성 정책 이름을 두 번 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 음성 정책이 만들어질 때 범위 및 이름이 설정 된 경우 이러한 설정은 변경할 수 없습니다.

    
    </div>

5.  반드시 **음성 정책 편집**에서 음성 정책에 대 한 추가 설명 정보를 입력 합니다.

6.  각 **통화 기능**을 사용 하거나 사용 하지 않도록 설정 하려면 다음 확인란을 선택 하거나 선택을 취소 합니다.
    
      - **음성 메일 이스케이프** 는 동시 벨 울림이 구성 되 고 전화가 꺼져 있거나, 배터리가 부족 하거나, 범위를 벗어날 때 전화가 사용자의 휴대폰 음성 메일 시스템으로 즉시 라우팅되지 않도록 방지 합니다.
        
        <div>
        

        > [!NOTE]  
        > 이 기능은 Lync Server 관리 셸을 통해서만 구성할 수 있습니다.

        
        </div>
    
      - **착신 전환** - 통화를 다른 전화 및 클라이언트 장치로 전달할 수 있습니다. Lync Server 2013에서는 착신 전환에 대 한 보다 광범위 한 구성 옵션을 제공 합니다. 예를 들어 조직에서 들어오는 전화가 PSTN에 외부적으로 전달 되는 것을 허용 하지 않으려는 경우 관리자는 특수 음성 정책을 적용 하 여이 제한을 배포할 수 있습니다. 이 확인란은 기본적으로 선택됩니다.
    
      - **위임** - 자신을 대신해 전화를 걸거나 받을 다른 사용자를 지정할 수 있습니다. Lync Server 2013에서는 대리인이 자신의 관리자에 게 들어오는 호출을 사용 하 여 모든 대리인의 동시 벨 울림 대상에 연결할 수 있도록 하는 동시 울림을 구성 합니다. 이를 통해 대리인이 관리자에 게 전송 되는 호출에 보다 유연성 있게 응답할 수 있습니다. 이 확인란은 기본적으로 선택됩니다.
    
      - **통화 전송** - 통화를 다른 사람에게 전송할 수 있습니다. 이 확인란은 기본적으로 선택됩니다.
    
      - **통화** 대기를 통해 사용자는 통화 보류를 선택 하 고 다른 전화나 클라이언트에서 전화를 받을 수 있습니다. 이 확인란은 기본적으로 선택 취소됩니다.
    
      - **동시 울림** 은 추가 전화기 (예: 휴대폰) 또는 기타 끝점 장치에서 수신 전화를 걸 수 있습니다. Lync Server 2013에서는 동시 울림을 위한 보다 광범위 한 구성 옵션을 제공 합니다. 이 확인란은 기본적으로 선택됩니다.
    
      - **팀 호출** - 정의된 팀의 사용자가 팀의 다른 구성원에 대한 통화에 응답할 수 있습니다. 이 확인란은 기본적으로 선택됩니다.
    
      - **Pstn 재 경로** 설정은 WAN이 혼잡 하거나 사용할 수 없는 경우이 정책이 할당 된 사용자의 통화를 pstn (공중 전화망)에서 다시 라우팅할 수 있도록 합니다. 이 확인란은 기본적으로 선택됩니다.
    
      - **대역폭 정책 재정의** 는 관리자가 특정 사용자에 대 한 CAC (통화 허용 제어) 정책 결정을 재정의할 수 있도록 합니다. 이 확인란은 기본적으로 선택 취소됩니다.
        
        <div>
        

        > [!NOTE]  
        > 정책은 사용자에 대 한 수신 전화에 대해서만 무시 되 고 사용자가 보내는 통화에는 적용 되지 않습니다. 세션이 설정 되 면 대역폭 소비를 정확 하 게 기록 합니다. 이 설정은 가급적 사용하지 않는 것이 좋습니다.

        
        </div>
    
      - **악의적인 통화 추적** 을 통해 사용자는 클라이언트 UI를 사용 하 여이에 대 한 악성 통화 (예: cdrs (통화 정보 기록)의 호출 플래그를 설정 하 여 보고 합니다. 이 확인란은 기본적으로 선택 취소됩니다.

7.  이 음성 정책에 대 한 PSTN 사용 레코드를 연결 및 구성 하려면 다음 중 하나를 수행 합니다.
    
      - Enterprise Voice 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다. 이 음성 정책에 연결할 레코드를 강조 표시 하 고 **확인**을 클릭 합니다.
    
      - 이 음성 정책에서 PSTN 사용 레코드를 제거 하려면 레코드를 강조 표시 하 고 **제거**를 클릭 합니다.
    
      - 새 PSTN 사용 레코드를 정의 하 고이 음성 정책과 연결 하려면 다음을 수행 합니다.
        
        1.  **새로 만들기**를 클릭합니다.
        
        2.  **이름** 필드에 레코드에 대 한 설명이 포함 된 고유 이름을 입력 합니다. 예를 들어 Redmond에 위치한 전일 근무 직원에 대해 **redmond** 라는 PSTN 사용 레코드를 만들고 임시 직원에 게는 **RedmondTemps** 이라는 다른 레코드를 만들 수 있습니다.
            
            <div>
            

            > [!NOTE]  
            > PSTN 사용 레코드 이름은 Enterprise Voice 배포 내에서 고유 해야 합니다. 레코드를 저장한 후에는 <STRONG>이름</STRONG> 필드를 편집할 수 없습니다.

            
            </div>
        
        3.  다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.
            
              - Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.
            
              - PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.
            
              - 새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다. 자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하십시오.
            
              - 이 PSTN 사용 레코드에 이미 연결 되어 있는 경로를 편집 하려면 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다. 자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하십시오.
        
        4.  **확인**을 클릭합니다.
    
      - 이 음성 정책에 이미 연결 된 PSTN 사용 레코드를 편집 하려면 다음을 수행 합니다.
        
        1.  편집할 PSTN 사용 레코드를 강조 표시 하 고 **자세한 정보 표시**를 클릭 합니다.
        
        2.  다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.
            
              - Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.
            
              - 이 PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.
            
              - 새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다. 자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하십시오.
            
              - 이 PSTN 사용 레코드에 이미 연결 되어 있는 경로를 편집 하려면 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다. 자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하십시오.
        
        3.  **확인**을 클릭합니다.

8.  최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다. 목록에서 레코드의 위치를 변경 하려면 레코드 이름을 강조 표시 하 고 위쪽 또는 아래쪽 화살표를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > PSTN 사용 레코드가 음성 정책에 나열 되는 순서는 중요 합니다. Lync Server가 목록을 위에서 아래로 트래버스 합니다. RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup 등의 사용 빈도에 따라 목록을 구성 하는 것이 좋습니다.

    
    </div>

9.  이 음성 정책에서 착신 전환 및 동시 신호 울림에 대 한 PSTN 사용 레코드를 연결 및 구성 하려면 다음 중 하나를 수행 합니다.
    
      - 이 음성 정책으로 착신 전환 및 동시 신호 울림에 동일한 PSTN 사용 레코드를 사용 하려면 드롭다운 메뉴에서 **통화 PSTN 사용을 사용한 옵션 경로** 를 선택 합니다.
    
      - 내부 Lync 사용자에 대해서만 착신 전환 및 동시 신호 울림을 허용 하려면 드롭다운 메뉴에서 **내부 Lync 사용자에 대해서만 경로** 를 선택 합니다. 통화가 외부 PSTN 번호로 전달 되지 않습니다.
    
      - 이 음성 정책에 사용 된 것 보다 착신 전환 및 동시 신호 울림에 대해 서로 다른 PSTN 사용 레코드를 지정 하려면 드롭다운 메뉴에서 **사용자 지정 PSTN 사용을 사용한 옵션 경로** 를 선택 합니다. 이 옵션은 기존 PSTN 사용 레코드를 선택 하거나, 특히 착신 전환 및 동시 신호 울림을 위해 새 PSTN 사용 레코드를 만드는 컨트롤을 표시 합니다.
        
          - 착신 전환 및 동시 신호 울림에 대 한 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다. 이 착신 전환 및 동시 신호 울림 정책과 연결 하려는 레코드를 강조 표시 하 고 **확인**을 클릭 합니다.
        
          - 이 착신 전환 및 동시 신호 울림 정책에서 PSTN 사용 레코드를 제거 하려면 레코드를 강조 표시 하 고 **제거**를 클릭 합니다.
        
          - 새 PSTN 사용 레코드를 정의 하 고이 착신 전환 및 동시 신호 울림 정책과 연결 하려면 다음을 수행 합니다.
            
            1.  **새로 만들기**를 클릭합니다.
            
            2.  **이름** 필드에 레코드에 대 한 설명이 포함 된 고유 이름을 입력 합니다.
                
                <div>
                

                > [!NOTE]  
                > PSTN 사용 레코드 이름은 Enterprise Voice 배포 내에서 고유 해야 합니다. 레코드를 저장한 후에는 <STRONG>이름</STRONG> 필드를 편집할 수 없습니다.

                
                </div>
            
            3.  다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.
                
                  - Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.
                
                  - PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.
                
                  - 새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다. 자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하십시오.
                
                  - 이 PSTN 사용 레코드에 이미 연결 되어 있는 경로를 편집 하려면 경로를 강조 표시 하 고 **자세한 정보 표시**를 클릭 합니다. 자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하십시오.
            
            4.  **확인**을 클릭합니다.
        
          - 이 음성 정책에 이미 연결 된 PSTN 사용 레코드를 편집 하려면 다음을 수행 합니다.
            
            1.  편집할 PSTN 사용 레코드를 강조 표시 하 고 **자세한 정보 표시**를 클릭 합니다.
            
            2.  다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.
                
                  - Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.
                
                  - 이 PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.
                
                  - 새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다. 자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하십시오.
                
                  - 이 PSTN 사용 레코드에 이미 연결 되어 있는 경로를 편집 하려면 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다. 자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하십시오.
            
            3.  **확인**을 클릭합니다.

10. 반드시 전화 번호를 입력 하 여 음성 정책을 테스트 하 고 **이동을**클릭 합니다. 테스트 결과가 변환 된 번호 아래 **에**표시 됩니다.
    
    <div>
    

    > [!NOTE]  
    > 아직 테스트를 통과 하지 않은 음성 정책을 저장 한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하십시오.

    
    </div>

11. **확인**을 클릭합니다.

12. **음성 정책** 페이지에서 **커밋을**클릭 하 고 **모두 커밋을**클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 음성 정책을 만들거나 수정할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.

    
    </div>

13. 반드시 음성 메일 이스케이프는 통화가 사용자의 휴대폰 음성 메일에 의해 즉시 응답 되었음을 감지 하 고 전화를 휴대폰 음성 메일로 연결을 끊습니다. 이를 통해 사용자가 통화에 응답할 수 있도록 하는 사용자의 다른 끝점에 대 한 통화가 계속 해 서 켜 집니다. 음성 메일 정책을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 음성 메일 이스케이프 구성을](lync-server-2013-configuring-voice-mail-escape.md)참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013에서 PSTN 사용 레코드 보기](lync-server-2013-view-pstn-usage-records.md)  
[Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)  
[Lync Server 2013에서 음성 경로 수정](lync-server-2013-modify-a-voice-route.md)  
[Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Lync Server 2013에서 음성 메일 이스케이프 구성](lync-server-2013-configuring-voice-mail-escape.md)  


[Lync Server 2013에서 음성 라우팅 테스트](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

