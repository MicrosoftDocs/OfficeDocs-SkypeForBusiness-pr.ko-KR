---
title: Microsoft Teams에서 실시간 이벤트 설정
author: serdarsoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: 네트워크 설정, 라이선스 할당, 라이브 이벤트 기능 및 일정 설정, 비디오 배포 솔루션 등 Teams 라이브 이벤트에 대해 설정합니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a2e7061252afc5c485da01c3c1c30e9625bd07cc
ms.sourcegitcommit: 3f046142c40b3b776165e964f2b8718e2fe55df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2022
ms.locfileid: "65661669"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Microsoft Teams에서 실시간 이벤트 설정

라이브 이벤트를 설정하는 경우 몇 가지 단계를 수행해야 합니다.

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>1단계: Teams에서 실시간 이벤트를 위한 네트워크 설정

Teams에서 생성된 라이브 이벤트를 사용하여 용어 집합을 가져오려면 [Teams을 위해 조직의 네트워크를 준비](../prepare-network.md)해야 합니다.  

## <a name="step-2-get-and-assign-licenses"></a>2단계: 라이선스 받기 및 할당하기

[실시간 이벤트를 생성하고 예약 할 수 있는 사람](plan-for-teams-live-events.md#who-can-attend-create-and-schedule-live-events)과 [실시간 이벤트를 볼 수 있는 사람](plan-for-teams-live-events.md#who-can-watch-live-events)에게 올바른 라이선스 할당이 있는지 확인하세요.

## <a name="step-3-set-up-live-events-policies"></a>3단계: 라이브 이벤트 정책 설정

실시간 이벤트 정책은 조직에서 실시간 이벤트를 보유할 수 있는 사람과 이들이 생성한 이벤트에서 사용할 수 있는 기능을 제어하는 데 사용됩니다. 기본 정책을 사용하거나 하나 이상의 사용자 지정 라이브 이벤트 정책을 만들 수 있습니다. 사용자 지정 정책을 만든 후 조직의 사용자 또는 사용자 그룹에 할당합니다.

> [!NOTE]
> 조직의 사용자는 사용자 지정 정책을 만들고 할당하지 않는 한 전역(조직 전체 기본값) 정책을 받게 됩니다. 기본적으로 전역 정책에서는 Teams 사용자에 게 실시간 이벤트 예약을 사용할 수 있습니다. live 캡션과 자막(기록)이 꺼져 있는 경우 조직의 모든 사용자가 실시간 이벤트에 참석할 수 있으며 녹음/녹화 설정은 항상 녹음/녹화로 설정됩니다.

### <a name="create-or-edit-a-live-events-policy"></a>라이브 이벤트 정책 만들기 또는 편집

<a name="bkcreatepolicy"> </a>

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **모임** > **라이브 이벤트 정책****관리 정책** >  탭으로 이동합니다.
2. 다음 옵션 중 하나를 수행합니다.

    - 기존 기본 정책을 편집하려면 **전역(조직 전체 기본값)** 을 선택하세요.
    - 새 사용자 지정 정책을 만들려면 **+추가** 를 선택합니다.
    - 사용자 지정 정책을 편집하려면 정책을 선택하고 **편집** 을 선택합니다.

    조직의 요구 사항에 맞게 변경할 수 있는 설정은 다음과 같습니다.

    ![라이브 이벤트 정책 설정의 스크린샷.](../media/teams-live-events-policies-new.png "Microsoft Teams 관리 센터의 라이브 이벤트 정책 설정 스크린샷입니다.")

|설정  |설명  |
|---------|---------|
|**제목**     |이 제목은 라이브 이벤트 정책 페이지에 나타나는 정책의 제목입니다. 64자를 초과하거나 특수 문자를 사용할 수 없습니다.          |
|**설명**    |이를 사용하여 정책에 대한 설명을 추가하세요.         |
|**라이브 이벤트 예약**     |이 기능을 켜면 조직 사용자가 팀에서 라이브 이벤트를 만들고 예약할 수 있습니다. 사용자가 외부 앱 이나 장치를 사용하여 생성된 라이브 이벤트를 예약하도록 하려면 추가 단계를 수행해야 합니다. 자세한 내용은 [사용자가 외부 앱 또는장치를 사용하여 생성된 이벤트를 예약할 수 있도록 허용](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)을 참조하세요.     |
|**참석자를 위한 전사** |이 설정은 팀에서 생성된 이벤트에만 적용할 수 있습니다. 이 기능을 켜면 이벤트 중에 실시간 이벤트 참석자가 실시간으로 캡션 및 자막을 볼 수 있습니다.         |
|**예약된 라이브 이벤트에 참석할 수 있는 사용자**    |다음 중 하나를 선택합니다.<br><br>**모두** 사용자는 조직 외부의 사람을 포함하여 모든 사람이 참석할 수 있는 실시간 이벤트를 만들 수 있습니다. 이 설정은 사용자가 실시간 이벤트를 예약할 때 Teams에서 **공개** 권한 유형을 활성화합니다.<br> **조직의 모든 사용자** 조직에 추가된 [게스트 사용자](../add-guests.md)를 포함하여 조직의 사용자가 참석할 수 있는 실시간 이벤트를 만들 수 있습니다. 사용자는 익명 사용자가 참석하는 라이브 이벤트를 만들 수 없습니다. 이 설정은 사용자가 실시간 이벤트를 예약할 때 Teams에서 **조직 내** 권한 유형을 활성화합니다.<br> **특정 사용자 또는 그룹** 사용자 또는 그룹은 조직의 특정 사용자 또는 그룹에만 참석할 수 있는 라이브 이벤트를 만들 수 있습니다. 사용자는 조직의 모든 사람이나 익명 사용자가 참석하는 실시간 이벤트를 만들 수 없습니다. 이 설정은 사용자가 실시간 이벤트를 예약할 때 Teams에서 **사용자 및 그룹** 권한 유형을 활성화합니다.       |
|**녹음/녹화 설정**  <br>     | 이 설정은 팀에서 생성된 이벤트에만 적용할 수 있습니다. 다음 중 하나를 선택합니다. <br><br> **항상 녹화** 사용자가 만든 라이브 이벤트는 항상 기록 됩니다. 이벤트가 끝나면 이벤트 팀 구성원이 녹화를 다운로드하고 참석자가 이벤트를 볼 수 있습니다. <br> **녹화하지 않음** 사용자가 만든 라이브 이벤트가 기록되지 않습니다. <br>**주최자에 따라 기록 여부 결정** 사용자는 라이브 이벤트를 기록할지 여부를 결정할 수 있습니다. 녹화된 경우 이벤트가 끝난 후 이벤트 팀 구성원이 녹화를 다운로드하면 참석자가 이벤트를 볼 수 있습니다.

또한 Windows PowerShell 사용하여 이 작업을 수행할 수 있으며, 현재 GCC High 및 DoD 고객은 이 방법을 사용해야 합니다. 자세한 내용은 [PowerShell을 사용하여 Teams에서 라이브 이벤트 정책 설정](set-teams-live-events-policies-using-powershell.md)을 참조 하세요.

### <a name="assign-a-live-events-policy-to-users"></a>사용자에게 라이브 이벤트 정책 할당

사용자 지정 라이브 이벤트 정책을 만든 경우, 정책이 활성화될 수 있도록 사용자에게 할당합니다. <br><br>[!INCLUDE [assign-policy](../includes/assign-policy.md)]

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>사용자가 외부 앱 또는 장치로 생성된 이벤트를 예약할 수 있도록 합니다.

사용자가 외부 앱 또는 디바이스를 사용하여 생성된 이벤트를 예약하려면 다음 단계도 수행해야 합니다.

1. 조직의 사용자에 대해 Microsoft Stream을 활성화하세요. 스트림은 적격 Microsoft 365 또는 Office 365 구독의 일부 또는 독립 실행형 서비스로 사용할 수 있습니다. 스트림은 Business Essentials 또는 Business Premium 요금제에 포함되지 않습니다. 자세한 내용은 [Stream 라이센싱 개요](/stream/license-overview)를 참조하세요.

   >[!Note]
   > Microsoft Stream에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](../tmr-meeting-recording-change.md)로의 변경은 단계별로 접근합니다. 출시하면 이 환경에 대해 옵트인할 수 있고 11월에는 Stream을 계속 사용하려는 경우 옵트아웃해야 합니다. 2021년 초에는 모든 고객이 새 모임 녹음/녹화를 위해 비즈니스용 OneDrive와 SharePoint를 사용해야 합니다. 사용자가 Stream에 액세스할 수 있도록 [**사용자에게 라이선스를 할당하는**](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) 방법에 대해 자세히 알아봅니다. [**이 문서에**](/stream/disable-user-organization) 정의된 대로 사용자에 대해 Stream이 차단되지 않았는지 확인합니다.

2. 사용자에게 Stream의 실시간 이벤트 생성 권한이 있는지 확인하세요. 기본적으로 관리자는 외부 앱 또는 장치로 이벤트를 만들 수 있습니다. Stream 관리자는 [추가 사용자를 사용하여 스트림에서 실시간 이벤트를 만들](/stream/live-event-administration#restrict-who-can-create-events) 수 있습니다.

3. 실시간 이벤트 주최자가 Stream 관리자가 설정한 회사 정책에 동의했는지 확인하십시오. Stream 관리자가 [회사 가이드라인 정책을 설정](/stream/company-policy-and-consent)하고 직원이 콘텐츠를 저장하기 전에이 정책을 수락하도록 요구하는 경우 사용자는 팀에서 실시간 이벤트(외부 앱 또는 장치 사용)를 만들기 전에 이 작업을 수행해야 합니다. 조직에서 실시간 이벤트 기능을 출시하기 전에 이러한 실시간 이벤트를 만들 사용자가 정책에 동의했는지 확인하세요.

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>4단계: Teams에서 라이브 이벤트에 대한 비디오 배포 솔루션 설정

라이브 이벤트 비디오 재생은 ABR(Adaptive Bitrate Streaming)을 사용하지만 유니캐스트 스트림이므로 모든 시청자가 인터넷에서 자신의 비디오 스트림을 받고 있습니다. 조직의 많은 부분으로 전송되는 실시간 이벤트 또는 비디오의 경우 시청자가 상당한 양의 인터넷 대역폭을 소비할 수 있습니다. 라이브 이벤트의 인터넷 트래픽을 줄이려는 조직을 위해 라이브 이벤트 솔루션은 소프트웨어 정의 네트워크(SDN) 또는 엔터프라이즈 컨텐츠 전송 네트워크 (eCDN)를 제공하는 Microsoft의 신뢰할 수 있는 비디오 제공 파트너와 통합됩니다. 이러한 SDN/eCDN 플랫폼을 통해 조직은 최종 사용자 시청 경험을 희생하지 않고도 네트워크 대역폭을 최적화할 수 있습니다. 파트너는 엔터프라이즈 네트워크에서보다 확장 가능하고 효율적인 비디오 배포를 지원할 수 있습니다.

**Teams 외부에서 솔루션 구매 및 설정** Microsoft의 신뢰할 수 있는 비디오 제공 파트너를 활용하여 비디오 제공 확장에 대한 전문가의 도움을 받으세요. 비디오 배달 공급자를 Teams 사용할 수 있도록 설정하려면 먼저 Teams 외부에서 SDN/eCDN 솔루션을 구매하고 설정해야 합니다.

다음 SDN/eCDN 솔루션은 사전 통합되어 있으며 Stream과 함께 사용하도록 설정할 수 있습니다.

- **Hive Streaming** 은 라이브 및 주문형 엔터프라이즈 비디오 배포를 위한 간단하고 강력한 솔루션을 제공합니다. Hive는 추가 하드웨어나 대역폭이 필요 없고 네트워크에 영향을 주지 않고 수천 명의 동시 비디오 뷰어를 안전하게 사용할 수 있는 소프트웨어 기반 솔루션입니다. Hive Streaming은 SDN/eCDN 솔루션을 구매하기 전에 비디오가 네트워크에 미치는 영향을 이해하려는 고객을 위해 Microsoft 고객을 위한 브라우저 기반 분석 솔루션도 제공합니다. [자세히 알아보세요](https://www.hivestreaming.com/partners/integration-partners/microsoft/).

- **Kollective** 는 기존 네트워크 인프라를 활용하여 다양한 형태의 콘텐츠(라이브 스트리밍 비디오, 주문형 비디오, 소프트웨어 업데이트, 보안 패치 등)를 더 빠르고 안정적으로, 더 적은 대역폭으로 제공하는 클라우드 기반 스마트 피어링 배포 플랫폼입니다. Microsoft의 보안 플랫폼은 세계 최대 금융 기관의 신뢰를 받고 있으며 추가 하드웨어와 설정이 필요하지 않고 유지 관리가 쉽습니다. [자세히 알아보세요](https://kollective.com/microsoft-pilot/).

- **Ramp OmniCache** 는 차세대 네트워크 배포를 제공하고 글로벌 WAN을 통한 비디오 컨텐츠의 완벽한 전달을 보장하여 이벤트 제작자가 네트워크 대역폭을 최적화하고 성공적인 라이브 이벤트 브로드 캐스트 및 주문형 스트리밍을 지원하도록 돕습니다. 팀에서 진행되는 라이브 이벤트에 대한 램프 OmniCache에 대한 지원은 곧 제공 될 예정입니다. [자세히 알아보세요](https://rampecdn.com).

- 네트워크 최적화 업계 표준인 **Riverbed** 는 가속 솔루션을 Microsoft Teams 및 Stream으로 확장하고 있습니다.  이제 Microsoft 365 고객은 어디서나 인력 생산성을 높이기 위해 다양한 주요 엔터프라이즈 SaaS 서비스와 함께 Teams 및 Stream을 포함한 365개의 트래픽을 자신 있게 가속화할 수 있습니다. Teams 및 스트림 가속은 Riverbed의 세계적 수준의 지원과 지속적인 투자에 대한 모든 보증과 함께 제공되는 간편한 설정을 통해 활성화할 수 있습니다.

> [!NOTE]
> 선택한 SDN 또는 eCDN 솔루션은 선택한 **타사 공급자의 서비스 약관 및 개인 정보 취급 방침** 에 적용됩니다. 이 기능은 공급자의 솔루션 사용을 제어합니다. 공급자의 솔루션 사용에는 Microsoft 볼륨 라이선싱 조건 또는 온라인 서비스 조건이 적용되지 않습니다. **타사 공급자의 약관** 에 동의하지 않을 경우 Teams에서 해당 솔루션을 사용하지 마세요.

SDN 또는 eCDN 솔루션을 설정한 후에는 Teams에서 실시간 이벤트에 대해 공급자를 구성할 수 있습니다.

## <a name="next-steps"></a>다음 단계

[Teams에서 라이브 이벤트 설정 구성하기](configure-teams-live-events.md)로 이동합니다.

### <a name="related-topics"></a>관련 항목

- [Teams 라이브 이벤트란?](what-are-teams-live-events.md)
- [Teams 라이브 이벤트 계획](plan-for-teams-live-events.md)
- [Teams에서 라이브 이벤트 설정 구성하기](configure-teams-live-events.md)
