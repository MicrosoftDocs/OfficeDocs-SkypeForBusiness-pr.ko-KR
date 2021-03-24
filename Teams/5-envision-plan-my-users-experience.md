---
title: Microsoft Teams의 사용자 환경 계획
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Teams 클라이언트 앱을 선택하고 엔드포인트 품질을 계획하고, 엔드포인트를 배포하고 오디오 Wi-Fi 권장 사항을 얻습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d20d914ab6ceca1d264a23662c9c8a067798a82
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094736"
---
# <a name="plan-my-users-experience"></a>사용자 환경 계획

이 문서에서는 사용자 경험에 직접적인 영향을 주는 클라우드 음성 서비스 배포의 요소를 올바르게 식별하기 위한 요구 사항에 대한 개요를 제공합니다. 배포 전에 이러한 항목을 준비하면 사용자에게 고품질의 신뢰할 수 있는 환경을 성공적으로 제공할 가능성이 높아질 수 있습니다. 

## <a name="client-deployment"></a>클라이언트 배포

Microsoft Teams에는 웹, 데스크톱(Windows 및 Mac), 모바일(Android 및 iOS)에 사용할 수 있는 클라이언트가 있습니다. 데스크톱(Windows 및 Mac) 및 모바일 클라이언트가 설치되는 방법에 대한 자세한 내용은 [Microsoft Teams에 대한 클라이언트 다운로드를 참조합니다.](./get-clients.md)

## <a name="client-updates"></a>클라이언트 업데이트

Teams의 주요 이점 중 하나는 클라이언트가 자동으로 최신으로 유지되는 것입니다. PC 및 Mac의 클라이언트는 새 빌드를 확인하고 앱이 유휴일 때 새 클라이언트를 다운로드하는 백그라운드 프로세스를 사용하여 업데이트됩니다.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>엔드포인트 품질 계획

아래 다이어그램에서 볼 수 있 처럼 엔드포인트는 사용자에게 품질 환경을 제공하는 데 중요한 구성 요소입니다.

![품질의 세 가지 구성 요소를 설명하는 다이어그램](media/plan-my-users-experience-image1.png "품질의 세 가지 구성 요소와 서비스 관리가 세 구성 요소를 모두 겹치는 방법을 설명하는 다이어그램입니다. 엔드포인트에 포커스가 있습니다.")

팀 엔드포인트는 PC, Mac, 태블릿 및 모바일 디바이스를 비롯한 여러 장치에서 실행할 수 있습니다. 환경의 일부에는 디바이스뿐만 아니라 사용자가 디바이스에 연결하는 방식(예: 디바이스의 기본 제공 마이크/스피커, 이어버드 또는 최적화된 헤드셋 사용)이 있습니다. 최적화된 헤드셋을 사용하면 전체 사용자 환경을 강화할 수 있습니다.

엔드포인트 계획에 대한 다음 지침은 조직이 Teams를 성공적으로 온보드할 수 있도록 하는 데 도움이 됩니다.

## <a name="endpoint-capability"></a>엔드포인트 기능

계획의 첫 번째 부분은 조직의 모든 PC 및 기타 디바이스가 Teams를 실행할 수 있도록 하는 것입니다. 이는 하드웨어 요구 사항을 보는 것만이 아니라 PC가 백그라운드에서 무엇을 하는지 이해해야 합니다. 많은 조직에서 디바이스의 기본 성능에 영향을 줄 수 있는 침입 감지 시스템 및 맬웨어 방지 소프트웨어를 포함하여 다른 소프트웨어를 실행합니다.

각 플랫폼(웹, 데스크톱 및 모바일)의 Teams 클라이언트에 대한 소프트웨어 요구 사항에 대한 자세한 내용은 Microsoft Teams에 대한 클라이언트 다운로드 [를 참조하세요.](./get-clients.md)

## <a name="endpoint-firewalls"></a>엔드포인트 방화벽

클라이언트 쪽 방화벽은 사용자 환경에 상당한 영향을 줄 수 있습니다.
클라이언트 쪽 방화벽은 통화가 설정되지 않도록 할 뿐만 아니라 통화 품질에 영향을 줄 수 있습니다. [Microsoft 365 또는 Office 365 URL](/microsoft-365/enterprise/urls-and-ip-address-ranges)및 IP 주소 범위의 정보를 기반으로 클라이언트 방화벽에서 적절한 제외를 구성합니다. 타사 공급업체는 제외를 만드는 방법에 대한 특정 지침을 제공합니다.

>[!NOTE]
> Microsoft Teams는 적절한 방화벽 구성으로 Windows 방화벽을 자동으로 업데이트합니다.

## <a name="wi-fi-recommendations-for-endpoints"></a>Wi-Fi 권장 사항

Microsoft Teams에서 실시간 워크로드를 지원하기 위해 최적화된 Wi-Fi 네트워크를 배포하는 데 상당한 계획이 소요됩니다. 다음 섹션에서는 엔드포인트를 계획할 때 일반적인 문제를 방지하는 데 도움이 되는 몇 가지 일반적인 지침을 제공합니다.

### <a name="wi-fi-drivers"></a>Wi-Fi 드라이버

일부 Wi-Fi 문제가 있을 수 있습니다. 예를 들어 드라이버는 액세스 지점 간에 매우 공격적인 로밍 동작이 발생하여 통화 품질이 좋지 않을 수 있습니다.
일반적으로 발생하는 것은 아니지만 배포하기 전에 PC의 Wi-Fi 드라이버를 업데이트하고 테스트하는 것이 중요합니다.

### <a name="wi-fi-bands"></a>Wi-Fi 밴드

현재는 2.4GHz 및 5.0GHz의 Wi-Fi 장비에 사용되는 두 가지 유형의 대역이 있습니다. 조직에서 두 대역을 모두 제공하는 경우 5.0GHz 대역을 선호하도록 드라이버 설정을 구성해야 합니다. 이 대역은 매우 밀도가 높고 2.4GHz 대역에서 볼 수 있는 간섭의 영향을 덜 받는다.
이 권장은 5.0GHz 네트워크 대역을 적절하게 최적화했다고 가정합니다.

### <a name="wi-fi-radio-type"></a>Wi-Fi 라디오 유형

새로운 무선 형식을 지원하는 Wi-Fi 계획합니다. 프로비전하는 디바이스에서 802.11ac 또는 최신 Wi-Fi 활용하면 매우 좋은 성능을 얻을 수 있습니다.

### <a name="wireless-avoidance"></a>무선 회피

일부 조직에서는 이러한 문제를 Wi-Fi 선호합니다. 경우에 따라 이 지침은 유선 네트워크에 직접 연결하기 위한 사용자에게 권장을 통해 제공됩니다. 경우에 따라 네트워크 바인딩 순서에 무선 연결이 선호되고 PC가 유선 연결에 연결되어 있는 경우에도 이 연결을 계속 사용할 수 있습니다. 의도하지 않은 동작을 방지하기 위해 이 시나리오를 피하기 위해 바인딩 순서를 구성합니다.

### <a name="80211-power-save-protocol"></a>802.11 Power Save 프로토콜

조직에서 802.11 Power Save 프로토콜을 지원하지 않는 무선 액세스 지점 또는 라우터를 사용하는 경우 Windows 장치에서 실행되는 Microsoft Teams에서 통화가 떨어질 수 있습니다. 무선 액세스 지점 또는 라우터를 업그레이드할 수 없는 경우 배터리 전원에서 실행되는 장치에서 Windows Power Plan 설정을 업데이트해야 합니다. 자세한 내용 및 구성 지침은 다음 지원 문서 [에 제공됩니다.](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>조직에 배포되는 Teams 클라이언트는 무엇입니까?</li><li>Teams 클라이언트를 처음에 사용자에게 배포하는 방법</li><li>품질 경험에 대한 Teams 요구 사항을 충족하는지 검사하기 위해 엔드포인트 및 디바이스를 평가하는 책임은 누구인가요?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>Teams 클라이언트를 배포하기 위해 수행될 프로세스를 문서화합니다.</li><li>엔드포인트 및 디바이스를 평가하고 필요한 수행 및 수정을 수행합니다.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Teams용 디바이스

Microsoft Teams는 모임 또는 전화 시스템으로 사용할 수 있습니다. 이러한 기능을 사용할 때 Teams에 사용되는 인터페이스 디바이스는 사용자 경험에서 중요한 역할을 합니다.

기본 제공 PC 스피커와 마이크를 사용하는 경우 해당 구성이 있는 사용자에게는 허용되는 소리가 들 수 있습니다. 그러나 일반적으로 이러한 디바이스는 노이즈 취소에 최적화되지 않습니다. 모든 유형의 주변 소음이 호출에 다른 사용자에 다운스트림 영향을 줄 수 있습니다. 이러한 시나리오에 최적화된 디바이스를 활용하면 고품질 환경을 보장하는 데 도움이 됩니다.

각 디바이스는 사용자의 요구를 충족해야 합니다. 조직의 다른 사용자 및 사용 사례에 대한 헤드셋과 같은 디바이스를 조정해야 합니다.
가상 장치 매핑 연습은 계획 프로세스의 일부로 완료해야 합니다.

디바이스를 선택한 후 최종 유효성 검사를 위한 파일럿 테스트 계획에 해당 디바이스를 포함합니다. 파일럿 중에 설문 조사를 활용하여 피드백을 수집하여 디바이스 전략이 최적의지 확인합니다.

> [!NOTE]
> 현재 비즈니스용 Skype 인증 프로그램을 통해 인증된 오디오 디바이스를 사용하는 것이 좋습니다. 이 프로그램에서 인증된 디바이스를 찾으신 경우 [Microsoft Teams](https://products.office.com/microsoft-teams/across-devices/devices) 디바이스 및 [USB 오디오 및 비디오 디바이스를 참조합니다.](/SkypeForBusiness/certification/devices-usb-devices)



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>사용자 및 회의실 환경을 위한 조직의 전체 디바이스 전략을 결정하세요.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>조직의 가상 장치 매핑 연습을 완료합니다.</li><li>사용자 및 회의실에 대한 디바이스를 얻기 위한 프로세스를 문서화합니다.</li><li>사용자 및 회의실에 대한 디바이스 배포 및 구성 프로세스를 문서화합니다.</li><li>배포를 시작할 초기 디바이스를 조달합니다.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->