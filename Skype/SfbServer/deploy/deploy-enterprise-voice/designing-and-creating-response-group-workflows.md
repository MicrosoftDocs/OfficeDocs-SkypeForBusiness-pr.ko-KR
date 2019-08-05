---
title: 비즈니스용 Skype에서 응답 그룹 워크플로 디자인 및 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: 비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 워크플로를 디자인 하 고 만듭니다. 헌트 그룹 워크플로 및 대화형 워크플로 둘 다에 적용 됩니다.
ms.openlocfilehash: 2ae6562ed4182c4c2ac5a801aa72b0505a19cf4f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192090"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a>비즈니스용 Skype에서 응답 그룹 워크플로 디자인 및 만들기

비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 워크플로를 디자인 하 고 만듭니다. 헌트 그룹 워크플로 및 대화형 워크플로 둘 다에 적용 됩니다.

워크플로는 다른 사용자가 전화를 건 시간으로 울릴 때 까지의 통화 동작을 정의 합니다. 워크플로는 통화를 보류 하는 데 사용할 큐를 지정 하 고, 헌트 그룹 워크플로 또는 대화형 응답 그룹 워크플로에 사용할 질문 및 답변에 사용할 라우팅 방법을 지정 합니다.

워크플로는 환영 메시지, 보류 중인 음악, 업무 시간, 휴일 등의 설정도 정의 합니다.

> [!NOTE]
> 에이전트 그룹과 큐를 사용 하는 워크플로를 만들기 전에 만들어야 합니다.

## <a name="creating-or-modifying-a-hunt-group-workflow"></a>헌트 그룹 워크플로 만들기 또는 수정

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>응답 그룹 구성 도구를 사용 하 여 헌트 그룹 워크플로를 만들거나 수정 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.

3. 왼쪽 탐색 모음에서 **응답 그룹**을 클릭 한 다음 **워크플로**를 클릭 합니다.

4. **워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭 합니다.

5. 서비스 검색 **선택** 필드에 만들거나 변경할 워크플로를 호스트 하는 **applicationserver** 서비스 이름의 전부 또는 일부를 입력 합니다. 서비스 결과 목록에서 원하는 서비스를 클릭 한 다음 **확인**을 클릭 합니다.

    > [!NOTE]
    > 응답 그룹 구성 도구가 열립니다. 다음 URL을 입력 하 여 웹 브라우저에서 직접 응답 그룹 구성 도구를 열 수도 있습니다. https://\<webpoolfqdn/RgsConfig.\>

6. 다음 중 하나를 수행 합니다.

   - **새 워크플로 만들기**에서 **헌트 그룹**옆에 있는 **만들기**를 클릭 합니다.

   - **기존 워크플로 관리**에서 변경 하려는 워크플로를 찾은 다음, **실행**에서 **편집**을 클릭 합니다.

7. 사용자가 워크플로 호출을 시작할 준비가 되었으면 **워크플로 활성화**를 선택 합니다.

    > [!NOTE]
    >  관리 되는 워크플로를 만드는 경우 **워크플로 활성화**를 선택 해야 합니다. 관리 되는 활성 워크플로를 저장 한 후에는 수정 하 고 비활성화할 수 있습니다.

8. 페더레이션 사용자가 그룹에 전화를 걸 수 있도록 허용 하려면 **페더레이션 사용** 확인란을 선택 합니다. 또한 페더레이션에 대해 구성 된 응답 그룹 응용 프로그램에 적용 되는 외부 액세스 정책만 있어야 합니다.

    > [!NOTE]
    > 글로벌 외부 액세스 정책이 응답 그룹 응용 프로그램에 적용 됩니다. 비즈니스용 Skype Server 제어판을 사용 하거나 **Set-CsExternalAccessPolicy** cmdlet을 사용 하 여 Enableout 액세스 매개 변수를 True로 설정 하 여 응답 그룹 페더레이션에 대 한 전역 정책을 구성할 수 있습니다. 전역 정책 설정은 사이트 또는 사용자 정책을 할당 하지 않는 한 모든 사용자에 게 적용 된다는 점에 유의 하세요. 따라서 응답 그룹에 대해이 설정을 변경 하기 전에 페더레이션 설정이 조직의 요구 사항에 맞는지 확인 해야 합니다. 정책이 사용자에 게 적용 되는 방법에 대 한 자세한 내용은 [조직의 외부 액세스 정책 관리](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)를 참조 하세요. 페더레이션 설정에 대 한 자세한 내용은 [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps)를 참조 하세요.

    > [!NOTE]
    > 비즈니스용 Skype Online에서 호스트 되는 사용자는 온-프레미스 배포에서 호스트 되는 응답 그룹에 전화를 걸 수 없습니다. 이는 하이브리드 배포와 온-프레미스 배포를 비즈니스용 Skype Online 배포에 연결 하는 경우에 모두 마찬가지입니다.

9. 통화 중 에이전트의 id를 숨기려면 **에이전트 익명 사용** 확인란을 선택 합니다.

    > [!NOTE]
    > 관리자나 발신자는 전화를 설정한 후에 IM 및 비디오를 추가할 수 있지만, 익명 호출은 메신저 또는 비디오로 시작할 수 없습니다. 익명 에이전트는 통화 대기, 통화 전환 (블라인드 및 consultative 전송 모두)을 할 수 있으며 통화를 전환 하 고 검색할 수도 있습니다. 익명 통화는 회의, 응용 프로그램 공유 및 데스크톱 공유, 파일 전송, whiteboarding, 데이터 공동 작업, 통화 기록을 지원 하지 않습니다. Lync VDI 플러그 인을 사용 하는 상담원은 들어오는 호출을 익명으로 받을 수 있지만, 나가는 호출을 익명으로 할 수는 없습니다.

10. 에서 **전화를 받을 그룹의 주소 입력**에 워크플로 호출에 응답할 그룹의 기본 SIP uri (uniform resource identifier) 주소를 입력 합니다.

    > [!NOTE]
    > 워크플로의 기본 URI는 워크플로를 식별 하 고 참조 하는 방법입니다. 입력 하는 SIP URI는 Active Directory 도메인 서비스의 contact 개체로 만들어집니다. URI를 만들려면 개체가 Active Directory에서 고유 해야 합니다.

11. **표시 이름**에 워크플로에 대해 표시할 이름 (예: 영업 응답 그룹)을 입력 합니다.

    > [!NOTE]
    > 표시 이름에 "<" 또는 ">" 문자를 포함 하지 마세요. 다음 표시 이름은 예약 됨: **RGS 현재 감시자** 또는 **알림 서비스**이므로 사용 하지 마세요.

12. **전화 번호**에서 응답 그룹의 줄 URI를 입력 합니다 (예: + 14255550165).

13. **표시 번호**에서 응답 그룹에 대해 표시할 숫자를 입력 합니다 (예: + 1 (425) 555-0165).

14. ) **설명**에 비즈니스용 Skype에서 연락처 카드에 표시할 워크플로 설명을 입력 합니다.

15. **워크플로 유형에**서이 워크플로를 응답 그룹 관리자가 관리 하는 경우 **관리** 를 선택 합니다. 응답 그룹 관리자를 워크플로에 할당 하려면 다음을 실행 합니다.

    에서. 이 워크플로에 대 한 관리자의 SIP URI를 입력 하 고 **추가**를 클릭 합니다.

    b. 추가 관리자의 SIP URI를 입력 하 여 워크플로에 추가 하 고 **추가**를 클릭 합니다.

    > [!IMPORTANT]
    > 응답 그룹의 관리자로 지정 된 모든 사용자에 게 CsResponseGroupManager 역할을 할당 해야 합니다. 사용자에 게이 역할이 할당 되지 않은 경우 응답 그룹을 관리할 수 없습니다.

16. **2 단계에서 언어를 선택**하 고 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭 합니다.

17. 환영 메시지를 구성 하려면 **3 단계에서 환영 메시지 구성**확인란을 선택 하 고 다음 중 하나 **** 를 수행 합니다.

    - 환영 메시지를 발신자를 위해 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 환영 메시지를 입력 합니다.

    > [!NOTE]
    > 입력 한 텍스트에 HTML 태그를 포함 하지 않습니다. HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.

    - 환영 메시지에 웨이브 (.wav) 또는 Windows Media 오디오 (.wma) 파일 기록을 사용 하려면 **기록 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용 하려는 오디오 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.

    > [!NOTE]
    > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 [응답 그룹에 대 한 기술 요구 사항을](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)참조 하세요.

18. **4 단계에서 업무 시간을 지정**하 고 **표준 시간대**에서 워크플로의 표준 시간대를 클릭 합니다.

    > [!NOTE]
    > 표준 시간대는 워크플로의 호출자와 에이전트가 상주 하는 표준 시간대입니다. 이 메서드는 시작 시간과 종료 시간을 계산 하는 데 사용 됩니다. 예를 들어 워크플로가 북미 동부 표준 시간대를 사용 하도록 구성 되 고 워크플로가 오전 7:00 시에 열리도록 예약 된 경우 11:00 P.M.에서 시작 하 여 닫은 시간은 각각 7:00 동부 표준시와 23:00 동부 시간으로 간주 됩니다. (24 시간 표시법으로 시간을 입력 해야 합니다.)

19. 다음 중 하나를 실행 하 여 사용 하려는 업무 시간 일정의 유형을 선택 합니다.

    - 미리 정의 된 업무 시간 일정을 사용 하려면 **미리 설정 된 일정 사용**을 클릭 한 다음 드롭다운 목록에서 사용할 일정을 선택 합니다.

      > [!NOTE]
      > 이 옵션을 선택할 수 있으려면 이전에 미리 설정 된 일정이 하나 이상 정의 되어 있어야 합니다. **새 CSRgsHoursOfBusiness** cmdlet을 사용 하 여 미리 설정 된 일정을 정의 합니다. 자세한 내용은 [(선택 사항) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의](optional-define-response-group-business-hours.md)를 참조 하세요.

      > [!NOTE]
      > 미리 설정 된 일정을 선택 하면 **일**, **열기**및 **닫기** 가 자동으로 응답 그룹을 사용할 수 있는 날짜와 시간으로 채워집니다.

    - 이 워크플로에만 적용 되는 사용자 지정 일정을 사용 하려면 **사용자 지정 일정 사용**을 클릭 합니다.

20. 이 워크플로에 대 한 사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있는 요일의 확인란을 클릭 합니다.

21. 사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있는 각 요일에 대해 **열기** 및 **닫기** 시간을 입력 합니다.

    > [!NOTE]
    > **열기** 시간과 **종료** 시간은 24 시간 표기 형식 이어야 합니다. 예를 들어, office가 9 ~ 5 개의 작업일로 근무 하 고 점심 시간에 종료 되는 경우 업무 시간은 **열린** 9:00, **종료** 12:00, **열기** 13:00 및 **닫기** 17:00로 지정 됩니다.

22. Office가 열려 있지 않은 경우 메시지를 재생 하려면 **응답 그룹이 업무 시간을 초과 하면 메시지 재생** 확인란을 선택 하 고 다음 중 하나를 실행 하 여 재생할 메시지를 지정 합니다.

    - 메시지를 호출자의 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 메시지를 입력 합니다.

      > [!NOTE]
      > 입력 한 텍스트에 HTML 태그를 포함 하지 않습니다. HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.

    - 메시지에 오디오 파일 녹음/녹화를 사용 하려면 **기록 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.

      > [!NOTE]
      > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 오디오 파일 형식에 대 한 자세한 내용은 [응답 그룹에 대 한 기술 요구 사항을](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)참조 하세요.

23. 메시지가 재생 된 후 호출을 처리 하는 방법 지정 (메시지가 구성 된 경우):

    - 통화 연결을 끊으려면 **통화 연결 끊기를**클릭 합니다.

    - 전화를 음성 메일로 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 음성 메일 주소를 입력 합니다. 음성 메일 주소의 형식은 * \<사용자 이름\>*@*\<domainName\> * (예: bob@contoso.com)입니다.

    - 다른 사용자에 게 통화를 착신 전환 하려면 **SIP URI로 전달을**클릭 한 다음 사용자 주소를 입력 합니다. 사용자 주소의 형식은 _ \<username\>_@_\<domainName\>_ 입니다.

    - 통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 전화 번호를 입력 합니다. 전화 번호의 형식은 * \<번호\>*@*\<의 이름\> * (예: + 14255550121@contoso.com)입니다. 도메인 이름은 호출자를 올바른 대상으로 라우팅하는 데 사용 됩니다.

24. **5 단계에서 공휴일을 지정**하 고 응답 그룹을 비즈니스용으로 닫은 날을 정의 하는 하나 이상의 공휴일 집합에 해당 하는 확인란을 클릭 합니다.

    > [!NOTE]
    > 워크플로를 구성 하기 전에 휴일 및 휴일 집합을 정의 해야 합니다. **CsRgsHoliday** 및 **new-CsRgsHolidaySet** cmdlet을 사용 하 여 휴일 및 휴일 집합을 정의 합니다. 자세한 내용은 [(선택 사항) 비즈니스용 Skype에서 응답 그룹 공휴일 집합 정의](optional-define-response-group-holiday-sets.md)를 참조 하세요.

25. 휴일에서 메시지를 재생 하려면 **공휴일 중 메시지 재생** 확인란을 선택한 후 다음 중 하나를 실행 하 여 재생할 메시지를 지정 합니다.

    - 메시지를 호출자의 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 메시지를 입력 합니다.

    > [!NOTE]
    > 입력 한 텍스트에 HTML 태그를 포함 하지 않습니다. HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.

    - 메시지에 오디오 파일 녹음/녹화를 사용 하려면 **기록 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.

      > [!NOTE]
      > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 오디오 파일 형식에 대 한 자세한 내용은 [응답 그룹에 대 한 기술 요구 사항을](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)참조 하세요.

26. 메시지가 재생 된 후 호출을 처리 하는 방법 지정 (메시지가 구성 된 경우):

    - 통화 연결을 끊으려면 **통화 연결 끊기를**클릭 합니다.

    - 전화를 음성 메일로 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 음성 메일 주소를 입력 합니다. 음성 메일 주소의 형식은 * \<사용자 이름\>*@*\<domainName\> * (예: bob@contoso.com)입니다.

    - 다른 사용자에 게 통화를 착신 전환 하려면 **SIP URI로 전달을**클릭 한 다음 사용자 주소를 입력 합니다. 사용자 주소의 형식은 _ \<username\>_@_\<domainName\>_ 입니다.

    - 통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 전화 번호를 입력 합니다. 전화 번호의 형식은 * \<번호\>*@*\<의 이름\> * (예: + 14255550121@contoso.com)입니다. 도메인 이름은 호출자를 올바른 대상으로 라우팅하는 데 사용 됩니다.

27. **6 단계에서 큐 구성**에서 전화를 **받을 큐를 선택**하 고 에이전트를 사용할 수 있게 될 때까지 호출자를 보관할 큐를 선택 합니다.

28. **7 단계에서 음악을 보류할**때 다음 중 하나를 수행 하 여 에이전트를 기다리는 동안 호출자가 수신할 음악을 선택 합니다.

    - 기본 음악 보관 기록을 사용 하려면 **기본값 사용**을 클릭 합니다.

    - 대기 중인 음악에 오디오 파일 녹음/녹화를 사용 하려면 **음악 파일 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **음악 파일** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.

      > [!NOTE]
      > 모든 사용자가 제공 하는 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 오디오 파일 형식에 대 한 자세한 내용은 [응답 그룹에 대 한 기술 요구 사항을](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)참조 하세요.

29. **배포**를 클릭 합니다.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 헌트 그룹 워크플로를 만들거나 수정 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

3. 환영 메시지에 대해 재생할 프롬프트를 만들고 변수에 저장 합니다. 명령줄에서 다음을 실행 합니다.

   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    예를 들면 다음과 같습니다.

   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > 프롬프트에 오디오 파일을 사용 하려면 **CsRgsAudioFile** cmdlet을 사용 합니다. 자세한 내용은 [가져오기-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)을 참조 하세요.

4. 호출이 리디렉션되는 큐 또는 질문의 id를 가져옵니다. 명령줄에서 다음을 실행 합니다.

   ```
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    큐 만들기에 대 한 자세한 내용은 [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)를 참조 하세요.

5. 업무 시간 동안 워크플로가 열려 있을 때 수행할 기본 작업을 정의 하 고 변수에 저장 합니다. 명령줄에서 다음을 실행 합니다.

   ```
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > 헌트 그룹 워크플로의 경우 기본 동작은 큐로 호출을 보내야 합니다. 이 매개 변수는 활성 워크플로에 필요 합니다. 비활성 워크플로에는 필요 하지 않습니다.

    예를 들면 다음과 같습니다.

   ```
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. 비즈니스 시간 및 휴일을 정의 하려는 경우 워크플로를 만들거나 수정 하기 전에 만들어야 합니다. 자세한 내용은 [(선택 사항) 비즈니스용 skype에서 응답 그룹 업무 시간 정의](optional-define-response-group-business-hours.md) 및 [(선택 사항) 비즈니스용 Skype에서 응답 그룹 명절 집합을 정의](optional-define-response-group-holiday-sets.md)하세요.

7. 업무 시간 또는 휴일을 통해 받은 통화에 대 한 메시지를 표시 하려면 **CsRgsPrompt** cmdlet을 사용 하 여 프롬프트를 정의 하 고 **new-CsRgsCallAction** 를 사용 하 여 프롬프트 후 수행할 작업을 정의 합니다. 자세한 내용은 [new-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) 및 [new-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)를 참조 하세요.

8. Lync Server 응답 그룹 서비스의 서비스 이름을 검색 하 여 변수에 할당 합니다. 명령에서 다음을 실행 합니다.

   ```
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. 워크플로를 만들거나 수정 합니다. 워크플로를 만들려면 **New-CsRgsWorkflow**을 사용 합니다. 워크플로를 수정 하려면 **Set-CsRgsWorkflow**를 사용 합니다. 명령줄에 다음을 입력 합니다.

   ```
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    예를 들면 다음과 같습니다.

   ```
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > 워크플로에 대해 지정 된 모든 사용자에 게 CsResponseGroupManager 역할을 할당 해야 합니다.

     > [!NOTE]
     > 추가 선택적 매개 변수에 대 한 자세한 내용은 [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) 또는 [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps) 을 참조 하세요.

## <a name="designing-an-interactive-workflow"></a>대화형 워크플로 디자인

IVR (대화형 음성 응답)을 사용 하 여 발신자의 정보를 얻고 해당 큐로 전화를 보낼 수 있습니다. 질문 및 답변 쌍에 따라 사용할 대기열이 결정 됩니다. 호출자의 응답에 따라 호출자가 후속 질문을 알리거나 해당 큐에 라우팅됩니다. IVR 질문이 나 발신자의 응답은 통화를 수락 하는 응답 에이전트에 제공 되며, 상담원에 게 중요 한 정보를 제공 합니다.

### <a name="overview-of-ivr-features"></a>IVR 기능 개요

응답 그룹 응용 프로그램은 26 개 언어의 음성 인식 및 텍스트 음성 변환 기능을 제공 합니다. 텍스트 음성 변환 또는 웨이브 (.wav) 또는 Windows Media 오디오 (.wma) 파일을 사용 하 여 IVR 질문을 입력할 수 있습니다. 발신자는 음성 또는 DTMF (multifrequency) 응답을 사용 하 여 응답할 수 있습니다.

대화형 워크플로는 두 가지 수준의 질문을 지원 하며 각 질문에 대 한 답변은 4 개까지 가능 합니다. IVR은 호출자에 게 질문을 하 고 호출자의 응답에 따라 호출자를 큐에 라우팅하고 또는 두 번째 질문을 요청 합니다. 두 번째 질문에는 네 가지 가능한 답을 사용할 수도 있습니다. 두 번째 수준 질문에 대 한 응답에 따라 호출자가 적절 한 큐로 라우팅됩니다.

> [!NOTE]
> 비즈니스용 Skype Server Management Shell을 사용 하 여 통화 흐름을 디자인 하는 경우 IVR 질문에 대 한 다양 한 수준과 답변을 정의할 수 있습니다. 그러나 호출자의 사용 편리성을 위해 각각 6 개 이상의 질문을 사용 하지 않는 것이 좋습니다. 또한 세 가지 이상의 질문에 대 한 답변이 세 개 이상 포함 된 통화 흐름을 디자인 하는 경우에는 비즈니스용 Skype 서버 제어판을 사용 하 여 통화 흐름을 편집할 수 없습니다.

IVR 질문이 나 발신자의 응답은 통화를 수락 하는 응답 하는 상담원에 게 제공 됩니다.

### <a name="working-with-speech-technologies"></a>음성 기술 사용

음성 인식과 텍스트 음성 변환 등의 음성 기술은 고객 환경을 개선 하 고 사람들이 정보에 더욱 자연스럽 게 액세스할 수 있도록 합니다. 그러나 음성 엔진에서 지정 된 텍스트 또는 사용자 음성 응답을 올바르게 인식 하지 못하는 경우가 있을 수 있습니다. 예를 들어 "#" 기호는 텍스트 음성 변환 엔진에 의해 "number" 라는 단어로 번역 됩니다. 이 문제는 다음과 같은 방법으로 완화할 수 있습니다.

- 음성 엔진은 발신자의 5 회 질문에 대 한 답변을 제공 합니다. 발신자가 질문에 잘못 대답 하거나 (즉, 답변이 지정 된 응답 중 하나가 아님) 대답을 제공 하지 않으면 호출자가 질문에 대답할 수 있는 또 다른 기회를 얻습니다. 발신자는 연결이 끊어지기 전에 질문에 대 한 답변을 5 회 시도 합니다. 각 발신자 오류 발생 후 사용자 지정 메시지를 재생 하도록 IVR을 구성할 수 있습니다. 질문은 매번 반복 됩니다.

- 음성 엔진에서 응답으로 앰비언트 노이즈가 해석 될 가능성을 최소화 하려면 긴 응답을 사용 합니다. 예를 들어 답은 두 개 이상 음절을가지고 있으며 서로 크게 달라 야 합니다.

- 질문에 음성 및 DTMF 응답이 둘 다 있는 경우 DTMF 응답 대신 개념을 나타내는 단어를 사용 하 여 음성 응답을 구성 합니다. 예를 들어 "누르기"를 사용 하는 대신 "단 1 또는 대금 청구"를 사용 하는 것이 좋습니다.

- IVR을 디자인 한 후에는 워크플로를 호출 하 고, 메시지를 듣고, 음성을 사용 하는 각 프롬프트에 응답 하 고, IVR의 사운드가 예상 대로 작동 하는지 확인 합니다. 그런 다음 IVR을 수정 하 여 해석 문제를 해결할 수 있습니다. 앞의 예제를 따라 # key를 참조 해야 하는 경우 # symbol 대신 키 이름을 사용 하도록 IVR 프롬프트를 다시 작성할 수 있습니다. 예를 들어 "영업부와 대화 하려면 우물 정자" 키를 누릅니다.

### <a name="ivr-design-examples"></a>IVR 디자인 예제

다음 섹션에는 다양 한 IVR 시나리오 및 질문과 대답 쌍의 예가 포함 되어 있습니다.

#### <a name="ivr-with-one-level-of-questions"></a>한 가지 수준의 질문이 있는 IVR

다음 예제에서는 한 가지 수준의 질문을 사용 하는 IVR을 보여 줍니다. 음성 인식을 사용 하 여 발신자의 응답을 감지 합니다.

 **질문:** "인적 자원을 통화 해 주셔서 감사 합니다. 급여에 대 한 통화를 원하시면 급여를 말합니다. 그렇지 않으면 HR "이라고 말합니다."

- **옵션 1이 선택 되어 있습니다.** 호출자는 급여 팀으로 라우팅됩니다.

- **옵션 2가 선택 되었습니다.** 발신자는 인적 자원 팀에 게 전달 됩니다.

다음 그림은 통화 흐름을 보여 줍니다.

 **한 수준의 대화형 통화 흐름**

![대화형 음성 응답을 사용하여 통화 흐름 설계](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a>두 가지 수준의 질문이 있는 IVR

다음 예제에서는 두 가지 수준의 질문을 사용 하는 IVR을 보여 줍니다. 이를 통해 발신자는 음성 또는 DTMF 키패드 입력을 사용 하 여 응답할 수 있습니다.

 **질문:** "IT 지원 센터에 전화 해 주셔서 감사 합니다. 네트워크 액세스 문제가 있는 경우 1 번 누르거나 네트워크를 말합니다. 소프트웨어 문제가 있는 경우 2 또는 말 소프트웨어를 누르세요. 하드웨어 문제가 있는 경우 3 번을 누르거나 하드웨어를 말합니다. "

- **옵션 1이 선택 되어 있습니다.** 발신자는 네트워크 지원 팀에 라우팅됩니다.

- **옵션 2가 선택 되었습니다.** 발신자에 게 후속 질문을 하는 메시지가 표시 됩니다.

    **질문:** "운영 체제 문제 라면 1 번을 누르거나 운영 체제를 말합니다. 내부 응용 프로그램에 문제가 있는 경우 2를 누르거나 내부 응용 프로그램을 말합니다. 그렇지 않으면 3을 누르거나 다른 단어를 말하기를 클릭 합니다.

  - **옵션 1이 선택 되어 있습니다.** 발신자는 운영 체제 지원 팀으로 라우팅됩니다.

  - **옵션 2가 선택 되었습니다.** 호출자는 내부 응용 프로그램 지원 팀으로 라우팅됩니다.

  - **옵션 3이 선택 되어 있습니다.** 발신자는 소프트웨어 지원 팀에 게 라우팅됩니다.

- **옵션 3이 선택 되어 있습니다.** 발신자에 게 후속 질문을 하는 메시지가 표시 됩니다.

    **질문:** "프린터 문제인 경우 1을 누릅니다. 그렇지 않으면 2를 누릅니다. "

  - **옵션 1이 선택 되어 있습니다.** 발신자는 프린터 지원 팀으로 라우팅됩니다.

  - **옵션 2가 선택 되었습니다.** 발신자는 하드웨어 지원 팀으로 라우팅됩니다.

다음 그림은 통화 흐름을 보여 줍니다.

 **2 수준 대화형 통화 흐름**

![대화형 음성 응답을 사용하여 통화 흐름 설계](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a>모범 사례

다음 목록에서는 IVR을 디자인 하기 위한 몇 가지 모범 사례에 대해 설명 합니다.

- 호출자가 작업에 빠르게 액세스할 수 있도록 합니다. IVR에 너무 많은 정보나 긴 마케팅 메시지를 제공 하지 마세요.

- 긴 메시지를 포함 하려는 경우 환영 메시지 대신 첫 번째 질문에 추가 하는 것이 좋습니다. 발신자는 질문에 대답 하 여 첫 번째 질문의 일부인 경우 메시지를 무시할 수 있지만,이 경우 환영 메시지를 우회할 수는 없습니다.

- 발신자의 언어로 말합니다. Stilted 언어를 사용 하지 마세요. 자연스럽 게 말할 것입니다.

- 효율적이 고 효과적인 메시지를 작성 합니다. 불필요 한 옵션을 제거 합니다. 호출자의 예상 응답이 문장의 끝에 오도록 정보를 구조화 합니다. 예를 들어 영업 팀에 게 문의 하려면 1을 누릅니다.

- 음성 응답을 사용자에 게 친숙 하 게 만듭니다. 예를 들어, DTMF 및 음성 응답을 모두 지정 하는 경우 "영업 팀에 게 말을 하려면 1을 누르고, 판매를 예로 들어"를 사용 합니다.

- 조직 전반에 배포 하기 전에 사용자 그룹에서 IVR을 테스트 합니다.

## <a name="creating-or-modifying-an-interactive-workflow"></a>대화형 워크플로 만들기 또는 수정

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>응답 그룹 구성 도구를 사용 하 여 대화형 워크플로를 만들거나 수정 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.

3. 왼쪽 탐색 모음에서 **응답 그룹**을 클릭 한 다음 **워크플로**를 클릭 합니다.

4. **워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭 합니다.

5. 서비스 검색 **선택** 필드에 만들거나 수정할 워크플로를 호스트 하는 **applicationserver** 서비스 이름의 전부 또는 일부를 입력 합니다. 서비스 결과 목록에서 원하는 서비스를 클릭 한 다음 **확인**을 클릭 합니다.

    > [!NOTE]
    > 응답 그룹 구성 도구가 열립니다. 다음 URL을 입력 하 여 웹 브라우저에서 직접 응답 그룹 구성 도구를 열 수도 있습니다. https://\<webpoolfqdn/RgsConfig.\>

6. 다음 중 하나를 수행 합니다.

   - **새 워크플로 만들기**에서 **대화형**옆에 있는 **만들기**를 클릭 합니다.

   - **기존 워크플로 관리**에서 변경 하려는 워크플로를 찾은 다음, **실행**에서 **편집**을 클릭 합니다.

7. 사용자가 워크플로 호출을 시작할 준비가 되지 않은 경우 **워크플로 활성화** 확인란의 선택을 취소 합니다.

    > [!NOTE]
    >  관리 되는 워크플로를 만드는 경우 **워크플로 활성화**를 선택 해야 합니다. 관리 되는 활성 워크플로를 저장 한 후에는 수정 하 고 비활성화할 수 있습니다.

8. 페더레이션 사용자가 그룹에 전화를 걸 수 있도록 허용 하려면 **페더레이션 사용** 확인란을 선택 합니다. 또한 페더레이션에 대해 구성 된 응답 그룹 응용 프로그램에 적용 되는 외부 액세스 정책만 있어야 합니다.

    > [!NOTE]
    > 글로벌 외부 액세스 정책이 응답 그룹 응용 프로그램에 적용 됩니다. 비즈니스용 Skype Server 제어판을 사용 하거나 **Set-CsExternalAccessPolicy** cmdlet을 사용 하 여 Enableout 액세스 매개 변수를 True로 설정 하 여 응답 그룹 페더레이션에 대 한 전역 정책을 구성할 수 있습니다. 전역 정책 설정은 사이트 또는 사용자 정책을 할당 하지 않는 한 모든 사용자에 게 적용 된다는 점에 유의 하세요. 따라서 응답 그룹에 대해이 설정을 변경 하기 전에 페더레이션 설정이 조직의 요구 사항에 맞는지 확인 해야 합니다. 정책이 사용자에 게 적용 되는 방법에 대 한 자세한 내용은 [조직의 외부 액세스 정책 관리](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)를 참조 하세요. 페더레이션 설정에 대 한 자세한 내용은 설명서의 **Set-CsExternalAccessPolicy** 을 참조 하세요.

    > [!NOTE]
    > 비즈니스용 Skype Online에서 호스트 되는 사용자는 온-프레미스 배포에서 호스트 되는 응답 그룹에 전화를 걸 수 없습니다. 이는 하이브리드 배포와 온-프레미스 배포를 비즈니스용 Skype Online 배포에 연결 하는 경우에 모두 마찬가지입니다.

9. 통화 중 에이전트의 id를 숨기려면 **에이전트 익명 사용** 확인란을 선택 합니다.

    > [!NOTE]
    > 관리자나 발신자는 전화를 설정한 후에 IM 및 비디오를 추가할 수 있지만, 익명 호출은 메신저 또는 비디오로 시작할 수 없습니다. 익명 에이전트는 통화 대기, 통화 전환 (블라인드 및 consultative 전송 모두)을 할 수 있으며 통화를 전환 하 고 검색할 수도 있습니다. 익명 통화는 회의, 응용 프로그램 공유 및 데스크톱 공유, 파일 전송, whiteboarding, 데이터 공동 작업, 통화 기록을 지원 하지 않습니다. Lync VDI 플러그 인을 사용 하는 상담원은 들어오는 호출을 익명으로 받을 수 있지만, 나가는 호출을 익명으로 할 수는 없습니다.

10. 에서 **전화를 받을 그룹의 주소 입력**에 워크플로 호출에 응답할 그룹의 기본 SIP uri (uniform resource identifier) 주소를 입력 합니다.

11. **표시 이름**에 워크플로에 대해 표시할 이름 (예: 영업권 IVR 응답 그룹)을 입력 합니다.

    > [!NOTE]
    > 표시 이름에 "\<" 또는 "\>" 문자를 포함 하지 마세요. 다음 표시 이름은 예약 됨: **RGS 현재 감시자** 또는 **알림 서비스**이므로 사용 하지 마세요.

12. **전화 번호**에서 응답 그룹에 대 한 줄 URI를 입력 합니다 (예: + 14255550165).

13. **표시 번호**에서 응답 그룹에 대해 표시할 숫자를 입력 합니다 (예: + 1 (425) 555-0165).

14. ) **설명**에 비즈니스용 Skype에서 연락처 카드에 표시할 워크플로에 대 한 설명을 입력 합니다.

15. **워크플로 유형에**서이 워크플로를 응답 그룹 관리자가 관리 하는 경우 **관리** 를 선택 합니다. 응답 그룹 관리자를 워크플로에 할당 하려면 다음을 실행 합니다.

    에서. 이 워크플로에 대 한 관리자의 SIP URI를 입력 하 고 **추가**를 클릭 합니다.

    b. 추가 관리자의 SIP URI를 입력 하 여 워크플로에 추가 하 고 **추가**를 클릭 합니다.

    > [!IMPORTANT]
    > 응답 그룹의 관리자로 지정 된 모든 사용자에 게 CsResponseGroupManager 역할을 할당 해야 합니다. 사용자에 게이 역할이 할당 되지 않은 경우 응답 그룹을 관리할 수 없습니다.

16. **2 단계에서 언어를 선택**하 고 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭 합니다.

17. 환영 메시지를 구성 하려면 **3 단계에서 환영 메시지 구성**확인란을 선택 하 고 다음 중 하나 **** 를 수행 합니다.

    - 환영 메시지를 발신자를 위해 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 환영 메시지를 입력 합니다.

    > [!NOTE]
    > 입력 한 텍스트에 HTML 태그를 포함 하지 않습니다. HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.

    - 환영 메시지에 웨이브 또는 Windows Media 오디오 파일 기록을 사용 하려면 **기록 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용 하려는 오디오 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.

    > [!NOTE]
    > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 [응답 그룹에 대 한 기술 요구 사항을](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)참조 하세요.

18. **4 단계에서 업무 시간을 지정**하 고 **표준 시간대** 상자에서 워크플로의 표준 시간대를 클릭 합니다.

    > [!NOTE]
    > 표준 시간대는 워크플로의 호출자와 에이전트가 상주 하는 표준 시간대입니다. 이 메서드는 시작 시간과 종료 시간을 계산 하는 데 사용 됩니다. 예를 들어 워크플로가 북미 동부 표준 시간대를 사용 하도록 구성 되 고 워크플로가 오전 7:00 시에 열리도록 예약 된 경우 11:00 P.M.에서 시작 하 여 닫은 시간은 각각 7:00 동부 표준시와 11:00 동부 시간으로 간주 됩니다. (24 시간 표시법으로 시간을 입력 해야 합니다.)

19. 다음 중 하나를 실행 하 여 사용 하려는 업무 시간 일정의 유형을 선택 합니다.

    - 미리 정의 된 업무 시간 일정을 사용 하려면 **미리 설정 된 일정 사용**을 클릭 한 다음 드롭다운 목록에서 사용할 일정을 선택 합니다.

      > [!NOTE]
      > 이 옵션을 선택할 수 있으려면 이전에 미리 설정 된 일정이 하나 이상 정의 되어 있어야 합니다. **새 CsRgsHoursOfBusiness** cmdlet을 사용 하 여 미리 설정 된 일정을 정의 합니다. 자세한 내용은 [(선택 사항) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의](optional-define-response-group-business-hours.md)를 참조 하세요. 미리 설정 된 일정을 선택 하면 **일**, **열기**및 **닫기** 가 자동으로 응답 그룹을 사용할 수 있는 날짜와 시간으로 채워집니다.

    - 이 워크플로에만 적용 되는 사용자 지정 일정을 사용 하려면 **사용자 지정 일정 사용**을 클릭 합니다.

20. 이 워크플로에 대 한 사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있는 요일의 확인란을 클릭 합니다.

21. 사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 **** 수 있는 시간을 입력 하 고 **닫습니다** .

     > [!NOTE]
     > **열기** 시간과 **종료** 시간은 24 시간 표기 형식 이어야 합니다. 예를 들어, office가 9 ~ 5 개의 작업일로 근무 하 고 점심 시간에 종료 되는 경우 업무 시간은 **열린** 9:00, **종료** 12:00, **열기** 13:00 및 **닫기** 17:00로 지정 됩니다.

22. Office가 열려 있지 않은 경우 메시지를 재생 하려면 **응답 그룹이 업무 시간을 초과 하면 메시지 재생** 확인란을 선택 하 고 다음 중 하나를 실행 하 여 재생할 메시지를 지정 합니다.

    - 메시지를 호출자의 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 메시지를 입력 합니다.

      > [!NOTE]
      > 입력 한 텍스트에 HTML 태그를 포함 하지 않습니다. HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.

    - 메시지에 오디오 파일 녹음/녹화를 사용 하려면 **기록 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.

    > [!NOTE]
    > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 [응답 그룹에 대 한 기술 요구 사항을](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)참조 하세요.

23. 메시지가 재생 된 후 호출을 처리 하는 방법 지정 (메시지가 구성 된 경우):

    - 통화 연결을 끊으려면 **통화 연결 끊기를**클릭 합니다.

    - 전화를 음성 메일로 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 음성 메일 주소를 입력 합니다. 음성 메일 주소의 형식은 * \<사용자 이름\>*@*\<domainname\> * (예: bob@contoso.com)입니다.

    - 다른 사용자에 게 통화를 착신 전환 하려면 **SIP URI로 전달을**클릭 한 다음 사용자 주소를 입력 합니다. 사용자 주소의 형식은 _ \<username\>_@_\<domainname\>_ 입니다.

    - 통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 전화 번호를 입력 합니다. 전화 번호의 형식은 * \<번호\>*@*\<의 이름\> * (예: + 14255550121@contoso.com)입니다. 도메인 이름은 호출자를 올바른 대상으로 라우팅하는 데 사용 됩니다.

24. **5 단계에서 공휴일을 지정**하 고 응답 그룹을 비즈니스용으로 닫은 날을 정의 하는 하나 이상의 공휴일 집합에 해당 하는 확인란을 클릭 합니다.

    > [!NOTE]
    > 워크플로를 구성 하기 전에 휴일 및 휴일 집합을 정의 해야 합니다. **CsRgsHoliday** 및 **new-CsRgsHolidaySet** cmdlet을 사용 하 여 휴일 및 휴일 집합을 정의 합니다. 자세한 내용은 [(선택 사항) 비즈니스용 Skype에서 응답 그룹 공휴일 집합 정의](optional-define-response-group-holiday-sets.md)를 참조 하세요.

25. 휴일에서 메시지를 재생 하려면 **공휴일 중 메시지 재생** 확인란을 선택한 후 다음 중 하나를 실행 하 여 재생할 메시지를 지정 합니다.

    - 메시지를 호출자의 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 메시지를 입력 합니다.

      > [!NOTE]
      > 입력 한 텍스트에 HTML 태그를 포함 하지 않습니다. HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.

    - 메시지에 오디오 파일 녹음/녹화를 사용 하려면 **기록 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.

      > [!NOTE]
      > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 오디오 파일 형식에 대 한 자세한 내용은 [응답 그룹에 대 한 기술 요구 사항을](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)참조 하세요.

26. 메시지가 재생 된 후 호출을 처리 하는 방법 지정 (메시지가 구성 된 경우):

    - 통화 연결을 끊으려면 **통화 연결 끊기를**클릭 합니다.

    - 전화를 음성 메일로 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 음성 메일 주소를 입력 합니다. 음성 메일 주소의 형식은 * \<사용자 이름\>*@*\<domainname\> * (예: bob@contoso.com)입니다.

    - 다른 사용자에 게 통화를 착신 전환 하려면 **SIP URI로 전달을**클릭 한 다음 사용자 주소를 입력 합니다. 사용자 주소의 형식은 _ \<username\>_@_\<domainname\>_ 입니다.

    - 통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 전화 번호를 입력 합니다. 전화 번호의 형식은 * \<번호\>*@*\<의 이름\> * (예: + 14255550121@contoso.com)입니다. 도메인 이름은 호출자를 올바른 대상으로 라우팅하는 데 사용 됩니다.

27. **6 단계에서 음악 구성**에서 다음 중 하나를 수행 하 여 에이전트를 기다리는 동안 호출자가 수신할 작업을 선택 합니다.

    - 기본 음악 보관 기록 기능을 사용 하려면 **기본값 사용**을 클릭 합니다.

    - 대기 중인 음악에 오디오 파일 녹음/녹화를 사용 하려면 **음악 파일 선택을**클릭 합니다. 새 오디오 파일을 업로드 하려면 **음악 파일** 링크를 클릭 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.

    > [!NOTE]
    > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 [응답 그룹에 대 한 기술 요구 사항을](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)참조 하세요.

28. **7 단계 대화형 음성 응답 구성**아래에 있는 **사용자는 다음 텍스트 또는 녹음 된 메시지 제목을 들** 을 수 있습니다. 라는 질문을 지정 하 여 다음과 같이 발신자를 요청 합니다.

    - 질문을 텍스트 형식으로 입력 하려면 **텍스트 읽어주기 사용**을 클릭 하 고 텍스트 상자에 질문을 입력 합니다.

    > [!NOTE]
    > 입력 한 텍스트에 HTML 태그를 포함 하지 않습니다. HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.

    > [!NOTE]
    > "#" 기호는 텍스트 음성 변환 엔진에 의해 "number" 라는 단어로 번역 됩니다. # Key를 참조 해야 하는 경우에는 프롬프트에 기호 대신 키 이름을 사용 해야 합니다. 예를 들어 "영업부와 대화 하려면 우물 정자" 키를 누릅니다.

    - 질문을 포함 하는 미리 녹음 된 오디오 파일을 사용 하려면 **기록 선택**을 클릭 한 다음 **기록** 링크를 클릭 하 여 파일을 업로드 합니다. 새 브라우저 창에서 **찾아보기를**클릭 하 고 오디오 파일을 선택한 다음 **열기**를 클릭 합니다. **업로드** 를 클릭 하 여 파일을 로드 한 다음 선택적으로 텍스트 상자에 질문을 입력할 수 있습니다 (질문 및 호출자의 응답을 응답 하는 에이전트로 착신 전환 가능).

      > [!NOTE]
      > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다. 지원 되는 파일 형식에 대 한 자세한 내용은 [응답 그룹에 대 한 기술 요구 사항을](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)참조 하세요.

29. **응답 1**아래에서 다음을 수행 하 여 질문에 대 한 첫 번째 응답을 지정 합니다.

    > [!IMPORTANT]
    > 음성 응답에 따옴표 (")를 사용 하지 마세요. 큰따옴표는 IVR을 실패 시킵니다.

    > [!NOTE]
    > 전화 건 사람이 음성, 영숫자 키패드 입력 또는 둘 다를 사용 하 여 응답 하도록 선택할 수 있습니다.

    - 발신자가 음성을 사용 하 여 응답할 수 있도록 허용 하려면 **음성 응답 입력**에 대답을 입력 합니다.

    - 키패드에서 키를 눌러 발신자가 응답할 수 있도록 허용 하려면 키패드 숫자를 클릭 합니다. ****

30. 호출자를 큐로 보낼지 아니면 다음과 같이 다른 질문을 요청할지 여부를 지정 합니다.

    - 호출자를 큐로 라우팅하려면 큐 **에 보내기를**클릭 하 고 **큐에 선택**에서 사용할 큐를 클릭 합니다.

    - 다른 질문을 요청 하려면 **다른 질문**하기를 클릭 한 다음 **텍스트 읽어주기 사용** 을 클릭 하 여 질문을 입력 하거나 **기록 선택을**클릭 합니다. 이 섹션의 응답 그룹을 사용 하 여 추가 질문 및 각 응답에 대해 사용할 큐에 대해 최대 4 개의 응답을 지정할 수 있습니다. 세 번째 또는 네 번째 가능 응답을 지정 하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭 합니다.

31. 28 ~ 29 단계를 반복 하 여 가능 응답과 각 응답에 대해 수행할 작업을 지정 하 여 원래 질문에 대 한 답변을 최대 3 개까지 지정할 수 있습니다. 세 번째 또는 네 번째로 발생할 수 있는 답변을 지정 하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭 합니다.

32. **배포**를 클릭 합니다.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 대화형 워크플로를 만들거나 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

3. 응답 그룹 서비스의 서비스 이름을 검색 하 고 변수에 할당 합니다. 명령줄에서 다음을 실행 합니다.

   ```
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. 대화형 워크플로에는 두 개 이상의 큐와 두 개 이상의 에이전트 그룹이 필요 합니다. 먼저 에이전트 그룹을 만듭니다. 런

   ```
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. 큐를 만듭니다. 런

   ```
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. 첫 번째 응답 그룹 메시지를 만듭니다. 런

   ```
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. 그런 다음 프롬프트 후에 수행할 작업을 만듭니다. 런

   ```
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. 첫 번째 응답 그룹 응답을 만듭니다. 런

   ```
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. 이제 두 번째 프롬프트를 만들고, 착신 동작을 수행 하 고, 응답 합니다. 먼저 프롬프트를 만듭니다. 런

   ```
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. 두 번째 호출 작업을 만듭니다. 런

    ```
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. 두 번째 응답 그룹 응답을 만듭니다. 런

    ```
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. 최상위 수준의 프롬프트를 만듭니다. 런

    ```
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. 최상위 수준의 질문을 만듭니다. 런

    ```
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. 이제 워크플로를 만듭니다. 런

    ```
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > 응답 그룹의 관리자로 지정 된 모든 사용자에 게 CsResponseGroupManager 역할을 할당 해야 합니다. 사용자에 게이 역할이 할당 되지 않은 경우 응답 그룹을 관리할 수 없습니다.

## <a name="see-also"></a>참고 항목

[) 비즈니스용 Skype에서 응답 그룹의 공휴일 집합 정의](optional-define-response-group-holiday-sets.md)

[) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의](optional-define-response-group-business-hours.md)

[새로운 CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[새로운 CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[새로운 CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

