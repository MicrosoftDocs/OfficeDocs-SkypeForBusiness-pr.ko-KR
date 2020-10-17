---
title: 'Lync Server 2013: 헌트 그룹 워크플로 만들기 또는 수정'
description: 'Lync Server 2013: 헌트 그룹 워크플로를 만들거나 수정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95f6374352c87d13b1e5c09bcef267059016eae0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570724"
---
# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a>Lync Server 2013에서 헌트 그룹 워크플로 만들기 또는 수정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-09-11_

다음 방법 중 하나를 사용하여 헌트 그룹 워크플로를 만들거나 수정합니다.

<div>


> [!NOTE]  
> Lync Server 관리 셸 또는 응답 그룹 구성 도구를 사용 하 여 헌트 그룹 워크플로를 만들고 수정할 수 있습니다. Lync Server 제어판에서 응답 그룹 구성 도구에 액세스 하거나, 다음 URL: <STRONG>Https://</STRONG> &lt; webpoolfqdn &gt; <STRONG>/RgsConfig</STRONG>을 입력 하 여 웹 브라우저에서 페이지를 직접 열 수 있습니다.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>응답 그룹 구성 도구를 사용 하 여 헌트 그룹 워크플로를 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **응답 그룹**을 클릭하고 **워크플로**를 클릭합니다.

4.  **워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭합니다.

5.  **서비스 선택** 검색 필드에 만들거나 변경할 워크플로를 호스팅하는 **ApplicationServer** 서비스의 이름 전부 또는 일부를 입력합니다. 서비스 결과 목록에서 원하는 서비스를 클릭하고 **확인**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 응답 그룹 구성 도구가 열립니다. <STRONG>Https://</STRONG> &lt; webpoolfqdn &gt; <STRONG>/RgsConfig</STRONG>URL을 입력 하 여 웹 브라우저에서 직접 응답 그룹 구성 도구를 열 수도 있습니다.

    
    </div>

6.  다음 중 하나를 수행합니다.
    
      - **새 워크플로 만들기**의 헌트 그룹 옆에 있는 **만들기**를 클릭합니다.
    
      - **기존 워크플로 관리**에서 변경할 워크플로를 찾은 다음 **동작**에서 **편집**을 클릭합니다.

7.  사용자가 워크플로를 호출할 준비가 되면 **워크플로 활성화**를 선택합니다.
    
    <div>
    

    > [!NOTE]  
    > 관리되는 워크플로를 만들어야 하는 경우 <STRONG>워크플로 활성화</STRONG>를 선택해야 합니다. 관리되는 활성 워크플로를 저장한 후에는 해당 워크플로를 수정하고 비활성화할 수 있습니다.

    
    </div>

8.  페더레이션 사용자가 그룹을 호출할 수 있도록 허용하려면 **페더레이션 사용** 확인란을 선택합니다. 또한 페더레이션에 대해 구성 된 응답 그룹 응용 프로그램에 적용 되는 외부 액세스 정책도 있어야 합니다.
    
    <div>
    

    > [!NOTE]  
    > 전역 외부 액세스 정책은 응답 그룹 응용 프로그램에 적용 됩니다. Lync Server 제어판을 사용 하거나 <STRONG>get-csexternalaccesspolicy</STRONG> cmdlet을 사용 하 여 Enableout access 매개 변수를 True로 설정 하 여 응답 그룹 페더레이션을 위한 전역 정책을 구성할 수 있습니다. 전역 정책 설정은 사이트 또는 사용자 정책이 할당되지 않은 모든 사용자에게 적용된다는 점에 유의하십시오. 따라서 응답 그룹에 대한 이 설정을 변경하기 전에 페더레이션 설정이 조직의 요구 사항을 충족하는지 확인해야 합니다. 정책이 사용자에 게 적용 되는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013에서 외부 액세스 정책 관리</A>를 참조 하세요. 페더레이션 설정에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">get-csexternalaccesspolicy</A>를 참조 하십시오.

    
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

10. **전화를 받을 그룹의 주소를 입력하십시오**에 워크플로 호출에 응답할 그룹의 기본 SIP URI(Uniform Resource Identifier) 주소를 입력합니다.
    
    <div>
    

    > [!NOTE]  
    > 워크플로의 기본 URI는 워크플로가 식별 및 참조되는 방식입니다. 입력 한 SIP URI는 Active Directory 도메인 서비스에서 연락처 개체로 만들어집니다. URI를 만들려면 개체가 Active Directory에서 고유 해야 합니다.

    
    </div>

11. **표시 이름**에 워크플로에 대해 표시할 이름을 입력 합니다 (예: Sales Response 그룹).
    
    <div>
    

    > [!NOTE]  
    > &lt;표시 이름에 "" 또는 "" 문자를 포함 하지 마십시오 &gt; . <STRONG>RGS Presence Watcher </STRONG> 또는 <STRONG>RGS Presence Watcher</STRONG>는 예약되어 있으므로 표시 이름으로 사용할 수 없습니다.

    
    </div>

12. **전화 번호**에 응답 그룹의 줄 URI(예: +14255550165)를 입력합니다.

13. **표시 이름**에 응답 그룹에 대해 표시할 번호(예: +1 (425) 555-0165)를 입력합니다.

14. 반드시 **설명**에 Lync 클라이언트의 대화 상대 카드에 표시할 워크플로에 대 한 설명을 입력 합니다.

15. 이 워크플로를 응답 그룹 관리자를 통해 관리하려는 경우 **워크플로 유형**에서 **관리**를 선택합니다. 응답 그룹 관리자를 워크플로에 할당 하려면 다음을 수행 합니다.
    
    1.  이 워크플로의 관리자 SIP URI를 입력하고 **추가**를 클릭합니다.
    
    2.  워크플로에 추가할 다른 관리자의 SIP URI를 입력하고 **추가**를 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 응답 그룹의 관리자로 지정된 모든 사용자에게 CsResponseGroupManager 역할이 할당되어야 합니다. 이 역할이 할당되지 않은 사용자는 응답 그룹을 관리할 수 없습니다.

    
    </div>

16. **2단계 언어 선택**에서 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭합니다.

17. 환영 메시지를 구성하려면 **3단계 환영 메시지 구성** 아래에서 **환영 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행합니다.
    
      - 환영 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용**을 클릭한 다음 텍스트 상자에 환영 메시지를 입력합니다.
        
        <div>
        

        > [!NOTE]  
        > 입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.

        
        </div>
    
      - 시작 메시지에 웨이브(.wav) 또는 Windows Media 오디오(.wma) 파일 녹음을 사용하려면 **녹음 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 오디오 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

18. **4단계 업무 시간 지정**의 **표준 시간대**에서 워크플로의 표준 시간대를 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 표준 시간대는 워크플로의 발신자 및 에이전트가 거주하는 지역의 표준 시간대로서, 시작 및 종료 시간을 계산하는 데 사용됩니다. 예를 들어 북미 동부 표준 시간대를 사용하도록 워크플로가 구성되어 있고 오전 7시에 시작하여 오후 11시에 끝나도록 워크플로를 예약한 경우 시작 및 종료 시간은 각각 동부 표준시 7시와 동부 표준시 23시로 설정됩니다. 시간은 24시간 형식으로 입력해야 합니다.

    
    </div>

19. 다음 중 하나를 수행하여 사용할 업무 시간 일정의 유형을 선택합니다.
    
      - 미리 정의된 업무 시간 일정을 사용하려면 **미리 설정된 일정 사용**을 클릭한 다음 드롭다운 메뉴에서 사용할 일정을 선택합니다.
        
        <div>
        

        > [!NOTE]  
        > 이 옵션을 선택하려면 이전에 미리 설정된 일정이 하나 이상 있어야 합니다. <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet을 사용하여 미리 설정된 일정을 정의할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Lync Server 2013에서 응답 그룹 업무 시간 정의</A>를 참조 하세요.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > 미리 설정된 일정을 선택한 경우 응답 그룹을 사용할 수 있는 요일 및 시간으로 <STRONG>요일</STRONG>, <STRONG>시작</STRONG> 및 <STRONG>종료</STRONG>가 자동으로 채워집니다.

        
        </div>
    
      - 이 워크플로에만 적용되는 사용자 지정 일정을 사용하려면 **사용자 지정 일정 사용**을 클릭합니다.

20. 이 워크플로에 대한 사용자 지정 일정을 만들려면 응답 그룹을 사용할 수 있는 요일 확인란을 클릭합니다.

21. 사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있는 주의 각 요일에 대해 **시작** 및 **종료** 시간을 입력합니다.
    
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
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

23. 메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).
    
      - 통화 연결을 끊으려면 **전화 끊기**를 클릭합니다.
    
      - 통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환**을 클릭하고 음성 메일 주소를 입력합니다. 음성 메일 주소 형식은 \<username\> @ \<domainName\> (예: bob@contoso.com)입니다.
    
      - 통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환**을 클릭하고 사용자 주소를 입력합니다. 사용자 주소 형식은 \<username\> @ \<domainName\> 입니다.
    
      - 통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환**을 클릭하고 전화 번호를 입력합니다. 전화 번호 형식은 \<number\> @ \<domainName\> (예: + 14255550121@contoso.com)입니다. 도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.

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
    
      - 통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환**을 클릭하고 음성 메일 주소를 입력합니다. 음성 메일 주소 형식은 \<username\> @ \<domainName\> (예: bob@contoso.com)입니다.
    
      - 통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환**을 클릭하고 사용자 주소를 입력합니다. 사용자 주소 형식은 \<username\> @ \<domainName\> 입니다.
    
      - 통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환**을 클릭하고 전화 번호를 입력합니다. 전화 번호 형식은 \<number\> @ \<domainName\> (예: + 14255550121@contoso.com)입니다. 도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.

27. **6단계 큐 구성**의 **전화를 받을 큐 선택**에서 에이전트가 사용 가능할 때까지 발신자를 대기 상태로 둘 큐를 선택합니다.

28. **7단계 대기 음악 구성**에서 다음 중 하나를 수행하여 에이전트를 기다리는 동안 발신자에게 들려줄 음악을 선택합니다.
    
      - 기본 대기 음악 녹음을 사용하려면 **기본값 사용**을 클릭합니다.
    
      - 대기 음악에 오디오 파일 녹음을 사용하려면 **음악 파일 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **음악 파일** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.
        
        <div>
        

        > [!NOTE]  
        > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.

        
        </div>

29. **배포**를 클릭합니다.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a>Windows PowerShell을 사용 하 여 헌트 그룹 워크플로를 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  시작 메시지로 재생할 프롬프트를 작성하여 변수에 저장합니다. 명령줄에서 다음을 실행합니다.
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    예를 들면 다음과 같습니다.
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > 오디오 파일을 음성 안내에 사용하려면 <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet을 사용합니다. 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">import-csrgsaudiofile</A>를 참조 하십시오.

    
    </div>

4.  통화가 이동될 해당 큐 또는 질문의 ID를 가져옵니다. 명령줄에서 다음을 실행합니다.
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    큐를 만드는 방법에 대 한 자세한 내용은 [get-csrgsqueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)를 참조 하십시오.

5.  업무 시간 동안 워크플로를 열 때 수행할 기본 동작을 정의하여 변수에 저장합니다. 명령줄에서 다음을 실행합니다.
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > 헌트 그룹 워크플로의 경우 기본적으로 통화를 큐로 이동해야 합니다. 이 매개 변수는 활성 워크플로에 필요합니다. 비활성 워크플로에는 필요하지 않습니다.

    
    </div>
    
    예를 들면 다음과 같습니다.
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  업무 시간과 휴일을 정의하려는 경우 워크플로를 만들거나 수정하기 전에 정의해야 합니다. 자세한 내용은 [(optional) lync server 2013에서 응답 그룹 업무 시간 정의](lync-server-2013-optional-define-response-group-business-hours.md) 및 [(선택 사항) lync Server 2013에서 응답 그룹 휴일 집합 정의](lync-server-2013-optional-define-response-group-holiday-sets.md)를 참조 하십시오.

7.  업무 시간 외나 휴일에 받는 통화에 대한 프롬프트를 만들려면 **New-CsRgsPrompt** cmdlet을 사용하여 프롬프트를 정의하고 **New-CsRgsCallAction**를 사용하여 프롬프트 후에 수행될 동작을 정의합니다. 자세한 내용은 [new-csrgsprompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) 및 [new-csrgscallaction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)를 참조 하십시오.

8.  Lync Server 응답 그룹 서비스에 대 한 서비스 이름을 검색 하 여 변수에 할당 합니다. 명령줄에 다음을 실행합니다.
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  워크플로를 만들거나 수정 합니다. 워크플로를 만들려면 **get-csrgsworkflow**을 사용 합니다. 워크플로를 수정 하려면 **get-csrgsworkflow**를 사용 합니다. 명령줄에 다음을 입력합니다.
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    예를 들면 다음과 같습니다.
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > 워크플로의 관리자로 지정된 모든 사용자에게 CsResponseGroupManager 역할을 할당해야 합니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 추가 선택적 매개 변수에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">get-csrgsworkflow</A> 또는 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">get-csrgsworkflow</A> 을 참조 하십시오.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[반드시 Lync Server 2013에서 응답 그룹 휴일 집합 정의](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[반드시 Lync Server 2013에서 응답 그룹 업무 시간 정의](lync-server-2013-optional-define-response-group-business-hours.md)  


[Get-csrgsworkflow](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[Get-csrgsworkflow](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[New-csrgsprompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[New-csrgscallaction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

