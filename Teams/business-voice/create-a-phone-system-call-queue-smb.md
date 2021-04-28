---
title: Microsoft Teams에서 호출 큐 만들기 - 중소기업 자습서
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: Microsoft 365 Business Voice를 사용하여 통화 큐를 설정하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: c7533227796fb9ae9357590993a9065dc01d5030
ms.sourcegitcommit: 03ff569a0b7a8e04d7b0ab32f370a9a537fa7fe7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2021
ms.locfileid: "52064824"
---
# <a name="create-a-call-queue---small-business-tutorial"></a>통화 큐 만들기 - 중소기업 자습서

통화 큐는 특정 문제나 질문에 대한 도움을 줄 수 있는 조직의 사용자에게 통화를 걸 수 있는 방법을 제공합니다. 호출은 큐의 사용자(*에이전트* 라고 함)에게 한 번에 하나씩 배포됩니다. 

통화 큐는 다음을 제공합니다.

- 인사말 메시지

- 큐에서 대기 중인 음악

- 에이전트에 대한 *FIFO(선입선출)* 순서 통화 라우팅.

- 큐 오버플로 및 시간 제한에 대한 처리 옵션

#### <a name="video-demonstration"></a>비디오 데모

이 비디오에서는 Teams에서 호출 큐를 만드는 방법을 보여 주었다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

#### <a name="before-you-begin"></a>시작하기 전에

일부 [전화 시스템 - 아직](../teams-add-on-licensing/virtual-user.md) 없는 경우 가상 사용자 라이선스를 얻습니다. 설정할 각 호출 큐 및 자동 참석자에 대해 하나를 얻습니다. 이러한 라이선스는 무료이기 때문에 향후 설정을 변경하기로 결정한 경우 몇 가지 추가를 제안합니다.

통화 큐의 에이전트가 전화 접속하여 고객 통화를 반환할 수 있습니다. 통화 에이전트의 발신자 ID를 주 전화 번호 또는 적절한 자동 참석자 수로 설정하는 것이 고려됩니다. 자세한 내용은 [Microsoft Teams에서 발신자 ID 정책 관리](../caller-id-policies.md)를 참조하세요.

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a>다음 단계에 따라 통화 큐를 설정합니다.

# <a name="step-1brcreate-a-team"></a>[1단계 <br> 팀 만들기](#tab/create-team)

호출 큐를 만들 때 큐에 개별 사용자를 추가하거나 기존 보안 그룹, Microsoft 365 그룹 또는 Microsoft Teams 팀을 사용할 수 있습니다. 팀 채널을 [사용하는 것이 좋습니다.](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e) 이렇게 하면 큐의 구성원이 서로 채팅하고, 아이디어를 공유하고, 문서 또는 기타 리소스를 만들어 고객에게 도움을 줄 수 있습니다. 또한 팀은 발신자들이 몇 시간 후에 메시지를 남기거나 큐가 최대 용량에 도달하는 경우 음성 사서함을 제공합니다.

팀 만들기

1. 먼저 앱의 왼쪽에서 **Teams를** 클릭한  다음 참가를 클릭하거나 팀 목록 맨 아래에 있는 팀 만들기를 클릭합니다.

2. 그런 다음 **팀 만들기(첫** 번째 카드, 왼쪽 위 모서리)를 클릭합니다.

3. 처음부터 **팀 빌드를 선택 합니다.**

4. 다음으로 공용 팀 또는 개인 팀을 원하는지 여부를 선택합니다. 팀에  가입하여 사람들이 의도치 않은 큐에 참여하지 않도록 통화 큐에 개인을 추천합니다.

5. 팀 이름을 지정하고 선택적 설명을 추가합니다.

6. 완료되면 만들기를 **클릭합니다.**

8. 통화 큐에 하려는 사용자 이름을 입력한 다음 추가를 **클릭합니다.**

9. 닫기 **를 클릭합니다.** 팀에 추가한 사람들은 이제 팀 구성원이 됐고 팀이 팀 목록에 표시됩니다는 전자 메일을 받게 됩니다.

다음으로 통화 큐에 사용할 채널을 추가합니다.

채널을 추가하는 경우

1. Teams에서 방금 만든 팀을  찾고 추가 옵션(...)을 클릭한 다음 채널 **추가를 클릭합니다.**

2. 채널의 이름 및 설명을 입력한 다음 추가를 **클릭합니다.**

> [!div class="nextstepaction"]
> [2단계 - 리소스 계정 >](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[2단계 <br> 리소스 계정](#tab/resource-account)

만드는 각 호출 큐에는 리소스 계정이 필요합니다. 이는 계정이 사용자 대신 자동 참석자 또는 통화 큐와 연결되어 있는 것을 제외하고 사용자 계정과 유사합니다. 이 단계에서는 계정을 만들고 *Microsoft 365 Phone System - Virtual User* 라이선스를 할당한 다음, 이 라이선스를 사용하여 통화 큐 만들기를 시작할 수 있습니다.

### <a name="create-a-resource-account"></a>리소스 계정 만들기

Teams 관리 센터에서 리소스 계정을 만들 수 있습니다.

1. Teams 관리 센터에서 **Org-wide** 설정을 확장한 다음 **리소스 계정을 클릭합니다.**

2. **추가** 를 클릭합니다.

3. 리소스 계정 **추가** 창에서 표시 **이름,** **사용자** 이름 및 를 입력하고 리소스 계정 유형에 **대한** 호출 **큐를 선택하세요.** 에이전트는 큐에서 들어오는 호출을 수신할 때 표시 이름이 표시됩니다.

    ![리소스 계정 사용자 인터페이스 추가 스크린샷](../media/resource-account-add-cq.png)

4. **저장** 을 클릭합니다.

   새 계정이 계정 목록에 표시됩니다.

   ![리소스 계정 목록 스크린샷](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>라이선스 할당

*Microsoft 365 Phone System - 가상 사용자* 라이선스를 리소스 계정에 할당해야 합니다.

1. Microsoft 365 관리 센터의 **활성** 사용자 목록에서 라이선스를 할당할 리소스 계정을 클릭합니다.

2. 라이선스 **및** 앱 탭의 라이선스 **아래에서** **Microsoft 365 Phone System - Virtual User 를 선택합니다.**

3. 변경 **내용 저장 을 클릭합니다.**

    ![Microsoft 365 관리 센터에서 라이선스 사용자 인터페이스 할당 스크린샷](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a>통화 큐 만들기

다음으로 새 호출 큐를 만들고 리소스 계정을 할당합니다.

1. Teams 관리 센터에서 **음성을** 확장하고 큐 호출을 **클릭한** 다음 **추가를 클릭합니다.**

1. 통화 큐의 이름을 입력합니다.

2. **계정 추가** 를 클릭하고 이 통화 큐에 사용할 리소스 계정을 검색하고 **추가** 를 클릭하고 **추가** 를 클릭합니다.

3. 언어를 선택합니다. 이 언어는 시스템에서 생성된 음성 프롬프트 및 음성 메시지(사용하도록 설정한 경우)에 사용됩니다.

    ![리소스 계정 및 언어 설정 스크린샷](../media/call-queue-name-language.png)

4. 발신자가 큐에 도착하면 발신자들에게 인사말을 재생할지 지정합니다. 재생하려는 인사말이 포함된 MP3, WAV 또는 WMA 파일을 업로드해야 합니다.

5. Teams에서 사용자가 큐에 있는 동안 발신자에게 기본 음악이 제공됩니다. 특정 오디오 파일을 재생하려면 **오디오 파일 재생** 을 선택하고 MP3 WAV 또는 WMA 파일을 업로드합니다.

   > [!NOTE]
   > 업로드된 녹음/녹화의 크기는 5MB 이상일 수 없습니다.
   > Teams 통화 큐에서 제공하는 기본 음악은 조직에서 지불해야 하는 로열티가 없습니다. 

> [!div class="nextstepaction"]
> [3단계 - 에이전트 호출 >](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[3단계 <br> 에이전트 호출](#tab/call-agents)

에이전트를 호출 큐에 추가하기 위해 앞에서 만든 팀 및 채널에 에이전트를 추가합니다.

1. 팀 선택 **옵션을 선택하고** 채널 **추가를 클릭합니다.**
2. 만든 팀의 이름을 입력하고, 선택한 다음 **추가를 클릭합니다.**
3. 큐에 대해 만든 채널을 선택합니다.
3. 적용 **을 클릭합니다.**

    ![통화 큐에 대한 사용자 및 그룹 설정의 스크린샷](../media/call-queue-users-groups.png)

> [!NOTE]
> 새 사용자가 팀에 추가될 때 첫 번째 통화가 도착하는 데 최대 8시간이 걸릴 수 있습니다.

> [!div class="nextstepaction"]
> [4단계 - 리소스 계정 >](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[4단계 <br> 라우팅 호출](#tab/call-routing)

사용할 호출 라우팅 메서드를 선택하십시오.

1. 회의 **모드를 자동으로** **설정합니다.**

2. 사용할 **라우팅** 방법을 선택하십시오. 그러면 에이전트가 큐에서 호출을 받는 순서가 결정됩니다. 직렬  라우팅 또는 **라운드 로빈을 추천합니다.** 다음 옵션 중에서 선택합니다.

    - **참석자 라우팅** 은 큐에 있는 모든 에이전트를 동시에 링합니다. 통화를 받은 첫 번째 통화 에이전트가 통화를 받습니다.

    - **직렬 라우팅은** 모든 호출 에이전트를 하나씩 링합니다. 에이전트가 통화를 취소하거나 통화를 받지 않으면 다음 에이전트가 호출을 울리고 선택되거나 시간이 초과될 때까지 모든 에이전트를 시도합니다.

    - **라운드 로빈** 은 각 호출 에이전트가 큐에서 동일한 수의 호출을 수신하도록 수신 호출 라우팅의 균형을 조정합니다. 이는 모든 상담원 간에 동등한 기회를 보장하기 위해 인바운드 영업 환경에서 바람직할 수 있습니다.

    - **가장 긴 유휴 상태** 는 각 통화를 가장 오랫동안 유휴 상태인 에이전트로 라우팅합니다. (현재 상태 상태가 10분 이상 멀어진 에이전트는 포함되지 않습니다.)

    ![회의 모드 및 라우팅 방법 설정 스크린샷](../media/call-queue-conference-mode-routing-method.png)

3. 현재 **상태 기반 라우팅을 설정합니다.** 이 경로는 현재 상태를 사용할 수 있는 에이전트에 **호출합니다.**

4. 에이전트가 통화를 옵트아웃할 수 있도록 허용할지 선택하십시오.

5. 에이전트 **경고** 시간을 설정하여 큐에서 호출을 다음 에이전트로 리디렉션하기 전에 에이전트의 전화가 울리는 시간을 지정합니다.

    ![라우팅, 옵트아웃 및 알림 시간 설정 스크린샷](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [5단계 - 오버플로 >](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[5단계 <br> 오버플로 호출](#tab/call-overflow)

큐의 최대값을 초과하는 호출을 처리하는 방법을 선택해야 합니다.

1. 큐에서 **최대 호출을 설정합니다.**

2. 최대 호출 수에 도달하면 할 작업을 선택해야 합니다. 통화 연결을 끊거나 리디렉션할 수 있습니다. 호출을 다음 대상 중 하나로 리디렉션하는 것이 좋습니다.
    - **조직의 사람** - 음성 통화를 받을 수 있는 조직의 사용자
    - **음성 앱** - 자동 참석자 또는 다른 통화 큐입니다. (이 대상을 선택할 때 자동 참석자 또는 호출 큐와 연결된 리소스 계정을 선택하세요.)
    - **외부 전화 번호** - 모든 전화 번호입니다. 이 형식 사용: +[국가 코드][지역 코드][전화 번호]
    - **음성 메일** - 만든 팀의 음성 사서함을 사용할 수 있습니다.

    ![통화 오버플로 설정 스크린샷](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [6단계 - 통화 시간 제한 >](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[6단계 <br> 통화 시간 제한](#tab/call-timeout)

큐에서 호출이 너무 오래 대기 중일 때 어떤 일이 일어날지 선택해야 합니다.

1. 최대 **대기 시간 을 설정합니다.**

2. 통화 시간 외의 경우 할 작업을 선택해야 합니다. 통화 연결을 끊거나 리디렉션할 수 있습니다. 호출을 다음 대상 중 하나로 리디렉션하는 것이 좋습니다.
    - **조직의 사람** - 음성 통화를 받을 수 있는 조직의 사용자
    - **음성 앱** - 자동 참석자 또는 다른 통화 큐입니다. (이 대상을 선택할 때 자동 참석자 또는 호출 큐와 연결된 리소스 계정을 선택하세요.)
    - **외부 전화 번호** - 모든 전화 번호입니다. 이 형식 사용: +[국가 코드][지역 코드][전화 번호]
    - **음성 메일** - 만든 팀의 음성 사서함을 사용할 수 있습니다.

    ![통화 오버플로 설정 스크린샷](../media/call-queue-timeout-handling.png)

3. **저장** 을 클릭합니다.

그러면 호출 큐의 설정이 완료됩니다. 다음으로 자동 참석자 [를 설정할 수 있습니다.](create-a-phone-system-auto-attendant-smb.md)

---

