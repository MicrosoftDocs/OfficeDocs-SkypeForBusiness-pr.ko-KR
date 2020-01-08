---
title: 'Lync Server 2013: 헌트 그룹 워크플로 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c927b10107626c1d40c33290b30f331f660e45e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a>Lync Server 2013에서 헌트 그룹 워크플로 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-09-11_

다음 절차 중 하나를 사용 하 여 헌트 그룹 워크플로를 만들거나 수정 합니다.

<div>


> [!NOTE]  
> Lync Server 관리 셸 또는 응답 그룹 구성 도구를 사용 하 여 헌트 그룹 워크플로를 만들고 수정할 수 있습니다. Lync Server 제어판에서 응답 그룹 구성 도구에 액세스 하거나 다음 URL을 입력 하 여 웹 브라우저에서 직접 웹 페이지를 열 수 있습니다. <STRONG>https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>응답 그룹 구성 도구를 사용 하 여 헌트 그룹 워크플로를 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **응답 그룹**을 클릭 한 다음 **워크플로**를 클릭 합니다.

4.  **워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭 합니다.

5.  서비스 검색 **선택** 필드에 만들거나 변경할 워크플로를 호스트 하는 **applicationserver** 서비스 이름의 전부 또는 일부를 입력 합니다. 서비스 결과 목록에서 원하는 서비스를 클릭 한 다음 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 응답 그룹 구성 도구가 열립니다. 다음 URL을 입력 하 여 웹 브라우저에서 직접 응답 그룹 구성 도구를 열 수도 있습니다. <STRONG>https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>.

    
    </div>

6.  다음 중 하나를 수행 합니다.
    
      - **새 워크플로 만들기**에서 **헌트 그룹**옆에 있는 만들기를 클릭 합니다.
    
      - **기존 워크플로 관리**에서 변경 하려는 워크플로를 찾은 다음, **실행**에서 **편집**을 클릭 합니다.

7.  사용자가 워크플로 호출을 시작할 준비가 되었으면 **워크플로 활성화**를 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 관리 되는 워크플로를 만들려면 <STRONG>워크플로 활성화</STRONG>를 선택 해야 합니다. 관리 되는 활성 워크플로를 저장 한 후에는 수정 하 고 비활성화할 수 있습니다.

    
    </div>

8.  페더레이션 사용자가 그룹에 전화를 걸 수 있도록 허용 하려면 **페더레이션 사용** 확인란을 선택 합니다. 또한 페더레이션에 대해 구성 된 응답 그룹 응용 프로그램에 적용 되는 외부 액세스 정책만 있어야 합니다.
    
    <div>
    

    > [!NOTE]  
    > 글로벌 외부 액세스 정책이 응답 그룹 응용 프로그램에 적용 됩니다. Lync Server 제어판을 사용 하거나 <STRONG>set-CsExternalAccessPolicy</STRONG> cmdlet을 사용 하 여 Enableout 액세스 매개 변수를 True로 설정 하 여 응답 그룹 페더레이션에 대 한 전역 정책을 구성할 수 있습니다. 전역 정책 설정은 사이트 또는 사용자 정책을 할당 하지 않는 한 모든 사용자에 게 적용 된다는 점에 유의 하세요. 따라서 응답 그룹에 대해이 설정을 변경 하기 전에 페더레이션 설정이 조직의 요구 사항에 맞는지 확인 해야 합니다. 정책이 사용자에 게 적용 되는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013에서 외부 액세스 정책 관리</A>를 참조 하세요. 페더레이션 설정에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>를 참조 하세요.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Lync Online에서 호스팅되는 사용자는 온-프레미스 배포에 호스팅된 응답 그룹에 대 한 통화를 할 수 없습니다. 이는 온-프레미스 배포와 Lync Online 배포에 연결 된 경우에 모두 마찬가지입니다.

    
    </div>

9.  통화 중 에이전트의 id를 숨기려면 **에이전트 익명 사용** 확인란을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 관리자나 발신자는 전화를 설정한 후에 IM 및 비디오를 추가할 수 있지만, 익명 호출은 메신저 또는 비디오로 시작할 수 없습니다. 익명 에이전트는 통화 대기, 통화 전환 (블라인드 및 consultative 전송 모두)을 할 수 있으며 통화를 전환 하 고 검색할 수도 있습니다. 익명 통화는 회의, 응용 프로그램 공유 및 데스크톱 공유, 파일 전송, whiteboarding, 데이터 공동 작업, 통화 기록을 지원 하지 않습니다. Lync VDI 플러그 인을 사용 하는 상담원은 들어오는 호출을 익명으로 받을 수 있지만, 나가는 호출을 익명으로 할 수는 없습니다.

    
    </div>

10. 에서 **전화를 받을 그룹의 주소 입력**에 워크플로 호출에 응답할 그룹의 기본 SIP uri (uniform resource identifier) 주소를 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 워크플로의 기본 URI는 워크플로를 식별 하 고 참조 하는 방법입니다. 입력 하는 SIP URI는 Active Directory 도메인 서비스의 contact 개체로 만들어집니다. URI를 만들려면 개체가 Active Directory에서 고유 해야 합니다.

    
    </div>

11. **표시 이름**에 워크플로에 대해 표시할 이름 (예: 영업 응답 그룹)을 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 표시 이름에 "&lt;" 또는 "&gt;" 문자를 포함 하지 마세요. 다음 표시 이름은 예약 됨: <STRONG>RGS 현재 감시자</STRONG> 또는 <STRONG>알림 서비스</STRONG>이므로 사용 하지 마세요.

    
    </div>

12. **전화 번호**에서 응답 그룹의 줄 URI를 입력 합니다 (예: + 14255550165).

13. **표시 번호**에서 응답 그룹에 대해 표시할 숫자를 입력 합니다 (예: + 1 (425) 555-0165).

14. ) **설명**에 Lync 클라이언트의 대화 상대 카드에 표시할 워크플로 설명을 입력 합니다.

15. **워크플로 유형에**서이 워크플로를 응답 그룹 관리자가 관리 하는 경우 **관리** 를 선택 합니다. 응답 그룹 관리자를 워크플로에 할당 하려면 다음을 실행 합니다.
    
    1.  이 워크플로에 대 한 관리자의 SIP URI를 입력 하 고 **추가**를 클릭 합니다.
    
    2.  추가 관리자의 SIP URI를 입력 하 여 워크플로에 추가 하 고 **추가**를 클릭 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 응답 그룹의 관리자로 지정 된 모든 사용자에 게 CsResponseGroupManager 역할을 할당 해야 합니다. 사용자에 게이 역할이 할당 되지 않은 경우 응답 그룹을 관리할 수 없습니다.

    
    </div>

16. **2 단계에서 언어를 선택**하 고 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭 합니다.

17. 환영 메시지를 구성 하려면 **3 단계에서 환영 메시지 구성**확인란을 선택 하 고 다음 중 하나를 **수행 합니다.**
    
      - 환영 메시지를 발신자를 위해 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 환영 메시지를 입력 합니다.
        
        <div>
        

        > [!NOTE]  
        > 입력 한 텍스트에 HTML 태그를 포함 하지 않습니다. HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.

        
        </div>
    
      - 환영 메시지에 웨이브 (.wav) 또는 Windows Media 오디오 (.wma) 파일 기록을 사용 하려면 **기록 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용 하려는 오디오 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

18. **4 단계에서 업무 시간을 지정**하 고 **표준 시간대**에서 워크플로의 표준 시간대를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 표준 시간대는 워크플로의 호출자와 에이전트가 상주 하는 표준 시간대입니다. 이 메서드는 시작 시간과 종료 시간을 계산 하는 데 사용 됩니다. 예를 들어 워크플로가 북미 동부 표준 시간대를 사용 하도록 구성 되 고 워크플로가 오전 7:00 시에 열리도록 예약 된 경우 11:00 P.M.에서 시작 하 여 닫은 시간은 각각 7:00 동부 표준시와 23:00 동부 시간으로 간주 됩니다. (24 시간 표시법으로 시간을 입력 해야 합니다.)

    
    </div>

19. 다음 중 하나를 실행 하 여 사용 하려는 업무 시간 일정의 유형을 선택 합니다.
    
      - 미리 정의 된 업무 시간 일정을 사용 하려면 **미리 설정 된 일정 사용**을 클릭 한 다음 드롭다운 목록에서 사용할 일정을 선택 합니다.
        
        <div>
        

        > [!NOTE]  
        > 이 옵션을 선택할 수 있으려면 이전에 미리 설정 된 일정이 하나 이상 정의 되어 있어야 합니다. <STRONG>새 CSRgsHoursOfBusiness</STRONG> cmdlet을 사용 하 여 미리 설정 된 일정을 정의 합니다. 자세한 내용은 <A href="lync-server-2013-optional-define-response-group-business-hours.md">(선택 사항) Lync Server 2013에서 응답 그룹 비즈니스 시간 정의</A>를 참조 하세요.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > 미리 설정 된 일정을 선택 하면 <STRONG>일</STRONG>, <STRONG>열기</STRONG>및 <STRONG>닫기</STRONG> 가 자동으로 응답 그룹을 사용할 수 있는 날짜와 시간으로 채워집니다.

        
        </div>
    
      - 이 워크플로에만 적용 되는 사용자 지정 일정을 사용 하려면 **사용자 지정 일정 사용**을 클릭 합니다.

20. 이 워크플로에 대 한 사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있는 요일의 확인란을 클릭 합니다.

21. 사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있는 각 요일에 대해 **열기** 및 **닫기** 시간을 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>열기</STRONG> 시간과 <STRONG>종료</STRONG> 시간은 24 시간 표기 형식 이어야 합니다. 예를 들어, office가 9 ~ 5 개의 작업일로 근무 하 고 점심 시간에 종료 되는 경우 업무 시간은 <STRONG>열린</STRONG> 9:00, <STRONG>종료</STRONG> 12:00, <STRONG>열기</STRONG> 13:00 및 <STRONG>닫기</STRONG> 17:00로 지정 됩니다.

    
    </div>

22. Office가 열려 있지 않은 경우 메시지를 재생 하려면 **응답 그룹이 업무 시간을 초과 하면 메시지 재생** 확인란을 선택 하 고 다음 중 하나를 실행 하 여 재생할 메시지를 지정 합니다.
    
      - 메시지를 호출자의 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 메시지를 입력 합니다.
        
        <div>
        

        > [!NOTE]  
        > 입력 한 텍스트에 HTML 태그를 포함 하지 않습니다. HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.

        
        </div>
    
      - 메시지에 오디오 파일 녹음/녹화를 사용 하려면 **기록 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

23. 메시지가 재생 된 후 호출을 처리 하는 방법 지정 (메시지가 구성 된 경우):
    
      - 통화 연결을 끊으려면 **통화 연결 끊기를**클릭 합니다.
    
      - 전화를 음성 메일로 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 음성 메일 주소를 입력 합니다. 음성 메일 주소의 형식은 사용자 \<이름\>@\<domainName\> (예: bob@contoso.com)입니다.
    
      - 다른 사용자에 게 통화를 착신 전환 하려면 **SIP URI로 전달을**클릭 한 다음 사용자 주소를 입력 합니다. 사용자 주소의 형식은 \<username\>@\<domainName\>입니다.
    
      - 통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 전화 번호를 입력 합니다. 전화 \<번호의 형식은 번호\>@\<의 이름\> (예: + 14255550121@contoso.com)입니다. 도메인 이름은 호출자를 올바른 대상으로 라우팅하는 데 사용 됩니다.

24. **5 단계에서 공휴일을 지정**하 고 응답 그룹을 비즈니스용으로 닫은 날을 정의 하는 하나 이상의 공휴일 집합에 해당 하는 확인란을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 워크플로를 구성 하기 전에 휴일 및 휴일 집합을 정의 해야 합니다. <STRONG>CsRgsHoliday</STRONG> 및 <STRONG>new-CsRgsHolidaySet</STRONG> cmdlet을 사용 하 여 휴일 및 휴일 집합을 정의 합니다. 자세한 내용은 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(선택 사항) Lync Server 2013에서 응답 그룹 휴일 집합 정의</A>를 참조 하세요.

    
    </div>

25. 휴일에서 메시지를 재생 하려면 **공휴일 중 메시지 재생** 확인란을 선택한 후 다음 중 하나를 실행 하 여 재생할 메시지를 지정 합니다.
    
      - 메시지를 호출자의 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 메시지를 입력 합니다.
        
        <div>
        

        > [!NOTE]  
        > 입력 한 텍스트에 HTML 태그를 포함 하지 않습니다. HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.

        
        </div>
    
      - 메시지에 오디오 파일 녹음/녹화를 사용 하려면 **기록 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

26. 메시지가 재생 된 후 호출을 처리 하는 방법 지정 (메시지가 구성 된 경우):
    
      - 통화 연결을 끊으려면 **통화 연결 끊기를**클릭 합니다.
    
      - 전화를 음성 메일로 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 음성 메일 주소를 입력 합니다. 음성 메일 주소의 형식은 사용자 \<이름\>@\<domainName\> (예: bob@contoso.com)입니다.
    
      - 다른 사용자에 게 통화를 착신 전환 하려면 **SIP URI로 전달을**클릭 한 다음 사용자 주소를 입력 합니다. 사용자 주소의 형식은 \<username\>@\<domainName\>입니다.
    
      - 통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 전화 번호를 입력 합니다. 전화 \<번호의 형식은 번호\>@\<의 이름\> (예: + 14255550121@contoso.com)입니다. 도메인 이름은 호출자를 올바른 대상으로 라우팅하는 데 사용 됩니다.

27. **6 단계에서 큐 구성**에서 전화를 **받을 큐를 선택**하 고 에이전트를 사용할 수 있게 될 때까지 호출자를 보관할 큐를 선택 합니다.

28. **7 단계에서 음악을 보류할**때 다음 중 하나를 수행 하 여 에이전트를 기다리는 동안 호출자가 수신할 음악을 선택 합니다.
    
      - 기본 음악 보관 기록을 사용 하려면 **기본값 사용**을 클릭 합니다.
    
      - 대기 중인 음악에 오디오 파일 녹음/녹화를 사용 하려면 **음악 파일 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **음악 파일** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자가 제공 하는 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

29. **배포**를 클릭 합니다.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a>Windows PowerShell을 사용 하 여 헌트 그룹 워크플로를 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  환영 메시지에 대해 재생할 프롬프트를 만들고 변수에 저장 합니다. 명령줄에서 다음을 실행 합니다.
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    예를 들면 다음과 같습니다.
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > 프롬프트에 오디오 파일을 사용 하려면 <STRONG>CsRgsAudioFile</STRONG> cmdlet을 사용 합니다. 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">가져오기-CsRgsAudioFile</A>을 참조 하세요.

    
    </div>

4.  호출이 리디렉션되는 큐 또는 질문의 id를 가져옵니다. 명령줄에서 다음을 실행 합니다.
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    큐 만들기에 대 한 자세한 내용은 [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)를 참조 하세요.

5.  업무 시간 동안 워크플로가 열려 있을 때 수행할 기본 작업을 정의 하 고 변수에 저장 합니다. 명령줄에서 다음을 실행 합니다.
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > 헌트 그룹 워크플로의 경우 기본 동작은 큐로 호출을 보내야 합니다. 이 매개 변수는 활성 워크플로에 필요 합니다. 비활성 워크플로에는 필요 하지 않습니다.

    
    </div>
    
    예를 들면 다음과 같습니다.
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  비즈니스 시간 및 휴일을 정의 하려는 경우 워크플로를 만들거나 수정 하기 전에 만들어야 합니다. 자세한 내용은 [(선택 사항) Lync server 2013에서 응답 그룹 비즈니스 시간 정의](lync-server-2013-optional-define-response-group-business-hours.md) 및 [(선택 사항) lync Server 2013의 응답 그룹 휴일 집합을 정의](lync-server-2013-optional-define-response-group-holiday-sets.md)하세요.

7.  업무 시간 또는 휴일을 통해 받은 통화에 대 한 메시지를 표시 하려면 **CsRgsPrompt** cmdlet을 사용 하 여 프롬프트를 정의 하 고 **new-CsRgsCallAction** 를 사용 하 여 프롬프트 후 수행할 작업을 정의 합니다. 자세한 내용은 [new-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) 및 [new-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)를 참조 하세요.

8.  Lync Server 응답 그룹 서비스의 서비스 이름을 검색 하 여 변수에 할당 합니다. 명령에서 다음을 실행 합니다.
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  워크플로를 만들거나 수정 합니다. 워크플로를 만들려면 **New-CsRgsWorkflow**을 사용 합니다. 워크플로를 수정 하려면 **Set-CsRgsWorkflow**를 사용 합니다. 명령줄에 다음을 입력 합니다.
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    예를 들면 다음과 같습니다.
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > 워크플로에 대해 지정 된 모든 사용자에 게 CsResponseGroupManager 역할을 할당 해야 합니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 추가 선택적 매개 변수에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> 또는 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A> 을 참조 하세요.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[) Lync Server 2013에서 응답 그룹의 휴일 집합 정의](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[) Lync Server 2013에서 응답 그룹 비즈니스 시간 정의](lync-server-2013-optional-define-response-group-business-hours.md)  


[새로운 CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[새로운 CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[새로운 CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

