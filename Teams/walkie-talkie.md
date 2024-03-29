---
title: Microsoft Teams의 Walkie Talkie 앱
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: IT 관리자 관점에서 Microsoft Teams에서 Walkie Talkie 앱을 구성하는 방법
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.date: 11/17/2022
ms.openlocfilehash: c4184e82e99fa4f3169fea14c62f3a892750bf8c
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2023
ms.locfileid: "69845895"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams의 Walkie Talkie 앱

Teams의 Walkie Talkie 앱은 팀에 PTT(즉시 푸시 투 토크) 통신을 제공하며 Android 및 iOS에서 사용할 수 있습니다. Walkie Talkie를 사용하면 사용자가 구성원인 것과 동일한 기본 채널을 사용하여 팀과 연결할 수 있습니다.

채널에서 Walkie Talkie에 연결하는 사용자만 참가자가 되고 PTT를 사용하여 서로 통신할 수 있습니다. 사용자는  **연결 끊기를** 탭할 때까지 전송을 계속 받습니다.

Teams의 Walkie Talkie를 사용하면 사용자는 부피가 큰 라디오를 휴대할 필요 없이 친숙한 PTT 환경과 안전하게 통신할 수 있으며, Walkie Talkie는 WiFi 또는 셀룰러 인터넷 연결을 통해 어디서나 작동합니다.

> [!NOTE]
> 워키 토키는 현재 중국에서 사용할 수 없습니다.

## <a name="license-requirements"></a>라이선스 요구 사항

Walkie Talkie는 [Microsoft 365 및 Office 365 구독](/office365/servicedescriptions/teams-service-description)에 있는 Teams의 모든 유료 라이선스에 포함되어 있습니다. Teams 가져오기에 대한 자세한 내용은 [Microsoft Teams를 어떻게 할까요? 확인하세요.](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploying-walkie-talkie"></a>Walkie Talkie 배포

Walkie Talkie는 GMS(Google Mobile Services) 및 iOS 디바이스를 사용하는 Android 디바이스에서 지원됩니다.

### <a name="step-1-make-sure-walkie-talkie-is-enabled-in-your-organization"></a>1단계: 조직에서 Walkie Talkie가 사용하도록 설정되어 있는지 확인

기본적으로 Walkie Talkie 앱은 조직의 모든 Teams 사용자에 대해 사용하도록 설정됩니다.

Microsoft Teams 관리 센터의 [앱 관리](manage-apps.md) 페이지에서 조직 수준에서 앱을 사용할 수 있는지 여부를 제어합니다. 조직에서 앱이 사용하도록 설정되어 있는지 확인하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 메뉴에서 **Teams 앱** > **앱 관리** 로 이동합니다.
2. 앱 목록에서 Walkie Talkie 앱을 검색하고 선택한 다음 **상태** 토글이 **허용됨** 으로 설정되어 있는지 확인합니다.

조직의 특정 사용자가 Walkie Talkie를 사용하도록 허용하거나 차단하려면 [앱 관리](manage-apps.md) 페이지에서 조직에 대해 Walkie Talkie가 사용하도록 설정되어 있는지 확인합니다. 그런 다음 앱 권한에 대한 사용자 지정 정책을 만들고 해당 사용자에게 할당합니다. 자세한 내용은 [Teams에서 앱 권한 정책 관리](teams-app-permission-policies.md)를 참조하세요.

### <a name="step-2-pin-walkie-talkie-to-teams"></a>2단계: 워키 토키를 Teams에 고정

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>맞춤형 최전방 앱 환경을 사용하여 Walkie Talkie 및 기타 앱을 Teams에 고정

Teams의 맞춤형 최전방 앱 환경은 [F 라이선스](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)가 있는 사용자를 위해 Teams에서 가장 관련성이 큰 앱을 고정합니다. 고정된 앱에는 Walkie Talkie, 교대 근무, 작업 및 승인이 포함됩니다. 기본적으로 이 기능은 사용 중이므로 최전방 작업자에게 요구 사항에 맞는 기본 제공 환경을 제공합니다.

앱은 사용자가 빠르고 쉽게 액세스할 수 있는 Teams 모바일 클라이언트 하단의 앱 트레이에 고정됩니다.

설정한 앱 정책의 작동 방식을 포함하여 자세한 내용은 [최전방 직원을 위한 Teams 앱 조정](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)을 참조하세요.

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>앱 설정 정책을 사용하여 Walkie Talkie를 Teams에 고정

앱 설정 정책을 사용하면 Teams를 사용자 지정하여 사용자의 사용자에게 가장 중요한 앱을 고정할 수 있습니다.

사용자를 위해 Walkie Talkie 앱을 고정하려면 전역(조직 전체 기본값) 정책을 편집하거나 앱 설정 정책에서 사용자 지정 정책을 만들고 할당할 수 있습니다. 자세한 내용은 [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)를 참조하세요.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="고정된 앱 추가 창의 고정된 앱 목록에 Walkie Talkie 추가를 보여 주는 스크린샷" lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>네트워크 설명서

Teams의 Walkie Talkie에는 인터넷 연결이 필요합니다. 최적의 환경을 위해서는 다음 네트워크 조건이 필요합니다.

|메트릭 | 필수 |
|---|---|
|대기 시간(RTT) | < 300ms |
|지터 |< 30ms |
|패킷 손실 |< 1% |

위에서 설명한 것처럼 IP 네트워크를 통해 실시간 미디어의 품질은 네트워크 연결의 품질, 특히 다음의 양에 의해 크게 영향을 받습니다.

- **대기 시간** - 네트워크의 지점 A에서 지점 B까지 IP 패킷을 가져오는 데 걸리는 시간입니다. 이 네트워크 전파 지연은 기본적으로 두 지점 사이의 물리적 거리와 빛의 속도와 관련이 있으며, 여기에는 그 사이에 있는 다양한 라우터가 더 많은 오버헤드를 포함합니다. 대기 시간은 RTT(왕복 시간)로 측정됩니다.
- **도착 간 지터** - 연속 패킷 간의 평균 지연 변화입니다.
- **패킷 손실** - 패킷 손실은 지정된 시간 동안 손실되는 패킷의 백분율로 정의되는 경우가 많습니다. 패킷 손실은 거의 영향을 주지 않는 작은 개별 손실 패킷부터 완전한 오디오 컷아웃을 유발하는 백투백 버스트 손실에 이르기까지 오디오 품질에 직접적인 영향을 줍니다.

오디오를 보내거나 받을 때 Walkie Talkie의 예상 데이터 사용량은 약 20Kb/s입니다. 유휴 상태인 경우 Walkie Talkie의 예상 데이터 사용량은 무시할 수 있습니다.

## <a name="walkie-talkie-devices"></a>워키 토키 디바이스

일선 직원들은 휴대폰이 잠겨 있더라도 워키 토키 통화를 말하고 받아야 하는 경우가 많습니다. 이 환경은 전용 PTT 단추가 있는 특수 디바이스를 통해 가능합니다.

#### <a name="headsets"></a>헤드셋

- 무선 헤드셋(iOS 및 Android)
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- 유선 헤드셋(Android만 해당)
  - [클라인 일렉트로닉스](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>견고한 Android 휴대폰

- Crosscall [Core-X4](https://www.crosscall.com/en_FR/core-x4-1001010801327.html), [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html), [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html), [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html) 및 [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - 수동 설정: Teams가 설치된 상태에서 **설정** > **단추** 로 이동합니다. 전용 단추(1 또는 2)에서 **길게 누른** 다음 **PTT 앱을** 선택합니다. **사용자 지정** 옆에 있는 파란색 휠을 선택하고 **Teams** 를 선택합니다.
- 교세라 [듀라포스 울트라 5G](https://kyoceramobile.com/duraforce-ultra-5g/) 및 [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - 수동 설정: Teams가 설치된 상태에서 **설정** > **프로그래밍 가능 키** 로 이동합니다. **PTT 키를** 선택하거나 디바이스에 따라 **길게 누르** 고 **Teams** 를 선택합니다.
- Honeywell [CT30 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-handheld-computer), [CT30 XP HC](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-hc-mobile-computer), [CT45 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct45-ct45-xp), [EDA51](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/scanpal-eda51-handheld-computer), [EDA52](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/eda52-handheld-computer), [EDA52 HC](https://sps.honeywell.com/gb/en/products/productivity/mobile-computers/healthcare-computers/scanpal-eda52-healthcare-mobile-computer), 
  - 수동 설정: Teams가 설치된 경우 전용 PTT 단추는 기본적으로 Walkie Talkie에서 작동합니다.
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - 수동 설정: Teams가 설치된 상태에서 **설정** > **고급 기능** > **XCover/활성 키로** 이동합니다. 앱으로 **XCover 키 제어를** 켜고 **Teams** 를 선택합니다.
  - [MDM 설정](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - 수동 설정: Teams가 설치된 상태에서 **설정** > **프로그래밍 가능 키** 로 이동합니다. **PTT 키 앱 선택을** 선택하고 **Teams를** 선택합니다.
- Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - 수동 설정: Teams가 설치되면 전용 PTT 단추(LEFT_TRIGGER_2)가 기본적으로 Walkie Talkie에서 작동합니다.

> [!NOTE]
> 이러한 디바이스는 Teams 인증을 받지 않았습니다. Teams Walkie Talkie와 함께 작업할 수 있는 유효성이 검사되었습니다.

## <a name="bluetooth-devices"></a>Bluetooth 디바이스

> [!NOTE]
> 사용자가 Bluetooth 액세서리를 사용하는 경우 MDM(모바일 디바이스 관리) 솔루션이 Bluetooth 디바이스를 차단하지 않는지 확인합니다.

Android OS 버전 12 이상을 실행하는 디바이스에서는 Bluetooth 권한이 필요하며 BLE 스택을 사용하여 연결하는 위치 권한이 더 이상 필요하지 않습니다. Teams 수준에서 "주변 권한"이 부여되지 않은 경우 사용자에게 Bluetooth 권한에 대한 프롬프트가 표시됩니다. 헤드셋과 같은 Bluetooth 액세서리가 장치에 연결되어 있는지 여부에 관계없이 이 프롬프트가 표시됩니다. Bluetooth 액세서리가 연결된 경우 **허용** 을 탭하면 Walkie Talkie를 Bluetooth 액세서리에 연결합니다.

## <a name="get-insight-into-walkie-talkie-usage-and-performance"></a>Walkie Talkie 사용량 및 성능에 대한 인사이트 얻기

Teams 관리 센터의 [Walkie Talkie 사용 현황 및 성능 보고서는](teams-analytics-and-reports/walkie-talkie-usage-report.md) 조직의 Walkie Talkie 활동 및 성능에 대한 개요를 제공합니다. 이 보고서는 생성 및 수신된 PTT 전송 수, 채널 활동, 전송 기간, 디바이스 및 참가자 세부 정보와 같은 정보를 제공합니다.

## <a name="more-information"></a>추가 정보

- 사용자가 모바일 데이터를 사용하여 Teams를 통해 통신하는 경우 Walkie Talkie는 동일한 방법을 사용합니다.
- 워키 토키는 낮은 대역폭 상황 또는 스마트 폰이 연결되고 작동하는 상황에서 잘 작동해야합니다. 워키 토키는 연결이 전혀 없을 때 작동하지 않습니다.

최종 사용자 환경에 대한 자세한 내용은 다음을 참조하세요.

- [Teams Walkie Talkie 시작](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Walkie Talkie를 사용하여 팀과 커뮤니케이션](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
