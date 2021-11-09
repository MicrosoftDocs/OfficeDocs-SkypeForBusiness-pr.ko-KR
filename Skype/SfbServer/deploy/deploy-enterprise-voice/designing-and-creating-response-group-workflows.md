---
title: 2013에서 응답 그룹 워크플로 디자인 및 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: 응답 그룹 워크플로를 디자인하고 비즈니스용 Skype 서버 Enterprise Voice. 헌트 그룹 워크플로와 대화형 워크플로에 모두 설명되어 있습니다.
ms.openlocfilehash: ec92a0dfa378746db98a6377b2ebd51df0e77813
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864385"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a>2013에서 응답 그룹 워크플로 디자인 및 비즈니스용 Skype

응답 그룹 워크플로를 디자인하고 비즈니스용 Skype 서버 Enterprise Voice. 헌트 그룹 워크플로와 대화형 워크플로에 모두 설명되어 있습니다.

워크플로는 전화가 울리는 시간부터 누군가가 전화를 받는 시간까지의 호출 동작을 정의합니다. 워크플로는 통화 대기에 사용할 큐를 지정하고 헌트 그룹 워크플로에 사용할 라우팅 방법 또는 대화형 응답 그룹 워크플로에 사용할 질문과 대답을 지정합니다.

또한 워크플로는 시작 메시지, 대기 음악, 업무 시간, 휴일 등의 설정도 정의합니다.

> [!NOTE]
> 에이전트 그룹 및 큐를 먼저 만든 후에 해당 그룹과 큐를 사용하는 워크플로를 만들어야 합니다.

## <a name="creating-or-modifying-a-hunt-group-workflow"></a>헌트 그룹 워크플로 만들기 또는 수정

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>응답 그룹 구성 도구를 사용하여 헌트 그룹 워크플로를 만들거나 수정하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3. 왼쪽 탐색 모음에서 **응답 그룹** 을 클릭하고 **워크플로** 를 클릭합니다.

4. **워크플로** 페이지에서 **워크플로 만들기 또는 편집** 을 클릭합니다.

5. **서비스 선택** 검색 필드에 만들거나 변경할 워크플로를 호스팅하는 **ApplicationServer** 서비스의 이름 전부 또는 일부를 입력합니다. 서비스 결과 목록에서 원하는 서비스를 클릭하고 **확인** 을 클릭합니다.

    > [!NOTE]
    > 응답 그룹 구성 도구가 열립니다. /RgsConfig의 URL을 입력하여 웹 브라우저에서 직접 응답 https:// \<webPoolFqdn\> 열 수 있습니다.

6. 다음 중 하나를 수행합니다.

   - 새 **워크플로 만들기에서** 헌트 그룹 **옆의** 만들기를 **클릭합니다.**

   - **기존 워크플로 관리** 에서 변경할 워크플로를 찾은 다음 **동작** 에서 **편집** 을 클릭합니다.

7. 사용자가 워크플로를 호출할 준비가 되면 **워크플로 활성화** 를 선택합니다.

    > [!NOTE]
    >  관리되는 워크플로를 만드는 경우 워크플로 활성화 를 **선택해야 합니다.** 활성화된 관리 워크플로를 저장한 후에는 이 워크플로를 수정하고 비활성화할 수 있습니다.

8. 페더레이션 사용자가 그룹을 호출할 수 있도록 허용하려면 **페더레이션 사용** 확인란을 선택합니다. 또한 페더전을 사용하도록 구성된 응답 그룹 응용 프로그램에 적용되는 외부 액세스 정책도 있어야 합니다.

    > [!NOTE]
    > 전역 외부 액세스 정책은 응답 그룹 응용 프로그램에 적용됩니다. 비즈니스용 Skype 서버 제어판을 사용하거나 **Set-CsExternalAccessPolicy** cmdlet을 사용하여 EnableOutsideAccess 매개 변수를 True로 설정하여 응답 그룹 페더에 대한 글로벌 정책을 구성할 수 있습니다. 전역 정책 설정은 사이트 또는 사용자 정책이 할당되지 않은 모든 사용자에게 적용된다는 점에 유의하십시오. 따라서 응답 그룹에 대한 이 설정을 변경하기 전에 페더레이션 설정이 조직의 요구 사항을 충족하는지 확인해야 합니다. 사용자에게 정책이 적용되는 방식에 대한 자세한 내용은 [Manage External Access Policy for Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-manage-external-access-policy-for-your-organization)를 참조하십시오. 페더ation 설정에 대한 자세한 내용은 [Set-CsExternalAccessPolicy를 참조합니다.](/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps)

    > [!NOTE]
    > 비즈니스용 Skype Online에서 호스팅되는 사용자는온-프레미스 배포에서 호스트되는 응답 그룹에 전화를 걸 수 없습니다. 이는 비즈니스용 Skype 하이브리드 배포와 온라인 배포에서 모두 해당됩니다.

9. 통화하는 동안 에이전트의 ID를 숨기려면 **에이전트 익명성 사용** 확인란을 선택합니다.

    > [!NOTE]
    > 통화가 연결된 후 에이전트 또는 발신자가 IM(인스턴트 메시징) 및 비디오를 추가할 수 있지만 IM 또는 비디오로 익명 통화를 시작할 수는 없습니다. 익명 에이전트는 통화를 보류하고, 전송(무조건 전송 및 협의 전송)하고, 대기시킨 후 재개할 수도 있습니다. 익명 통화는 회의, 응용 프로그램 공유 및 데스크톱 공유, 파일 전송, 화이트보드 및 데이터 공동 작업, 통화 기록을 지원하지 않습니다. Lync VDI 플러그 인을 사용하는 에이전트는 수신 전화를 익명으로 받을 수 있지만 익명으로 발신 전화를 걸 수는 없습니다.

10. **전화를 받을 그룹의 주소를 입력하십시오** 에 워크플로 호출에 응답할 그룹의 기본 SIP URI(Uniform Resource Identifier) 주소를 입력합니다.

    > [!NOTE]
    > 워크플로의 기본 URI는 워크플로가 식별 및 참조되는 방식입니다. 입력하는 SIP URI는 Active Directory 도메인 서비스에서 연락처 개체로 만들어집니다. URI를 만들 경우 개체는 Active Directory에서 고유해야 합니다.

11. 표시 **이름에** 워크플로에 대해 표시할 이름(예: 영업 응답 그룹)을 입력합니다.

    > [!NOTE]
    > "<" 또는 ">" 문자를 표시 이름에 포함하지 마십시오. **RGS Presence Watcher** 또는 **RGS Presence Watcher** 는 예약되어 있으므로 표시 이름으로 사용할 수 없습니다.

12. **전화 번호** 에 응답 그룹의 줄 URI(예: +14255550165)를 입력합니다.

13. **표시 이름** 에 응답 그룹에 대해 표시할 번호(예: +1 (425) 555-0165)를 입력합니다.

14. (선택 사항) **설명에** 워크플로에 대한 설명을 워크플로의 연락처 카드에 표시하려는 경우 해당 워크플로에 대한 설명을 비즈니스용 Skype.

15. 이 워크플로를 응답 그룹 관리자를 통해 관리하려는 경우 **워크플로 유형** 에서 **관리** 를 선택합니다. 워크플로에 응답 그룹 관리자를 할당하기 위해 다음을 실행합니다.

    a. 이 워크플로의 관리자 SIP URI를 입력하고 **추가** 를 클릭합니다.

    b. 워크플로에 추가할 다른 관리자의 SIP URI를 입력하고 **추가** 를 클릭합니다.

    > [!IMPORTANT]
    > 응답 그룹의 관리자로 지정된 모든 사용자에게 CsResponseGroupManager 역할이 할당되어야 합니다. 이 역할이 할당되지 않은 사용자는 응답 그룹을 관리할 수 없습니다.

16. **2단계 언어 선택** 에서 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭합니다.

17. 환영 메시지를 구성하려면 **3단계 환영 메시지 구성** 아래에서 **환영 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행합니다.

    - 환영 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 환영 메시지를 입력합니다.

    > [!NOTE]
    > 입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.

    - 시작 메시지에 웨이브(.wav) 또는 Windows Media 오디오(.wma) 파일 녹음을 사용하려면 **녹음 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 오디오 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.

    > [!NOTE]
    > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원되는 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)을 참조하십시오.

18. **4단계 업무 시간 지정** 의 **표준 시간대** 에서 워크플로의 표준 시간대를 클릭합니다.

    > [!NOTE]
    > 표준 시간대는 워크플로의 발신자 및 에이전트가 거주하는 지역의 표준 시간대로서, 시작 및 종료 시간을 계산하는 데 사용됩니다. 예를 들어 북미 동부 표준 시간대를 사용하도록 워크플로가 구성되어 있고 오전 7시에 시작하여 오후 11시에 끝나도록 워크플로를 예약한 경우 시작 및 종료 시간은 각각 동부 표준시 7시와 동부 표준시 23시로 설정됩니다. 시간은 24시간 형식으로 입력해야 합니다.

19. 다음 중 하나를 수행하여 사용할 업무 시간 일정의 유형을 선택합니다.

    - 미리 정의된 업무 시간 일정을 사용하려면 **미리 설정된 일정 사용** 을 클릭한 다음 드롭다운 메뉴에서 사용할 일정을 선택합니다.

      > [!NOTE]
      > 이 옵션을 선택하려면 이전에 미리 설정된 일정이 하나 이상 있어야 합니다. **New-CSRgsHoursOfBusiness** cmdlet을 사용하여 미리 설정된 일정을 정의할 수 있습니다. 자세한 내용은 [(Optional) Define Response Group business hours in 비즈니스용 Skype.](optional-define-response-group-business-hours.md)

      > [!NOTE]
      > 미리 설정된 일정을 선택한 경우 응답 그룹을 사용할 수 있는 요일 및 시간으로 **요일**, **시작** 및 **종료** 가 자동으로 채워집니다.

    - 이 워크플로에만 적용되는 사용자 지정 일정을 사용하려면 **사용자 지정 일정 사용** 을 클릭합니다.

20. 이 워크플로에 대한 사용자 지정 일정을 만들려면 응답 그룹을 사용할 수 있는 요일 확인란을 클릭합니다.

21. 사용자 지정 일정을 만드는 경우  응답  그룹을 사용할 수 있는 각 주에 대한 열기 및 닫기 시간을 입력합니다.

    > [!NOTE]
    > **시작** 및 **종료** 시간은 24시간 형식이어야 합니다. 예를 들어 평일 오전 9시에서 오후 5시까지 근무하고 12시부터 점심 시간 동안 문을 닫는 경우 업무 시간은 **시작** 9:00, **종료** 12:00, **시작** 13:00 및 **종료** 17:00로 지정됩니다.

22. 근무하지 않는 동안 메시지를 재생하려면 **응답 그룹의 업무 시간이 지났을 때 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 메시지를 지정합니다.

    - 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.

      > [!NOTE]
      > 입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.

    - 메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.

      > [!NOTE]
      > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원되는 오디오 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)을 참조하십시오.

23. 메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).

    - 통화 연결을 끊으려면 **전화 끊기** 를 클릭합니다.

    - 통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환** 을 클릭하고 음성 메일 주소를 입력합니다. 음성 메일 주소의 형식은 다음과 *\<username\>* @ *\<domainName\>* 같습니다(예: bob@contoso.com.

    - 통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환** 을 클릭하고 사용자 주소를 입력합니다. 사용자 주소의 형식은 _\<username\>_ @ _\<domainName\>_ 입니다.

    - 통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환** 을 클릭하고 전화 번호를 입력합니다. 전화 번호 형식은 *\<number\>* @ *\<domainName\>* +14255550121@contoso.com. 도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.

24. **5단계 휴일 지정** 아래에서 응답 그룹이 근무하지 않는 요일을 정의하는 하나 이상의 휴일 집합에 대한 확인란을 클릭합니다.

    > [!NOTE]
    > 워크플로를 구성하기 전에 휴일 및 휴일 집합을 정의해야 합니다. **New-CsRgsHoliday** 및 **New-CsRgsHolidaySet** cmdlet을 사용하여 휴일 및 휴일 집합을 정의할 수 있습니다. 자세한 내용은 [(Optional) Define Response Group holiday sets in 비즈니스용 Skype.](optional-define-response-group-holiday-sets.md)

25. 휴일에 메시지를 재생하려면 **휴일에 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 재생할 메시지를 지정합니다.

    - 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.

    > [!NOTE]
    > 입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.

    - 메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.

      > [!NOTE]
      > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원되는 오디오 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)을 참조하십시오.

26. 메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).

    - 통화 연결을 끊으려면 **전화 끊기** 를 클릭합니다.

    - 통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환** 을 클릭하고 음성 메일 주소를 입력합니다. 음성 메일 주소의 형식은 다음과 *\<username\>* @ *\<domainName\>* 같습니다(예: bob@contoso.com.

    - 통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환** 을 클릭하고 사용자 주소를 입력합니다. 사용자 주소의 형식은 _\<username\>_ @ _\<domainName\>_ 입니다.

    - 통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환** 을 클릭하고 전화 번호를 입력합니다. 전화 번호 형식은 *\<number\>* @ *\<domainName\>* +14255550121@contoso.com. 도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.

27. **6단계 큐 구성** 의 **전화를 받을 큐 선택** 에서 에이전트가 사용 가능할 때까지 발신자를 대기 상태로 둘 큐를 선택합니다.

28. **7단계 대기 음악 구성** 에서 다음 중 하나를 수행하여 에이전트를 기다리는 동안 발신자에게 들려줄 음악을 선택합니다.

    - 기본 대기 음악 녹음을 사용하려면 **기본값 사용** 을 클릭합니다.

    - 대기 음악에 오디오 파일 녹음을 사용하려면 **음악 파일 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **음악 파일** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.

      > [!NOTE]
      > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원되는 오디오 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)을 참조하십시오.

29. **배포** 를 클릭합니다.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>관리 비즈니스용 Skype 서버 사용하여 헌트 그룹 워크플로를 만들거나 수정하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.

2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

3. 시작 메시지로 재생할 프롬프트를 작성하여 변수에 저장합니다. 명령줄에서 다음을 실행합니다.

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    예를 들면 다음과 같습니다.

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > 오디오 파일을 음성 안내에 사용하려면 **Import-CsRgsAudioFile** cmdlet을 사용합니다. 자세한 내용은 [Import-CsRgsAudioFile을 참조합니다.](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)

4. 통화가 이동될 해당 큐 또는 질문의 ID를 가져옵니다. 명령줄에서 다음을 실행합니다.

   ```powershell
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    큐를 만드는 데 대한 자세한 내용은 [New-CsRgsQueue를 참조합니다.](/powershell/module/skype/new-csrgsqueue?view=skype-ps)

5. 업무 시간 동안 워크플로를 열 때 수행할 기본 동작을 정의하여 변수에 저장합니다. 명령줄에서 다음을 실행합니다.

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > 헌트 그룹 워크플로의 경우 기본적으로 통화를 큐로 이동해야 합니다. 이 매개 변수는 활성 워크플로에 필요합니다. 비활성 워크플로에는 필요하지 않습니다.

    예를 들면 다음과 같습니다.

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. 업무 시간과 휴일을 정의하려는 경우 워크플로를 만들거나 수정하기 전에 정의해야 합니다. 자세한 내용은 [(Optional) Define Response Group business hours in 비즈니스용 Skype](optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in 비즈니스용 Skype.](optional-define-response-group-holiday-sets.md)

7. 업무 시간 외나 휴일에 받는 통화에 대한 프롬프트를 만들려면 **New-CsRgsPrompt** cmdlet을 사용하여 프롬프트를 정의하고 **New-CsRgsCallAction** 를 사용하여 프롬프트 후에 수행될 동작을 정의합니다. 자세한 내용은 [New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps) 및 [New-CsRgsCallAction을 참조합니다.](/powershell/module/skype/new-csrgscallaction?view=skype-ps)

8. Lync Server 응답 그룹 서비스의 서비스 이름을 검색하여 변수에 할당합니다. 명령줄에 다음을 실행합니다.

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. 워크플로를 만들거나 수정합니다. 워크플로를 만들려면 **New-CsRgsWorkflow** 를 사용하고, 워크플로를 수정하려면 **Set-CsRgsWorkflow** 를 사용합니다. 명령줄에 다음을 입력합니다.

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    예를 들면 다음과 같습니다.

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > 워크플로의 관리자로 지정된 모든 사용자에게 CsResponseGroupManager 역할을 할당해야 합니다.

     > [!NOTE]
     > 추가 선택적 매개 변수에 대한 자세한 내용은 [New-CsRgsWorkflow](/powershell/module/skype/new-csrgsworkflow?view=skype-ps) 또는 [Set-CsRgsWorkflow를 참조합니다.](/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

## <a name="designing-an-interactive-workflow"></a>대화형 워크플로 디자인

IVR(대화형 음성 응답)을 사용하여 발신자로부터 정보를 획득하고 통화를 적절한 큐로 안내할 수 있습니다. 질문 및 응답 쌍에 따라 사용할 큐가 결정됩니다. 발신자 응답에 따라 발신자에 대한 후속 질문을 듣거나 적절한 큐로 라우팅됩니다. IVR 질문과 발신자 응답은 전화를 수락하는 응답 에이전트에게 제공 하여 에이전트에게 중요한 정보를 제공합니다.

### <a name="overview-of-ivr-features"></a>IVR 기능 개요

응답 그룹 응용 프로그램은 26개 언어로 음성 인식 및 텍스트 음성 음성 입력 기능을 제공합니다. 텍스트 음성 또는 웨이브(.wav) 또는 미디어 오디오(.wma) 파일을 사용하여 IVR Windows 입력할 수 있습니다. 발신자는 음성 또는 DTMF(Dual-Tone Multifrequency) 응답을 사용하여 응답할 수 있습니다.

대화형 워크플로는 최대 두 가지 수준의 질문을 지원하며, 각 질문에는 최대 4개의 가능한 응답이 있습니다. IVR은 발신자에게 질문을 한 다음 발신자 응답에 따라 발신자 통화를 큐로 라우팅하거나 두 번째 질문을 합니다. 두 번째 질문 역시 가능한 응답은 4개입니다. 두 번째 수준의 질문에 대한 응답에 따라 적합한 큐로 발신자가 라우팅됩니다.

> [!NOTE]
> 관리 셸을 사용하여 통화 흐름을 비즈니스용 Skype 서버 IVR 질문 수준과 답변 수를 정의할 수 있습니다. 그러나 발신자 사용성을 위해 질문 수준이 3개 이상인 경우 각각 5개 이상의 답변을 사용하지 않는 것이 좋습니다. 또한 각각 4개 이상의 응답이 있는 두 개 이상의 질문 수준이 있는 통화 흐름을 디자인하는 경우 제어판을 사용하여 통화 흐름을 비즈니스용 Skype 서버 없습니다.

IVR 질문과 발신자 응답은 전화를 수락하는 응답 에이전트에게 제공됩니다.

### <a name="working-with-speech-technologies"></a>음성 기술 작업

음성 인식 및 텍스트 음성 음성 입력과 같은 음성 기술은 고객 환경을 향상하고 더 자연스럽고 효과적으로 정보에 액세스할 수 있도록 합니다. 그러나 음성 엔진에서 지정한 텍스트 또는 사용자 음성 응답이 올바르게 인식되지 않는 경우도 있습니다. 예를 들어 "#" 기호는 텍스트 음성 변환 엔진에서 "number"라는 단어로 변환됩니다. 이 문제는 다음을 통해 완화할 수 있습니다.

- 음성 엔진은 발신자 5명이 질문에 응답할 수 있는 시도를 제공합니다. 발신자에서 질문에 잘못 응답하거나(즉, 응답이 지정된 응답 중 하나에 해당되지 않은 경우) 또는 응답을 제공하지 않으면 발신자에 대해 다시 질문할 수 있는 기회가 주어지게 됩니다. 발신자 연결이 끊어지기 전에 5회 동안 질문에 응답을 시도합니다. 각 발신자 오류 후에 사용자 지정된 메시지를 재생하도록 IVR을 구성할 수 있습니다. 질문은 매번 반복됩니다.

- 음성 엔진에서 주변 잡음이 응답으로 해석될 가능성을 최소화하기 위해 더 긴 응답을 사용 합니다. 예를 들어 응답에는 두 개 이상의 음소리가 있으며 서로 크게 달라야 합니다.

- 질문에 음성 응답과 DTMF 응답이 모두 있는 경우 DTMF 응답이 아닌 개념을 나타내는 단어로 음성 응답을 구성합니다. 예를 들어 "누르거나 말하기"를 사용하는 대신 "1을 누르거나 대금 청구라고 말하세요."를 사용합니다.

- IVR을 디자인한 후 워크플로를 호출하고, 음성을 듣고, 음성을 사용하여 각 프롬프트에 응답하고, IVR 소리가 예상대로 실행되는지 확인할 수 있습니다. 그런 다음 IVR을 수정하여 해석 문제를 해결할 수 있습니다. 이전 예제에 따라 # 키를 참조해야 하는 경우 # 기호 대신 키 이름을 사용하여 IVR 프롬프트를 다시 덮어 사용할 수 있습니다. 예를 들어 "영업부에 대해 대화를 하다가 파운드 키를 누르고 있습니다."라는 예제가 있습니다.

### <a name="ivr-design-examples"></a>IVR 디자인 예제

다음 섹션에는 다양한 IVR 시나리오와 질문 및 응답 쌍의 예가 포함되어 있습니다.

#### <a name="ivr-with-one-level-of-questions"></a>한 가지 질문 수준이 있는 IVR

다음 예제에서는 한 가지 수준의 질문을 사용하는 IVR을 보여줍니다. 음성 인식을 사용하여 발신자 응답을 검색합니다.

 **질문:** "인사부에 전화 주셔서 감사합니다. 급여에게 말하고자 하는 경우 급여라고 말합니다. 그렇지 않으면 HR을 말하기를 원합니다."

- **옵션 1이 선택되어 있습니다.** 발신이 급여 팀으로 라우팅됩니다.

- **옵션 2가 선택되어 있습니다.** 발신 사람이 인사 팀으로 라우팅됩니다.

다음 그림에서는 통화 흐름을 보여줍니다.

 **한 수준 대화형 통화 흐름**

![대화형 음성 리포지티브를 사용하여 통화 흐름을 디자인합니다.](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a>두 가지 수준의 질문이 있는 IVR

다음 예제에서는 두 가지 수준의 질문을 사용하는 IVR을 보여줍니다. 발신자는 음성 또는 DTMF 키패드 입력을 사용하여 응답할 수 있습니다.

 **질문:** "IT 지원 센터에 문의해 주셔서 감사합니다. 네트워크 액세스 문제가 있는 경우 1을 누르거나 네트워크를 말하십시오. 소프트웨어 문제가 있는 경우 2를 누르거나 소프트웨어를 말하십시오. 하드웨어 문제가 있는 경우 3을 누르거나 하드웨어라고 말하십시오."

- **옵션 1이 선택되어 있습니다.** 발신이 네트워크 지원 팀으로 라우팅됩니다.

- **옵션 2가 선택되어 있습니다.** 발신자에 대한 후속 질문을 묻는 질문이 나타날 수 있습니다.

    **질문:** "운영 체제 문제인 경우 1을 누르거나 운영 체제를 말하십시오. 내부 응용 프로그램에 문제가 있는 경우 2를 누르거나 내부 응용 프로그램을 말하십시오. 그렇지 않으면 3을 누르거나 다른 말로 말해야 합니다."

  - **옵션 1이 선택되어 있습니다.** 발신이 운영 체제 지원 팀으로 라우팅됩니다.

  - **옵션 2가 선택되어 있습니다.** 발신이 내부 응용 프로그램 지원 팀으로 라우팅됩니다.

  - **옵션 3이 선택되어 있습니다.** 발신자 통화가 소프트웨어 지원 팀으로 라우팅됩니다.

- **옵션 3이 선택되어 있습니다.** 발신자에 대한 후속 질문을 묻는 질문이 나타날 수 있습니다.

    **질문:** "프린터 문제인 경우 1을 누르십시오. 그렇지 않으면 2를 누르고 있습니다."

  - **옵션 1이 선택되어 있습니다.** 발신자 통화가 프린터 지원 팀으로 라우팅됩니다.

  - **옵션 2가 선택되어 있습니다.** 발신이 하드웨어 지원 팀으로 라우팅됩니다.

다음 그림에서는 통화 흐름을 보여줍니다.

 **두 수준 대화형 통화 흐름**

![대화형 음성 리포지티브를 사용하여 통화 흐름을 디자인합니다.](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a>모범 사례

다음 목록에서는 IVR을 디자인하기 위한 몇 가지 모범 사례를 제공합니다.

- 발신자에 작업을 신속하게 수행하게 합니다. IVR에 너무 많은 정보나 긴 마케팅 메시지를 제공하지 않도록 합니다.

- 긴 메시지를 포함하려는 경우 환영 메시지 대신 첫 번째 질문에 추가하는 것이 좋습니다. 첫 번째 질문의 일부인 경우 발신자는 질문에 응답하여 메시지를 무시할 수 있지만 환영 메시지를 무시할 수는 없습니다.

- 발신자 언어로 말하기 길게 언어를 피합니다. 자연스럽게 말하기

- 효율적이고 효과적인 프롬프트를 작성합니다. 불필요한 옵션을 제거합니다. 발신자 예상 응답이 문장의 끝에 있도록 정보를 구조화합니다. 예를 들어 "영업 팀에 말하기 위해 1을 누르고 있습니다."

- 음성 응답을 사용자에게 친숙하게 만들어야 합니다. 예를 들어 DTMF와 음성 응답을 모두 지정하는 경우 "영업 팀에 말하기 위해 1을 누르거나 영업에 대해 말하기"를 지정합니다.

- 조직에 배포하기 전에 사용자 그룹에서 IVR을 테스트합니다.

## <a name="creating-or-modifying-an-interactive-workflow"></a>대화형 워크플로 만들기 또는 수정

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>응답 그룹 구성 도구를 사용하여 대화형 워크플로를 만들거나 수정하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3. 왼쪽 탐색 모음에서 **응답 그룹** 을 클릭하고 **워크플로** 를 클릭합니다.

4. **워크플로** 페이지에서 **워크플로 만들기 또는 편집** 을 클릭합니다.

5. **서비스 선택** 검색 필드에 만들거나 수정할 워크플로를 호스팅하는 **ApplicationServer** 서비스의 이름 일부나 전체를 입력하고 결과 서비스 목록에서 원하는 서비스를 클릭한 후 **확인** 을 클릭합니다.

    > [!NOTE]
    > 응답 그룹 구성 도구가 열립니다. /RgsConfig의 URL을 입력하여 웹 브라우저에서 직접 응답 https:// \<webPoolFqdn\> 열 수 있습니다.

6. 다음 중 하나를 수행합니다.

   - **새 워크플로 만들기** 아래에서 **대화형** 옆에 있는 **만들기** 를 클릭합니다.

   - **기존 워크플로 관리** 에서 변경할 워크플로를 찾은 다음 **동작** 에서 **편집** 을 클릭합니다.

7. 사용자가 워크플로 호출을 시작할 수 있도록 준비되지 않은 경우 **워크플로 활성화** 확인란의 선택을 취소합니다.

    > [!NOTE]
    >  관리되는 워크플로를 만드는 경우 워크플로 활성화 를 **선택해야 합니다.** 활성화된 관리 워크플로를 저장한 후에는 이 워크플로를 수정하고 비활성화할 수 있습니다.

8. 페더레이션 사용자가 그룹을 호출할 수 있도록 허용하려면 **페더레이션 사용** 확인란을 선택합니다. 또한 페더전을 사용하도록 구성된 응답 그룹 응용 프로그램에 적용되는 외부 액세스 정책도 있어야 합니다.

    > [!NOTE]
    > 전역 외부 액세스 정책은 응답 그룹 응용 프로그램에 적용됩니다. 비즈니스용 Skype 서버 제어판을 사용하거나 **Set-CsExternalAccessPolicy** cmdlet을 사용하여 EnableOutsideAccess 매개 변수를 True로 설정하여 응답 그룹 페더에 대한 글로벌 정책을 구성할 수 있습니다. 전역 정책 설정은 사이트 또는 사용자 정책이 할당되지 않은 모든 사용자에게 적용된다는 점에 유의하십시오. 따라서 응답 그룹에 대한 이 설정을 변경하기 전에 페더레이션 설정이 조직의 요구 사항을 충족하는지 확인해야 합니다. 사용자에게 정책이 적용되는 방식에 대한 자세한 내용은 [Manage External Access Policy for Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-manage-external-access-policy-for-your-organization)를 참조하십시오. 페더ation 설정에 대한 자세한 내용은 설명서에서 **Set-CsExternalAccessPolicy를** 참조하십시오.

    > [!NOTE]
    > 비즈니스용 Skype Online에서 호스팅되는 사용자는온-프레미스 배포에서 호스트되는 응답 그룹에 전화를 걸 수 없습니다. 이는 비즈니스용 Skype 하이브리드 배포와 온라인 배포에서 모두 해당됩니다.

9. 통화하는 동안 에이전트의 ID를 숨기려면 **에이전트 익명성 사용** 확인란을 선택합니다.

    > [!NOTE]
    > 통화가 연결된 후 에이전트 또는 발신자가 IM(인스턴트 메시징) 및 비디오를 추가할 수 있지만 IM 또는 비디오로 익명 통화를 시작할 수는 없습니다. 익명 에이전트는 통화를 보류하고, 전송(무조건 전송 및 협의 전송)하고, 대기시킨 후 재개할 수도 있습니다. 익명 통화는 회의, 응용 프로그램 공유 및 데스크톱 공유, 파일 전송, 화이트보드 및 데이터 공동 작업, 통화 기록을 지원하지 않습니다. Lync VDI 플러그 인을 사용하는 에이전트는 수신 전화를 익명으로 받을 수 있지만 익명으로 발신 전화를 걸 수는 없습니다.

10. **전화를 받을 그룹의 주소를 입력하십시오** 에 워크플로 호출에 응답할 그룹의 SIP URI(Uniform Resource Identifier) 주소를 입력합니다.

11. **표시 이름** 에 클라이언트에서 워크플로에 대해 표시하도록 할 이름(예: Sales IVR Response Group)을 입력합니다.

    > [!NOTE]
    > 표시 이름에 " \<" or "\> " 문자를 포함하지 않습니다. **RGS Presence Watcher** 또는 **RGS Presence Watcher** 는 예약되어 있으므로 표시 이름으로 사용할 수 없습니다.

12. **전화 번호** 에 응답 그룹의 줄 URI(예: +14255550165)를 입력합니다.

13. **표시 이름** 에 응답 그룹에 대해 표시할 번호(예: +1 (425) 555-0165)를 입력합니다.

14. (선택 사항) **설명에** 연락처 카드에 표시하려는 워크플로에 대한 설명을 비즈니스용 Skype.

15. 이 워크플로를 응답 그룹 관리자를 통해 관리하려는 경우 **워크플로 유형** 에서 **관리** 를 선택합니다. 워크플로에 응답 그룹 관리자를 할당하기 위해 다음을 실행합니다.

    a. 이 워크플로의 관리자 SIP URI를 입력하고 **추가** 를 클릭합니다.

    b. 워크플로에 추가할 다른 관리자의 SIP URI를 입력하고 **추가** 를 클릭합니다.

    > [!IMPORTANT]
    > 응답 그룹의 관리자로 지정된 모든 사용자는 CsResponseGroupManager 역할이 할당되어야 합니다. 이 역할이 할당되지 않은 사용자는 응답 그룹을 관리할 수 없습니다.

16. **2단계 언어 선택** 아래에서 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭합니다.

17. 환영 메시지를 구성하려면 **3단계 환영 메시지 구성** 아래에서 **환영 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행합니다.

    - 환영 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 환영 메시지를 입력합니다.

    > [!NOTE]
    > 입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.

    - 환영 메시지에 웨이브 또는 Windows Media 오디오 파일 녹음을 사용하려면 **녹음 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 오디오 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.

    > [!NOTE]
    > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원되는 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)을 참조하십시오.

18. **4단계 업무 시간 지정** 아래에 있는 **표준 시간대** 상자에서 워크플로의 표준 시간대를 클릭합니다.

    > [!NOTE]
    > 표준 시간대는 워크플로의 발신자 및 에이전트가 거주하는 지역의 표준 시간대로서, 시작 및 종료 시간을 계산하는 데 사용됩니다. 예를 들어 북미 동부 표준 시간대를 사용하도록 워크플로가 구성되어 있고 오전 7시에 시작하여 오전 11:00:00시에 끝나도록 워크플로를 예약한 경우 시작 및 종료 시간은 각각 동부 표준시 7시와 동부 표준시 23시로 설정됩니다. 시간은 24시간 형식으로 입력해야 합니다.

19. 다음 중 하나를 수행하여 사용할 업무 시간 일정의 유형을 선택합니다.

    - 미리 정의된 업무 시간 일정을 사용하려면 **미리 설정된 일정 사용** 을 클릭한 다음 드롭다운 메뉴에서 사용할 일정을 선택합니다.

      > [!NOTE]
      > 이 옵션을 선택하려면 이전에 미리 설정된 일정이 하나 이상 있어야 합니다. **New-CsRgsHoursOfBusiness** cmdlet을 사용하여 미리 설정한 일정을 정의합니다. 자세한 내용은 [(Optional) Define Response Group business hours in 비즈니스용 Skype.](optional-define-response-group-business-hours.md) 미리 설정된 일정을 선택한 경우 응답 그룹을 사용할 수 있는 요일 및 시간으로 **요일**, **시작** 및 **종료** 가 자동으로 채워집니다.

    - 이 워크플로에만 적용되는 사용자 지정 일정을 사용하려면 **사용자 지정 일정 사용** 을 클릭합니다.

20. 이 워크플로에 대한 사용자 지정 일정을 만들려면 응답 그룹을 사용할 수 있는 요일 확인란을 클릭합니다.

21. 사용자 지정 일정을 만드는 경우  응답  그룹을 사용할 수 있는 열기 및 종료 시간을 입력합니다.

     > [!NOTE]
     > **시작** 및 **종료** 시간은 24시간 형식이어야 합니다. 예를 들어 평일 오전 9시에서 오후 5시까지 근무하고 12시부터 점심 시간 동안 문을 닫는 경우 업무 시간은 **시작** 9:00, **종료** 12:00, **시작** 13:00 및 **종료** 17:00로 지정됩니다.

22. 근무하지 않는 동안 메시지를 재생하려면 **응답 그룹의 업무 시간이 지났을 때 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 메시지를 지정합니다.

    - 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.

      > [!NOTE]
      > 입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.

    - 메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.

    > [!NOTE]
    > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원되는 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)을 참조하십시오.

23. 메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).

    - 통화 연결을 끊으려면 **전화 끊기** 를 클릭합니다.

    - 통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환** 을 클릭하고 음성 메일 주소를 입력합니다. 음성 메일 주소의 형식은 다음과 *\<username\>* @ *\<domainname\>* 같습니다(예: bob@contoso.com.

    - 통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환** 을 클릭하고 사용자 주소를 입력합니다. 사용자 주소의 형식은 _\<username\>_ @ _\<domainname\>_ 입니다.

    - 통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환** 을 클릭하고 전화 번호를 입력합니다. 전화 번호 형식은 *\<number\>* @ *\<domainname\>* +14255550121@contoso.com. 도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.

24. **5단계 휴일 지정** 아래에서 응답 그룹이 근무하지 않는 요일을 정의하는 하나 이상의 휴일 집합에 대한 확인란을 클릭합니다.

    > [!NOTE]
    > 워크플로를 구성하기 전에 휴일 및 휴일 집합을 정의해야 합니다. **New-CsRgsHoliday** 및 **New-CsRgsHolidaySet** cmdlet을 사용하여 휴일 및 휴일 집합을 정의할 수 있습니다. 자세한 내용은 [(Optional) Define Response Group holiday sets in 비즈니스용 Skype.](optional-define-response-group-holiday-sets.md)

25. 휴일에 메시지를 재생하려면 **휴일에 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 재생할 메시지를 지정합니다.

    - 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.

      > [!NOTE]
      > 입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.

    - 메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.

      > [!NOTE]
      > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원되는 오디오 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)을 참조하십시오.

26. 메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).

    - 통화 연결을 끊으려면 **전화 끊기** 를 클릭합니다.

    - 통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환** 을 클릭하고 음성 메일 주소를 입력합니다. 음성 메일 주소의 형식은 다음과 *\<username\>* @ *\<domainname\>* 같습니다(예: bob@contoso.com.

    - 통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환** 을 클릭하고 사용자 주소를 입력합니다. 사용자 주소의 형식은 _\<username\>_ @ _\<domainname\>_ 입니다.

    - 통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환** 을 클릭하고 전화 번호를 입력합니다. 전화 번호 형식은 *\<number\>* @ *\<domainname\>* +14255550121@contoso.com. 도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.

27. **6단계 대기 음악 구성** 아래에서 다음 중 하나를 수행하여 에이전트를 기다리는 동안 발신자에게 들려줄 음악을 선택합니다.

    - 기본 대기 음악 녹음을 사용하려면 **기본값 사용** 을 클릭합니다.

    - 오디오 파일 녹음을 대기 음악에 사용하려면 **음악 파일 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **음악 파일** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.

    > [!NOTE]
    > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원되는 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)을 참조하십시오.

28. **7단계 대화형 음성 응답 구성** 의 **사용자에게 다음 텍스트 또는 녹음된 메시지가 재생됩니다** 머리글 아래에서 다음과 같이 발신자에게 제공할 질문을 지정합니다.

    - 질문을 텍스트 형식으로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 질문을 입력합니다.

    > [!NOTE]
    > 입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.

    > [!NOTE]
    > "#" 기호는 텍스트 음성 변환 엔진에서 "숫자"라는 단어로 변환합니다. # 키를 참조해야 하는 경우 프롬프트에 기호 대신 키 이름을 사용해야 합니다. 예를 들어 "영업부에 대해 대화를 하다가 파운드 키를 누르고 있습니다."라는 예제가 있습니다.

    - 질문이 포함된 미리 녹음된 오디오 파일을 사용하려면 녹음 선택 을  클릭한 다음 녹음 링크를 클릭하여 파일을 업로드합니다. 새 브라우저 창에서 찾아보기를 클릭하고 오디오 파일을 선택한 다음 열기 를 **클릭합니다.** 업로드  클릭하여 파일을 로드한 다음 선택적으로 텍스트 상자에 질문을 입력할 수 있습니다(이렇게 하면 질문과 발신자 응답이 응답 에이전트로 전달될 수 있습니다).

      > [!NOTE]
      > 모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다. 지원되는 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)을 참조하십시오.

29. **응답 1** 아래에서 다음을 수행하여 질문에 대한 첫 번째 가능한 응답을 지정합니다.

    > [!IMPORTANT]
    > 음성 응답에 따옴표(")를 사용하지 마십시오. 따옴표를 사용하면 IVR에 실패합니다.

    > [!NOTE]
    > 발신자가 음성과 영숫자 키패드 입력 중 하나 또는 둘 다를 사용하여 응답하도록 허용할 수 있습니다.

    - 발신자가 음성을 사용하여 응답하도록 하려면 **음성 응답 입력** 상자에 응답을 입력합니다.

    - 발신자가 키패드의 키를 눌러 응답하도록 하려면 **숫자** 상자에서 키패드 숫자를 클릭합니다.

30. 다음과 같이 발신자를 큐로 라우팅할지 또는 다른 질문을 제공할지 지정합니다.

    - 발신자를 큐로 라우팅하려면 **큐로 보내기** 를 클릭한 다음 **큐 선택** 에서 사용할 큐를 클릭합니다.

    - 다른 질문을 제공하려면 **또 다른 질문하기** 를 클릭한 다음 **텍스트 음성 변환 사용** 을 클릭하고 질문을 입력하거나 **녹음 선택** 을 클릭합니다. 이 섹션의 응답 그룹을 사용하여 추가 질문에 가능한 최대 4개의 응답 및 각 응답에 사용할 큐를 지정할 수 있습니다. 세 번째 또는 네 번째 가능한 응답을 지정하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭합니다.

31. 28단계와 29단계를 반복하여 원래 질문에 가능한 최대 3개의 응답을 추가로 지정하여 가능한 응답 및 각 응답에 대해 수행할 작업을 지정합니다. 세 번째 또는 네 번째 가능한 응답을 지정하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭합니다.

32. **배포** 를 클릭합니다.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>관리 비즈니스용 Skype 서버 셸을 사용하여 대화형 워크플로를 만들거나 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.

2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

3. 응답 그룹 서비스의 서비스 이름을 검색하여 변수 하나에 할당합니다. 명령줄에서 다음을 실행합니다.

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. 대화형 워크플로를 만들려면 두 개 이상의 큐와 두 개 이상의 에이전트 그룹이 필요합니다. 먼저 다음을 실행하여 에이전트 그룹을 만듭니다.

   ```powershell
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. 다음을 실행하여 큐를 만듭니다.

   ```powershell
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. 다음을 실행하여 첫 번째 응답 그룹 프롬프트를 만듭니다.

   ```powershell
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. 그런 다음 프롬프트 후에 수행할 동작을 만듭니다. 다음을 실행합니다.

   ```powershell
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. 다음을 실행하여 첫 번째 응답 그룹 답변을 만듭니다.

   ```powershell
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. 이제 두 번째 프롬프트, 호출 동작 및 답변을 만듭니다. 먼저 다음을 실행하여 프롬프트를 만듭니다.

   ```powershell
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. 다음을 실행하여 큐를 만듭니다.

    ```powershell
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. 다음을 실행하여 두 번째 응답 그룹 답변을 만듭니다.

    ```powershell
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. 다음을 실행하여 최상위 프롬프트를 만듭니다.

    ```powershell
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. 다음을 실행하여 최상위 질문을 만듭니다.

    ```powershell
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. 이제 다음을 실행하여 워크플로를 만듭니다.

    ```powershell
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > 응답 그룹의 관리자로 지정된 모든 사용자에게 CsResponseGroupManager 역할이 할당되어야 합니다. 이 역할이 할당되지 않은 사용자는 응답 그룹을 관리할 수 없습니다.

## <a name="see-also"></a>참고 항목

[(선택 사항) 다음의 응답 그룹 휴일 집합 비즈니스용 Skype](optional-define-response-group-holiday-sets.md)

[(선택 사항) 다음의 경우 응답 그룹 업무 시간을 비즈니스용 Skype](optional-define-response-group-business-hours.md)

[New-CsRgsWorkflow](/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[Set-CsRgsWorkflow](/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)