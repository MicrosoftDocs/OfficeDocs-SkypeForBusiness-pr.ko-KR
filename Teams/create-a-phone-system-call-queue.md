---
title: Microsoft Teams에서 통화 큐 만들기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
- seo-marvel-apr2020
description: 인사말 메시지를 제공하고, 음악, 통화 리디렉션 및 기타 기능을 제공하는 Microsoft Teams를 사용하여 통화 큐에 전화 시스템을 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: 0253fb15a8672d83e672e3e3e18f8455d292214c
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145895"
---
# <a name="create-a-call-queue"></a>통화 큐 만들기

통화 큐는 특정 문제 또는 질문에 도움을 줄 수 있는 조직의 사용자에게 발신자 라우팅 방법을 제공합니다. 호출은 큐에 있는 사람(에이전트라고도 하는)에게 한 번씩 *배포됩니다.* 

호출 큐는 다음을 제공합니다.

- 인사말 메시지입니다.

- 음악 대기 중인 동안 대기합니다.

- 호출 라우팅(FIFO(First *In, First Out)* 순서로 에이전트에 라우팅합니다.

- 큐 오버플로 및 시간 제한에 대한 처리 옵션입니다.

이 문서의 절차를 수행하기 전에 [Teams](plan-auto-attendant-call-queue.md) 자동 전화 회의 [](plan-auto-attendant-call-queue.md#getting-started) 및 통화 큐에 대한 계획을 읽고 시작 단계를 수행해야 합니다.

통화 큐를 설정하려면 Teams 관리 센터에서 음성을 확장하고 **통화** 큐를 클릭한 다음 추가를 **클릭합니다.**

## <a name="resource-account-and-language"></a>리소스 계정 및 언어

![리소스 계정 및 언어 설정 스크린샷](media/call-queue-name-language.png)

1. 호출 큐의 이름을 입력합니다. 에이전트는 큐에서 들어오는 호출을 받으면 이 이름을 볼 수 있습니다.

2. 계정 **추가를** 클릭하고 이 호출 큐에 사용할 리소스 계정을 검색한 다음 추가를 클릭한 다음 추가를 **클릭합니다.**

3. 언어를 선택 합니다. 이 언어는 시스템 생성 음성 프롬프트 및 음성메일 전사(사용하도록 설정한 경우)에 사용됩니다.

## <a name="greetings-and-music-on-hold-in-queue"></a>대기 중인 큐에서 인사말 및 음악

발신자들에게 큐에 도착할 때 인사말을 재생할지 지정합니다. 재생하려는 인사말이 포함된 MP3, WAV 또는 WMA 파일을 업로드해야 합니다.

Teams는 발신자에 큐에 대기 중인 동안 발신자에 기본 음악을 제공 합니다. 특정 오디오 파일을 재생하려면 오디오 파일 재생을 **선택하고** MP3, WAV 또는 WMA 파일을 업로드합니다.

> [!NOTE]
> 업로드된 기록은 5MB를 넘지 않습니다.
> Teams 통화 큐에 제공되는 기본 음악은 조직에서 지불하는 로열티가 없습니다. 

## <a name="call-agents"></a>에이전트 호출

호출 [큐에](plan-auto-attendant-call-queue.md#prerequisites) 에이전트를 추가할 수 있는 경우 전제적 준비를 참조합니다.

![통화 큐에 대한 사용자 및 그룹 설정 스크린샷](media/call-queue-users-groups.png)

그룹을 통해 최대 20개 에이전트를 개별적으로 최대 200개까지 추가할 수 있습니다.

사용자를 큐에 추가하려면 **사용자** 추가를 클릭하고 사용자를 검색하고 추가를 클릭한 다음 추가를 **클릭합니다.**

큐에 그룹을 추가하려면 그룹 추가를 클릭하고 **그룹을** 검색한 다음 추가를 클릭한 다음 추가를 **클릭합니다.** 메일 그룹, 보안 그룹 및 Microsoft 365 그룹 또는 Microsoft Teams 팀을 사용할 수 있습니다.

> [!NOTE]
> 그룹에 추가된 새 사용자는 첫 번째 호출이 도착하는 데 최대 8시간이 걸릴 수 있습니다.

## <a name="call-routing"></a>통화 라우팅

![회의 모드 및 라우팅 방법 설정 스크린샷](media/call-queue-conference-mode-routing-method.png)

**전화 회의 모드는** 에이전트가 통화를 수락한 후 발신자에 연결되는 데 걸리는 시간을 크게 줄입니다. 전화 회의 모드가 작동하려면 통화 큐의 에이전트가 다음 클라이언트 중 하나를 사용해야 합니다.

  - 최신 버전의 Microsoft Teams 데스크톱 클라이언트, Android 앱 또는 iOS 앱
  - Microsoft Teams 휴대폰 버전 1449/1.0.94.2020051601 이상
  
에이전트의 Teams 계정을 Teams 전용 모드로 설정해야 합니다. 요구 사항을 충족하지 않는 에이전트는 통화 라우팅 목록에 포함되지 않습니다. 에이전트가 호환되는 클라이언트를 모두 사용하는 경우 통화 큐에 전화 회의 모드를 사용하는 것이 좋습니다.

**라우팅 메서드는** 에이전트가 큐에서 호출을 수신하는 순서를 결정합니다. 다음 옵션에서 선택합니다.

- **참석자 라우팅은** 큐에 있는 모든 에이전트를 동시에 링합니다. 호출을 픽업하는 첫 번째 호출 에이전트가 호출을 얻습니다.

- **직렬 라우팅은** 호출 에이전트 목록에 지정된 순서대로 모든 호출 에이전트를 하나씩 **링합니다.** 에이전트가 통화를 기각하거나 선택하지 않는 경우 호출은 다음 에이전트에 벨을 울리며, 에이전트가 선택되거나 시간 외 시간 외로 호출될 때까지 모든 에이전트를 시도합니다.

- **라운드 로빈은** 들어오는 호출의 라우팅을 균형 조정하여 각 호출 에이전트가 큐에서 동일한 호출 수를 얻습니다. 인바운드 판매 환경에서는 모든 호출 에이전트가 동일한 기회를 보장하는 것이 바람직할 수 있습니다.

- **가장 긴 유휴** 시간은 각 호출을 유휴 시간이 가장 긴 에이전트로 라우팅합니다. 에이전트는 현재 상태를 사용할 수 있는 경우 또는 10분 미만 동안 상태 비움 상태인 경우 유휴 상태로 간주됩니다. 현재 상태가 10분 넘게 부재 중 상태인 에이전트는 유휴 상태로 간주되지 않습니다. 현재 상태를 사용 가능으로 변경할 때까지 통화를 받을 자격이 없습니다. 

![라우팅, 옵트아웃 및 경고 시간 설정 스크린샷](media/call-queue-presence-agents-time.png)


**현재 상태 기반 라우팅은** 호출 에이전트의 가용성 상태를 사용하여 선택한 라우팅 방법에 대한 호출 라우팅 목록에 에이전트를 포함해야 하는지 여부를 판단합니다. 가용성 상태가 사용 가능으로  설정된 호출 에이전트는 통화 라우팅 목록에 포함되어 있으며 통화를 받을 수 있습니다. 가용성 상태가 다른 상태로 설정된 에이전트는 통화 라우팅 목록에서 제외되어 가용성 상태가 사용 가능으로 다시 변경될 때까지 통화를 받지 **못합니다.** 

라우팅 방법 중 원하는 방법으로 현재 상태 기반 호출 라우팅을 사용하도록 설정할 수 있습니다.

에이전트가 통화 수신을 옵트아웃하면 해당 가용성 상태가 설정되어 있는 항목과 관계없이 통화 라우팅 목록에 포함되지 않습니다. 

> [!NOTE]
> 비즈니스용 Skype 클라이언트를 사용하는 에이전트는 현재 상태 기반 라우팅을 사용하도록 설정한 경우 통화 라우팅 목록에 포함되지 않습니다. 비즈니스용 Skype를 사용하는 에이전트가 있는 경우 현재 상태 기반 통화 라우팅을 사용하지 않습니다.

**에이전트 경고 시간은** 큐가 다음 에이전트로 호출을 리디렉션하기 전에 에이전트의 전화가 울리는 기간을 지정합니다.

권장되는 설정은 다음과 같습니다.

- **회의 모드에서** **자동으로**
- **라운드** **로빈** 또는 가장 긴 유휴로 라우팅 **방법**
- **에 대한** 현재 상태 기반 **라우팅**
- **에이전트 경고 시간:** **20초**

> [!NOTE]
> 현재 상태 기반 라우팅을 사용하도록 설정되지 않은 경우 큐에 여러 호출이 있는 경우 시스템은 해당 상태와 관계없이 에이전트에 동시에 이러한 호출을 제공합니다. 이렇게 하면 특히 일부 에이전트가 제시된 초기 호출에 응답하지 않는 경우 에이전트에 대한 여러 호출 알림이 표시됩니다.

## <a name="call-overflow-handling"></a>호출 오버플로 처리

![호출 오버플로 설정 스크린샷](media/call-queue-overflow-handling.png)

**큐의 최대 호출은** 주어진 시간 동안 큐에서 대기할 수 있는 최대 호출 수를 지정합니다. 기본값은 50이지만 0~200 범위일 수 있습니다. 이 제한에 도달하면 최대 호출 수에 도달한 경우 설정에 따라 호출이 **처리됩니다.**

통화 연결을 끊거나 통화 라우팅 대상 중 하나에 리디렉션할 수 있습니다. 예를 들어 발신자에 큐에 있는 에이전트에 대한 음성 메일이 남아 있을 수 있습니다. 외부 전송의 경우 번호 [](plan-auto-attendant-call-queue.md#prerequisites) 서식에 대한 기술 [](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) 세부 정보인 전제 사항 및 외부 전화 번호 전송을 참조합니다.

> [!NOTE]
> 최대 호출 수를 0으로 설정하면 인사말 메시지가 재생되지 않습니다.

## <a name="call-timeout-handling"></a>호출 시간 제한 처리

![통화 시간 제한 설정 스크린샷](media/call-queue-timeout-handling.png)

**호출 시간 제한: 최대** 대기 시간은 리디렉션되거나 연결이 끊기기 전에 큐에 통화가 대기할 수 있는 최대 시간을 지정합니다. 0초에서 45분까지 값을 지정할 수 있습니다.

통화 연결을 끊거나 통화 라우팅 대상 중 하나에 리디렉션할 수 있습니다. 예를 들어 발신자에 큐에 있는 에이전트에 대한 음성 메일이 남아 있을 수 있습니다. 외부 전송의 경우 번호 [](plan-auto-attendant-call-queue.md#prerequisites) 서식에 대한 기술 [](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) 세부 정보인 전제 사항 및 외부 전화 번호 전송을 참조합니다.

통화 시간 제한 옵션을 선택한 경우 저장을 **클릭합니다.**

## <a name="caller-id-for-outbound-calls"></a>아웃바운드 호출에 대한 호출자 ID

호출 큐의 에이전트가 고객 호출을 반환하기 위해 전화를 걸 수 있는 경우 통화 큐의 구성원에 대한 발신자 ID를 적절한 자동 전화 연결의 서비스 번호로 설정하는 것이 고려됩니다. 자세한 [내용은 Microsoft Teams에서 발신자 ID](caller-id-policies.md) 정책 관리를 참조하세요.

## <a name="supported-clients"></a>지원되는 클라이언트

다음 클라이언트는 호출 큐의 호출 에이전트에 대해 지원됩니다.

  - 비즈니스용 Skype 데스크톱 클라이언트 2016(32비트 및 64비트 버전)
  - Lync 데스크톱 클라이언트 2013(32비트 및 64비트 버전)
  - Microsoft Teams에서 지원되는 모든 IP 전화 모델입니다. 비즈니스용 [Skype Online용 전화기 보기를 참조하세요.](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)
  - Mac 비즈니스용 Skype 클라이언트(버전 16.8.196 이상)
  - Android 비즈니스용 Skype 클라이언트(버전 6.16.0.9 이상)
  - iPhone 비즈니스용 Skype 클라이언트(버전 6.16.0 이상)
  - iPad 비즈니스용 Skype 클라이언트(버전 6.16.0 이상)
  - Microsoft Teams Windows 클라이언트(32비트 및 64비트 버전)
  - Microsoft Teams Mac 클라이언트
  - Microsoft Teams iPhone 앱
  - Microsoft Teams Android 앱

    > [!NOTE]
    > 직접 라우팅 번호가 할당된 통화 큐는 비즈니스용 Skype 클라이언트, Lync 클라이언트 또는 비즈니스용 Skype IP 전화기에서 에이전트로 지원되지 않습니다.

## <a name="call-queue-cmdlets"></a>큐 cmdlet 호출

또한 큐를 사용하여 Windows PowerShell 큐를 만들고 설정할 수 있습니다. 다음은 호출 큐를 관리하는 데 사용하는 cmdlet입니다.

- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>관련 항목

[다음은 전화 시스템 기능입니다.](here-s-what-you-get-with-phone-system.md)

[서비스 전화 번호 가져오기](getting-service-phone-numbers.md)

[오디오 회의 및 통화 요금제 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[Windows PowerShell 및 Lync Online 소개](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
