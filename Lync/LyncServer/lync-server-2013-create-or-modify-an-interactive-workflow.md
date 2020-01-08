---
title: 'Lync Server 2013: 대화형 워크플로 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ede826df74d63270afe2ea3f4e992cdcddbbe412
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a>Lync Server 2013에서 대화형 워크플로 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-09-11_

다음 절차 중 하나를 사용 하 여 대화형 워크플로를 만들거나 수정 합니다.

<div>


> [!NOTE]  
> Lync Server 관리 셸 또는 응답 그룹 구성 도구를 사용 하 여 대화형 워크플로를 만들고 수정할 수 있습니다. Lync Server 제어판에서 응답 그룹 구성 도구에 액세스 하거나 다음 URL을 입력 하 여 웹 브라우저에서 직접 웹 페이지를 열 수 있습니다. <STRONG>https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>응답 그룹 구성 도구를 사용 하 여 대화형 워크플로를 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **응답 그룹**을 클릭 한 다음 **워크플로**를 클릭 합니다.

4.  **워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭 합니다.

5.  서비스 검색 **선택** 필드에 만들거나 수정할 워크플로를 호스트 하는 **applicationserver** 서비스 이름의 전부 또는 일부를 입력 합니다. 서비스 결과 목록에서 원하는 서비스를 클릭 한 다음 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 응답 그룹 구성 도구가 열립니다. 다음 URL을 입력 하 여 웹 브라우저에서 직접 응답 그룹 구성 도구를 열 수도 있습니다. <STRONG>https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>.

    
    </div>

6.  다음 중 하나를 수행 합니다.
    
      - **새 워크플로 만들기**에서 **대화형**옆에 있는 **만들기**를 클릭 합니다.
    
      - **기존 워크플로 관리**에서 변경 하려는 워크플로를 찾은 다음, **실행**에서 **편집**을 클릭 합니다.

7.  사용자가 워크플로 호출을 시작할 준비가 되지 않은 경우 **워크플로 활성화** 확인란의 선택을 취소 합니다.
    
    <div>
    

    > [!NOTE]  
    > 관리 되는 워크플로를 만들려면 <STRONG>워크플로 활성화</STRONG>를 선택 해야 합니다. 관리 되는 활성 워크플로를 저장 한 후에는 수정 하 고 비활성화할 수 있습니다.

    
    </div>

8.  페더레이션 사용자가 그룹에 전화를 걸 수 있도록 허용 하려면 **페더레이션 사용** 확인란을 선택 합니다. 또한 페더레이션에 대해 구성 된 응답 그룹 응용 프로그램에 적용 되는 외부 액세스 정책만 있어야 합니다.
    
    <div>
    

    > [!NOTE]  
    > 글로벌 외부 액세스 정책이 응답 그룹 응용 프로그램에 적용 됩니다. Lync Server 제어판을 사용 하거나 <STRONG>set-CsExternalAccessPolicy</STRONG> cmdlet을 사용 하 여 Enableout 액세스 매개 변수를 True로 설정 하 여 응답 그룹 페더레이션에 대 한 전역 정책을 구성할 수 있습니다. 전역 정책 설정은 사이트 또는 사용자 정책을 할당 하지 않는 한 모든 사용자에 게 적용 된다는 점에 유의 하세요. 따라서 응답 그룹에 대해이 설정을 변경 하기 전에 페더레이션 설정이 조직의 요구 사항에 맞는지 확인 해야 합니다. 정책이 사용자에 게 적용 되는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013에서 외부 액세스 정책 관리</A>를 참조 하세요. 페더레이션 설정에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 <STRONG>CsExternalAccessPolicy</STRONG> 를 참조 하세요.

    
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

11. **표시 이름**에 워크플로에 대해 표시할 이름 (예: 영업권 IVR 응답 그룹)을 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 표시 이름에 "&lt;" 또는 "&gt;" 문자를 포함 하지 마세요. 다음 표시 이름은 예약 됨: RGS 현재 감시자 또는 알림 서비스 이므로 사용 하지 마세요.

    
    </div>

12. **전화 번호**에서 응답 그룹에 대 한 줄 URI를 입력 합니다 (예: + 14255550165).

13. **표시 번호**에서 응답 그룹에 대해 표시할 숫자를 입력 합니다 (예: + 1 (425) 555-0165).

14. ) **설명**에 Lync 클라이언트의 대화 상대 카드에 표시할 워크플로에 대 한 설명을 입력 합니다.

15. **워크플로 유형에**서이 워크플로를 응답 그룹 관리자가 관리 하는 경우 **관리** 를 선택 합니다. 응답 그룹 관리자를 워크플로에 할당 하려면 다음을 실행 합니다.
    
    1.  이 워크플로에 대 한 관리자의 SIP URI를 입력 하 고 **추가**를 클릭 합니다.
    
    2.  워크플로에 추가할 추가 관리자의 SIP URI를 입력 하 고 **추가**를 클릭 합니다.
    
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
    
      - 환영 메시지에 웨이브 또는 Windows Media 오디오 파일 기록을 사용 하려면 **기록 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용 하려는 오디오 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

18. **4 단계에서 업무 시간을 지정**하 고 **표준 시간대** 상자에서 워크플로의 표준 시간대를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 표준 시간대는 워크플로의 호출자와 에이전트가 상주 하는 표준 시간대입니다. 이 메서드는 시작 시간과 종료 시간을 계산 하는 데 사용 됩니다. 예를 들어 워크플로가 북미 동부 표준 시간대를 사용 하도록 구성 되 고 워크플로가 오전 7:00 시에 열리도록 예약 된 경우 11:00 P.M.에서 시작 하 여 닫은 시간은 각각 7:00 동부 표준시와 11:00 동부 시간으로 간주 됩니다. (24 시간 표시법으로 시간을 입력 해야 합니다.)

    
    </div>

19. 다음 중 하나를 실행 하 여 사용 하려는 업무 시간 일정의 유형을 선택 합니다.
    
      - 미리 정의 된 업무 시간 일정을 사용 하려면 **미리 설정 된 일정 사용**을 클릭 한 다음 드롭다운 목록에서 사용할 일정을 선택 합니다.
        
        <div>
        

        > [!NOTE]  
        > 이 옵션을 선택할 수 있으려면 이전에 미리 설정 된 일정이 하나 이상 정의 되어 있어야 합니다. <STRONG>새 CSRgsHoursOfBusiness</STRONG> cmdlet을 사용 하 여 미리 설정 된 일정을 정의 합니다. 자세한 내용은 <A href="lync-server-2013-optional-define-response-group-business-hours.md">(선택 사항) Lync Server 2013에서 응답 그룹 비즈니스 시간 정의</A>를 참조 하세요. 미리 설정 된 일정을 선택 하면 <STRONG>일</STRONG>, <STRONG>열기</STRONG>및 <STRONG>닫기</STRONG> 가 자동으로 응답 그룹을 사용할 수 있는 날짜와 시간으로 채워집니다.

        
        </div>
    
      - 이 워크플로에만 적용 되는 사용자 지정 일정을 사용 하려면 **사용자 지정 일정 사용**을 클릭 합니다.

20. 이 워크플로에 대 한 사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있는 요일의 확인란을 클릭 합니다.

21. 사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있게 되 면 **열기** 및 **닫기** 시간을 입력 합니다.
    
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
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

23. 메시지가 재생 된 후 호출을 처리 하는 방법 지정 (메시지가 구성 된 경우):
    
      - 통화 연결을 끊으려면 **통화 연결 끊기를**클릭 합니다.
    
      - 전화를 음성 메일로 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 음성 메일 주소를 입력 합니다. 음성 메일 주소의 형식은 사용자 \<이름\>@\<domainname\> (예: bob@contoso.com)입니다.
    
      - 다른 사용자에 게 통화를 착신 전환 하려면 **SIP URI로 전달을**클릭 한 다음 사용자 주소를 입력 합니다. 사용자 주소의 형식은 \<username\>@\<domainname\>입니다.
    
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
    
      - 전화를 음성 메일로 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 음성 메일 주소를 입력 합니다. 음성 메일 주소의 형식은 사용자 \<이름\>@\<domainname\> (예: bob@contoso.com)입니다.
    
      - 다른 사용자에 게 통화를 착신 전환 하려면 **SIP URI로 전달을**클릭 한 다음 사용자 주소를 입력 합니다. 사용자 주소의 형식은 \<username\>@\<domainname\>입니다.
    
      - 통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 전화 번호를 입력 합니다. 전화 \<번호의 형식은 번호\>@\<의 이름\> (예: + 14255550121@contoso.com)입니다. 도메인 이름은 호출자를 올바른 대상으로 라우팅하는 데 사용 됩니다.

27. **6 단계에서 음악 구성**에서 다음 중 하나를 수행 하 여 에이전트를 기다리는 동안 호출자가 수신할 작업을 선택 합니다.
    
      - 기본 음악 보관 기록 기능을 사용 하려면 **기본값 사용**을 클릭 합니다.
    
      - 대기 중인 음악에 오디오 파일 녹음/녹화를 사용 하려면 **음악 파일 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **음악 파일** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

28. **7 단계 대화형 음성 응답 구성**아래에 있는 **사용자는 다음 텍스트 또는 녹음 된 메시지 제목을 들** 을 수 있습니다. 라는 질문을 지정 하 여 다음과 같이 발신자를 요청 합니다.
    
      - 질문을 텍스트 형식으로 입력 하려면 **텍스트 읽어주기 사용**을 클릭 하 고 텍스트 상자에 질문을 입력 합니다.
        
        <div>
        

        > [!NOTE]  
        > 입력 한 텍스트에 HTML 태그를 포함 하지 않습니다. HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > "#" 기호는 텍스트 음성 변환 엔진에 의해 "number" 라는 단어로 번역 됩니다. # Key를 참조 해야 하는 경우에는 프롬프트에 기호 대신 키 이름을 사용 해야 합니다. 예를 들어 "영업부와 대화 하려면 우물 정자" 키를 누릅니다.

        
        </div>
    
      - 질문을 포함 하는 미리 녹음 된 오디오 파일을 사용 하려면 **기록 선택**을 클릭 한 다음 **기록** 링크를 클릭 하 여 파일을 업로드 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 오디오 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 파일을 로드 한 다음 선택적으로 텍스트 상자에 질문을 입력할 수 있습니다 (질문 및 호출자의 응답을 응답 하는 에이전트로 착신 전환 가능).
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

29. **응답 1**아래에서 다음을 수행 하 여 질문에 대 한 첫 번째 응답을 지정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 음성 응답에 따옴표 (")를 사용 하지 마세요. 큰따옴표는 IVR을 실패 시킵니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 전화 건 사람이 음성, 영숫자 키패드 입력 또는 둘 다를 사용 하 여 응답 하도록 선택할 수 있습니다.

    
    </div>
    
      - 발신자가 음성을 사용 하 여 응답할 수 있도록 허용 하려면 **음성 응답 입력**에 대답을 입력 합니다.
    
      - 키패드에서 키를 눌러 발신자가 응답할 수 있도록 허용 하려면 키패드 **숫자를 클릭**합니다.

30. 호출자를 큐로 보낼지 아니면 다음과 같이 다른 질문을 요청할지 여부를 지정 합니다.
    
      - 호출자를 큐로 라우팅하려면 큐 **에 보내기를**클릭 하 고 **큐에 선택**에서 사용할 큐를 클릭 합니다.
    
      - 다른 질문을 요청 하려면 **다른 질문**하기를 클릭 한 다음 **텍스트 읽어주기 사용** 을 클릭 하 여 질문을 입력 하거나 **기록 선택을**클릭 합니다. 이 섹션의 응답 그룹을 사용 하 여 추가 질문 및 각 응답에 대해 사용할 큐에 대해 최대 4 개의 응답을 지정할 수 있습니다. 세 번째 또는 네 번째 가능 응답을 지정 하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭 합니다.

31. 28 ~ 29 단계를 반복 하 여 가능 응답과 각 응답에 대해 수행할 작업을 지정 하 여 원래 질문에 대 한 답변을 최대 3 개까지 지정할 수 있습니다. 세 번째 또는 네 번째로 발생할 수 있는 답변을 지정 하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭 합니다.

32. **배포**를 클릭 합니다.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a>Windows PowerShell을 사용 하 여 대화형 워크플로를 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  응답 그룹 서비스의 서비스 이름을 검색 하 고 변수에 할당 합니다. 명령줄에서 다음을 실행 합니다.
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  대화형 워크플로에는 두 개 이상의 큐와 두 개 이상의 에이전트 그룹이 필요 합니다. 먼저 에이전트 그룹을 만듭니다. 런
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  큐를 만듭니다. 런
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  첫 번째 응답 그룹 메시지를 만듭니다. 런
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  그런 다음 프롬프트 후에 수행할 작업을 만듭니다. 런
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  첫 번째 응답 그룹 응답을 만듭니다. 런
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  이제 두 번째 프롬프트를 만들고, 착신 동작을 수행 하 고, 응답 합니다. 먼저 프롬프트를 만듭니다. 런
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. 두 번째 호출 작업을 만듭니다. 런
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. 두 번째 응답 그룹 응답을 만듭니다. 런
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. 최상위 수준의 프롬프트를 만듭니다. 런
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. 최상위 수준의 질문을 만듭니다. 런
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. 이제 워크플로를 만듭니다. 런
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > 응답 그룹 관리자로 지정 된 모든 사용자에 게는 CsResponseGroupManager 역할을 할당 해야 합니다. 사용자에 게이 역할이 할당 되지 않은 경우 응답 그룹을 관리할 수 없습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

