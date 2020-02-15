---
title: 'Lync Server 2013: 대화형 워크플로 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93df8640593769b7b90d8b4e157133f8f7df2f19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41994083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a>Lync Server 2013에서 대화형 워크플로 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-09-11_

다음 절차를 사용하여 대화형 워크플로를 만들거나 수정할 수 있습니다.

<div>


> [!NOTE]  
> Lync Server 관리 셸 또는 응답 그룹 구성 도구를 사용 하 여 대화형 워크플로를 만들고 수정할 수 있습니다. Lync Server 제어판에서 응답 그룹 구성 도구에 액세스 하거나, 다음 URL: <STRONG>https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>을 입력 하 여 웹 브라우저에서 페이지를 직접 열 수 있습니다.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>응답 그룹 구성 도구를 사용 하 여 대화형 워크플로를 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **응답 그룹**을 클릭하고 **워크플로**를 클릭합니다.

4.  **워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭합니다.

5.  **서비스 선택** 검색 필드에 만들거나 수정할 워크플로를 호스트 하는 **applicationserver** 서비스의 이름 전부 또는 일부를 입력 합니다. 서비스 결과 목록에서 원하는 서비스를 클릭하고 **확인**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 응답 그룹 구성 도구가 열립니다. <STRONG>Https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>URL을 입력 하 여 웹 브라우저에서 직접 응답 그룹 구성 도구를 열 수도 있습니다.

    
    </div>

6.  다음 중 하나를 수행합니다.
    
      - **새 워크플로 만들기** 아래에서 **대화형** 옆에 있는 **만들기**를 클릭합니다.
    
      - **기존 워크플로 관리**에서 변경할 워크플로를 찾은 다음 **동작**에서 **편집**을 클릭합니다.

7.  사용자가 워크플로 호출을 시작할 수 있도록 준비되지 않은 경우 **워크플로 활성화** 확인란의 선택을 취소합니다.
    
    <div>
    

    > [!NOTE]  
    > 관리 워크플로를 만들려는 경우 <STRONG>워크플로 활성화</STRONG>를 선택해야 합니다. 활성화된 관리 워크플로를 저장한 후에는 이 워크플로를 수정하고 비활성화할 수 있습니다.

    
    </div>

8.  페더레이션 사용자가 그룹을 호출할 수 있도록 허용하려면 **페더레이션 사용** 확인란을 선택합니다. 또한 페더레이션에 대해 구성 된 응답 그룹 응용 프로그램에 적용 되는 외부 액세스 정책도 있어야 합니다.
    
    <div>
    

    > [!NOTE]  
    > 전역 외부 액세스 정책은 응답 그룹 응용 프로그램에 적용 됩니다. Lync Server 제어판을 사용 하거나 <STRONG>get-csexternalaccesspolicy</STRONG> cmdlet을 사용 하 여 Enableout access 매개 변수를 True로 설정 하 여 응답 그룹 페더레이션을 위한 전역 정책을 구성할 수 있습니다. 전역 정책 설정은 사이트 또는 사용자 정책이 할당되지 않은 모든 사용자에게 적용된다는 점에 유의하십시오. 따라서 응답 그룹에 대한 이 설정을 변경하기 전에 페더레이션 설정이 조직의 요구 사항을 충족하는지 확인해야 합니다. 정책이 사용자에 게 적용 되는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013에서 외부 액세스 정책 관리</A>를 참조 하세요. 페더레이션 설정에 대 한 자세한 내용은 <STRONG>get-csexternalaccesspolicy</STRONG> In Lync Server Management Shell 설명서를 참조 하십시오.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Lync Online에서 호스트 되는 사용자는 온-프레미스 배포에서 호스트 되는 응답 그룹에 대 한 호출을 수행할 수 없습니다. 이는 하이브리드 배포와 온-프레미스 배포가 Lync Online 배포와 연결 된 경우 모두에 적용 됩니다.

    
    </div>

9.  통화하는 동안 에이전트의 ID를 숨기려면 **에이전트 익명성 사용** 확인란을 선택합니다.
    
    <div>
    

    > [!NOTE]  
    > 통화가 연결된 후 에이전트 또는 발신자가 IM(인스턴트 메시징) 및 비디오를 추가할 수 있지만 IM 또는 비디오로 익명 통화를 시작할 수는 없습니다. 익명 에이전트는 통화를 보류하고, 전송(무조건 전송 및 협의 전송)하고, 대기시킨 후 재개할 수도 있습니다. 익명 통화는 회의, 응용 프로그램 공유 및 데스크톱 공유, 파일 전송, 화이트보드 및 데이터 공동 작업, 통화 기록을 지원하지 않습니다. Lync VDI 플러그 인을 사용 하는 에이전트는 들어오는 호출을 익명으로 받을 수 있지만 발신 전화를 익명으로 만들 수는 없습니다.

    
    </div>

10. **전화를 받을 그룹의 주소를 입력하십시오**에 워크플로 호출에 응답할 그룹의 SIP URI(Uniform Resource Identifier) 주소를 입력합니다.

11. **표시 이름**에 클라이언트에서 워크플로에 대해 표시하도록 할 이름(예: Sales IVR Response Group)을 입력합니다.
    
    <div>
    

    > [!NOTE]  
    > 표시 이름에 "&lt;" 또는 "&gt;" 문자를 포함 하지 마십시오. RGS Presence Watcher 또는 알림 서비스는 예약되어 있으므로 표시 이름으로 사용할 수 없습니다.

    
    </div>

12. **전화 번호**에 응답 그룹의 줄 URI(예: +14255550165)를 입력합니다.

13. **표시 이름**에 응답 그룹에 대해 표시할 번호(예: +1 (425) 555-0165)를 입력합니다.

14. 반드시 **설명**에 Lync 클라이언트의 대화 상대 카드에 표시할 워크플로에 대 한 설명을 입력 합니다.

15. 이 워크플로를 응답 그룹 관리자를 통해 관리하려는 경우 **워크플로 유형**에서 **관리**를 선택합니다. 응답 그룹 관리자를 워크플로에 할당 하려면 다음을 수행 합니다.
    
    1.  이 워크플로 관리자의 SIP URI를 입력하고 **추가**를 클릭합니다.
    
    2.  추가 관리자의 SIP URI를 입력하여 워크플로에 추가하고 **추가**를 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 응답 그룹의 관리자로 지정된 모든 사용자는 CsResponseGroupManager 역할이 할당되어야 합니다. 이 역할이 할당되지 않은 사용자는 응답 그룹을 관리할 수 없습니다.

    
    </div>

16. **2단계 언어 선택** 아래에서 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭합니다.

17. 환영 메시지를 구성하려면 **3단계 환영 메시지 구성** 아래에서 **환영 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행합니다.
    
      - 환영 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용**을 클릭한 다음 텍스트 상자에 환영 메시지를 입력합니다.
        
        <div>
        

        > [!NOTE]  
        > 입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.

        
        </div>
    
      - 환영 메시지에 웨이브 또는 Windows Media 오디오 파일 녹음을 사용하려면 **녹음 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 오디오 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

18. **4단계 업무 시간 지정** 아래에 있는 **표준 시간대** 상자에서 워크플로의 표준 시간대를 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 표준 시간대는 워크플로의 발신자 및 에이전트가 거주하는 지역의 표준 시간대로서, 시작 및 종료 시간을 계산하는 데 사용됩니다. 예를 들어 북미 동부 표준 시간대를 사용하도록 워크플로가 구성되어 있고 오전 7시에 시작하여 오전 11:00:00시에 끝나도록 워크플로를 예약한 경우 시작 및 종료 시간은 각각 동부 표준시 7시와 동부 표준시 23시로 설정됩니다. 시간은 24시간 형식으로 입력해야 합니다.

    
    </div>

19. 다음 중 하나를 수행하여 사용할 업무 시간 일정의 유형을 선택합니다.
    
      - 미리 정의된 업무 시간 일정을 사용하려면 **미리 설정된 일정 사용**을 클릭한 다음 드롭다운 메뉴에서 사용할 일정을 선택합니다.
        
        <div>
        

        > [!NOTE]  
        > 이 옵션을 선택하려면 이전에 미리 설정된 일정이 하나 이상 있어야 합니다. <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet을 사용하여 미리 설정된 일정을 정의할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Lync Server 2013에서 응답 그룹 업무 시간 정의</A>를 참조 하세요. 미리 설정된 일정을 선택한 경우 응답 그룹을 사용할 수 있는 요일 및 시간으로 <STRONG>요일</STRONG>, <STRONG>시작</STRONG> 및 <STRONG>종료</STRONG>가 자동으로 채워집니다.

        
        </div>
    
      - 이 워크플로에만 적용되는 사용자 지정 일정을 사용하려면 **사용자 지정 일정 사용**을 클릭합니다.

20. 이 워크플로에 대한 사용자 지정 일정을 만들려면 응답 그룹을 사용할 수 있는 요일 확인란을 클릭합니다.

21. 사용자 지정 일정을 만들려면 응답 그룹을 사용할 수 있는 **시작** 및 **종료** 시간을 입력합니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>시작</STRONG> 및 <STRONG>종료</STRONG> 시간은 24시간 형식이어야 합니다. 예를 들어 평일 오전 9시에서 오후 5시까지 근무하고 12시부터 점심 시간 동안 문을 닫는 경우 업무 시간은 <STRONG>시작</STRONG> 9:00, <STRONG>종료</STRONG> 12:00, <STRONG>시작</STRONG> 13:00 및 <STRONG>종료</STRONG> 17:00로 지정됩니다.

    
    </div>

22. 근무하지 않는 동안 메시지를 재생하려면 **응답 그룹의 업무 시간이 지났을 때 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 메시지를 지정합니다.
    
      - 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용**을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.
        
        <div>
        

        > [!NOTE]  
        > 입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.

        
        </div>
    
      - 메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

23. 메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).
    
      - 통화 연결을 끊으려면 **전화 끊기**를 클릭합니다.
    
      - 통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환**을 클릭하고 음성 메일 주소를 입력합니다. 음성 메일 \<주소 형식은 사용자 이름\>@\<domainname\> (예: bob@contoso.com)입니다.
    
      - 통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환**을 클릭하고 사용자 주소를 입력합니다. \<사용자 주소 형식은 username\>@\<domainname\>입니다.
    
      - 통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환**을 클릭하고 전화 번호를 입력합니다. 전화 번호 형식은 \<번호\>@\<domainname\> (예: + 14255550121@contoso.com)입니다. 도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.

24. **5단계 휴일 지정** 아래에서 응답 그룹이 근무하지 않는 요일을 정의하는 하나 이상의 휴일 집합에 대한 확인란을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 워크플로를 구성하기 전에 휴일 및 휴일 집합을 정의해야 합니다. <STRONG>New-CsRgsHoliday</STRONG> 및 <STRONG>New-CsRgsHolidaySet</STRONG> cmdlet을 사용하여 휴일 및 휴일 집합을 정의할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Lync Server 2013에서 응답 그룹 휴일 집합 정의</A>를 참조 하십시오.

    
    </div>

25. 휴일에 메시지를 재생하려면 **휴일에 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 재생할 메시지를 지정합니다.
    
      - 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용**을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.
        
        <div>
        

        > [!NOTE]  
        > 입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.

        
        </div>
    
      - 메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

26. 메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).
    
      - 통화 연결을 끊으려면 **전화 끊기**를 클릭합니다.
    
      - 통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환**을 클릭하고 음성 메일 주소를 입력합니다. 음성 메일 \<주소 형식은 사용자 이름\>@\<domainname\> (예: bob@contoso.com)입니다.
    
      - 통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환**을 클릭하고 사용자 주소를 입력합니다. \<사용자 주소 형식은 username\>@\<domainname\>입니다.
    
      - 통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환**을 클릭하고 전화 번호를 입력합니다. 전화 번호 형식은 \<번호\>@\<domainname\> (예: + 14255550121@contoso.com)입니다. 도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.

27. **6단계 대기 음악 구성** 아래에서 다음 중 하나를 수행하여 에이전트를 기다리는 동안 발신자에게 들려줄 음악을 선택합니다.
    
      - 기본 대기 음악 녹음을 사용하려면 **기본값 사용**을 클릭합니다.
    
      - 오디오 파일 녹음을 대기 음악에 사용하려면 **음악 파일 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **음악 파일** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

28. **7단계 대화형 음성 응답 구성**의 **사용자에게 다음 텍스트 또는 녹음된 메시지가 재생됩니다** 머리글 아래에서 다음과 같이 발신자에게 제공할 질문을 지정합니다.
    
      - 질문을 텍스트 형식으로 입력하려면 **텍스트 음성 변환 사용**을 클릭한 다음 텍스트 상자에 질문을 입력합니다.
        
        <div>
        

        > [!NOTE]  
        > 입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > "#" 기호는 텍스트 음성 변환 엔진에서 "숫자"라는 단어로 변환합니다. # 키를 참조해야 하는 경우 프롬프트에 기호 대신 키 이름을 사용해야 합니다. 예를 들어 "sales와 대화 하려면 파운드 키를 누릅니다."

        
        </div>
    
      - 질문이 포함된 미리 녹음된 오디오 파일을 사용하려면 **녹음 선택**을 클릭한 다음 **녹음** 링크를 클릭하여 파일을 업로드합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 오디오 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 파일을 로드한 다음 필요에 따라 텍스트 상자에 질문을 입력할 수 있습니다. 이렇게 하면 질문과 발신자의 응답이 응답 에이전트로 전달됩니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

29. **응답 1** 아래에서 다음을 수행하여 질문에 대한 첫 번째 가능한 응답을 지정합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 음성 응답에 따옴표(")를 사용하지 마십시오. 따옴표를 사용하면 IVR에 실패합니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 발신자가 음성과 영숫자 키패드 입력 중 하나 또는 둘 다를 사용하여 응답하도록 허용할 수 있습니다.

    
    </div>
    
      - 발신자가 음성을 사용하여 응답하도록 하려면 **음성 응답 입력** 상자에 응답을 입력합니다.
    
      - 발신자가 키패드의 키를 눌러 응답하도록 하려면 **숫자** 상자에서 키패드 숫자를 클릭합니다.

30. 다음과 같이 발신자를 큐로 라우팅할지 또는 다른 질문을 제공할지 지정합니다.
    
      - 발신자를 큐로 라우팅하려면 **큐로 보내기**를 클릭한 다음 **큐 선택**에서 사용할 큐를 클릭합니다.
    
      - 다른 질문을 제공하려면 **또 다른 질문하기**를 클릭한 다음 **텍스트 음성 변환 사용**을 클릭하고 질문을 입력하거나 **녹음 선택**을 클릭합니다. 이 섹션의 응답 그룹을 사용하여 추가 질문에 가능한 최대 4개의 응답 및 각 응답에 사용할 큐를 지정할 수 있습니다. 세 번째 또는 네 번째 가능한 응답을 지정하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭합니다.

31. 28단계와 29단계를 반복하여 원래 질문에 가능한 최대 3개의 응답을 추가로 지정하여 가능한 응답 및 각 응답에 대해 수행할 작업을 지정합니다. 세 번째 또는 네 번째 가능한 응답을 지정하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭합니다.

32. **배포**를 클릭합니다.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a>Windows PowerShell을 사용 하 여 대화형 워크플로를 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  응답 그룹 서비스의 서비스 이름을 검색하여 변수 하나에 할당합니다. 명령줄에서 다음을 실행합니다.
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  대화형 워크플로를 만들려면 두 개 이상의 큐와 두 개 이상의 에이전트 그룹이 필요합니다. 먼저 다음을 실행하여 에이전트 그룹을 만듭니다.
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  다음을 실행하여 큐를 만듭니다.
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  다음을 실행하여 첫 번째 응답 그룹 프롬프트를 만듭니다.
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  그런 다음 프롬프트 후에 수행할 동작을 만듭니다. 다음을 실행합니다.
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  다음을 실행하여 첫 번째 응답 그룹 답변을 만듭니다.
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  이제 두 번째 프롬프트, 호출 동작 및 답변을 만듭니다. 먼저 다음을 실행하여 프롬프트를 만듭니다.
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. 다음을 실행하여 큐를 만듭니다.
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. 다음을 실행하여 두 번째 응답 그룹 답변을 만듭니다.
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. 다음을 실행하여 최상위 프롬프트를 만듭니다.
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. 다음을 실행하여 최상위 질문을 만듭니다.
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. 이제 다음을 실행하여 워크플로를 만듭니다.
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > 응답 그룹의 관리자로 지정된 모든 사용자는 CsResponseGroupManager 역할이 할당되어야 합니다. 이 역할이 할당되지 않은 사용자는 응답 그룹을 관리할 수 없습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

