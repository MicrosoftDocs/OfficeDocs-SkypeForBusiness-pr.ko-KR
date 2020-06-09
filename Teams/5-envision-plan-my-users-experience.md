---
title: Microsoft 팀의 사용자 환경 계획
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 팀 클라이언트 앱을 선택 하 고, 끝점 품질을 계획 하 고, Wi-fi 끝점을 배포 하기 위한 권장 사항을 얻고, 오디오 장치를 선택 합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad827244baaacde8ee5c7166590c81347c8eea5b
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610023"
---
# <a name="plan-my-users-experience"></a>내 사용자 환경 계획

이 문서에서는 사용자 환경에 직접적인 영향을 주는 클라우드 음성 서비스 배포 요소를 적절 하 게 식별 하는 데 필요한 요구 사항에 대해 간략하게 설명 합니다. 배포 하기 전에 이러한 항목을 준비 하면 고품질의 사용자를 위한 안정적인 환경을 제공 하는 데 성공할 확률이 높아집니다. 

## <a name="client-deployment"></a>클라이언트 배포

Microsoft 팀에는 웹, 데스크톱 (Windows 및 Mac) 및 모바일 (Android 및 iOS)에 사용할 수 있는 클라이언트가 있습니다. 데스크톱 (Windows 및 Mac)과 모바일 클라이언트를 설치 하는 방법에 대 한 자세한 내용은 [Microsoft 팀 용 클라이언트 가져오기를](https://docs.microsoft.com/microsoftteams/get-clients)참조 하세요.

## <a name="client-updates"></a>클라이언트 업데이트

팀의 주요 이점 중 하나는 클라이언트가 자동으로 최신 상태로 유지 된다는 것입니다. PC 및 Mac의 클라이언트는 새 빌드를 확인 하는 백그라운드 프로세스를 사용 하 여 업데이트 되며 앱이 유휴 상태일 때 새 클라이언트를 다운로드 합니다.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>끝점 품질 계획

아래 다이어그램에서 볼 수 있듯이 끝점은 사용자에 게 품질 경험을 제공 하기 위한 중요 한 빌딩 블록입니다.

![품질의 세 가지 구성 요소를 설명 하는 다이어그램](media/plan-my-users-experience-image1.png "품질의 세 가지 구성 요소와 서비스 관리가 세 구성 요소를 모두 겹치는 방법을 설명 하는 다이어그램입니다. 끝점에 포커스를 둔 상태")

팀 끝점은 Pc, Mac, 태블릿, 모바일 장치를 비롯 한 다양 한 장치에서 실행 될 수 있습니다. 장치의 기본 제공 마이크/스피커, 이어폰 또는 최적화 된 헤드셋을 사용 하는 것과 같이 장치를 포괄 하는 방법과 사용자가 디바이스에 연결 하는 방법을 경험해 보세요. 최적화 된 헤드셋을 사용 하면 전체적인 사용자 환경이 보강 될 수 있습니다.

끝점 계획에 대 한 다음 지침을 통해 조직에서 팀과 성공적으로 온 보 딩 환경을 유지할 수 있습니다.

## <a name="endpoint-capability"></a>끝점 기능

계획의 첫 번째 부분은 조직의 모든 Pc와 다른 장치에서 팀을 실행할 수 있는지 확인 하는 것입니다. 여기에는 하드웨어 요구 사항이 아닌 PC가 백그라운드에서 수행 하는 작업을 이해 하는 것이 포함 됩니다. 많은 조직이 침입 감지 시스템 및 맬웨어 방지 소프트웨어를 포함 하 여 다른 소프트웨어를 실행 하 여 디바이스의 기본 성능에 영향을 줄 수 있습니다.

각 플랫폼 (웹, 데스크톱, 모바일)의 팀 클라이언트에 대 한 소프트웨어 요구 사항에 대 한 자세한 내용은 [Microsoft 팀 용 클라이언트 가져오기를](https://docs.microsoft.com/microsoftteams/get-clients)참조 하세요.

## <a name="endpoint-firewalls"></a>끝점 방화벽

클라이언트쪽 방화벽은 사용자 환경에 큰 영향을 미칠 수 있습니다.
클라이언트 쪽 방화벽은 통화 설정 방지 외에도 통화 음질에 영향을 줄 수 있습니다. [Microsoft 365 또는 Office 365 url 및 IP 주소 범위](https://aka.ms/o365ips)에 대 한 정보를 기반으로 클라이언트 방화벽에 대 한 적절 한 예외를 구성 합니다. 타사 공급 업체는 제외를 만드는 방법에 대 한 특정 지침을 제공 합니다.

>[!NOTE]
> Microsoft 팀은 적절 한 방화벽 구성을 사용 하 여 Windows 방화벽을 자동으로 업데이트 합니다.

## <a name="wi-fi-recommendations-for-endpoints"></a>끝점에 대 한 wi-fi 권장 사항

Microsoft 팀에서 실시간 작업 부하를 지원 하기 위해 최적화 된 Wi-fi 네트워크를 배포 하는 계획은 매우 중요 합니다. 다음 섹션에서는 끝점을 계획할 때 일반적인 문제를 방지 하는 데 도움이 될 수 있는 몇 가지 일반적인 지침을 제공 합니다.

### <a name="wi-fi-drivers"></a>Wi-fi 드라이버

일부 Wi-fi 드라이버에는 문제가 있을 수 있습니다. 예를 들어 드라이버는 액세스 지점 간에 매우 적극적인 로밍 동작을 사용 하 여 낮은 통화 품질을 유발할 수 있습니다.
이는 일반적인 경우가 아니지만 PC의 Wi-fi 드라이버가 배포 전에 업데이트 되 고 테스트 되었는지 확인 하는 것이 중요 합니다.

### <a name="wi-fi-bands"></a>Wi-fi 밴드

현재 Wi-fi 장비에 사용 되는 밴드에는 주로 2.4 GHz 및 5.0 GHz의 두 가지 유형이 있습니다. 조직에서 두 밴드를 모두 제공 하는 경우 5.0 GHz 밴드를 선호 하도록 드라이버 설정을 구성 해야 합니다. 이 밴드는 처리량 측면에서 훨씬 denser, 2.4 GHz 밴드에 표시 되는 간섭의 영향을 덜 받습니다.
이 권장 사항은 5.0 GHz 네트워크 대역을 적절 하 게 최적화 했다고 가정 합니다.

### <a name="wi-fi-radio-type"></a>Wi-fi 송수신 장치 유형

최신 Wi-fi 라디오 형식을 지 원하는 장치에 대 한 계획 프로 비전 하는 장치에서 802.11 ac 이상을 이용 하는 경우 Wi-fi 성능이 매우 우수한 것을 볼 수 있습니다.

### <a name="wireless-avoidance"></a>무선 방지

일부 조직에서는 Wi-fi를 전혀 사용 하지 않는 것이 좋습니다. 때로는 사용자에 게 유선 네트워크에 직접 연결 하는 권장 사항을 통해이 지침이 제공 됩니다. 경우에 따라 네트워크 바인딩 순서에 무선 연결이 기본 설정 되어 있는 경우 PC가 유선 연결에 연결 된 경우에도 해당 연결을 계속 사용할 수 있습니다. 의도 하지 않은이 동작을 방지 하려면이 시나리오를 방지 하기 위해 바인딩 순서를 구성 합니다.

### <a name="80211-power-save-protocol"></a>802.11 전원 절약 프로토콜

조직에서 802.11 절전 프로토콜을 지원 하지 않는 무선 액세스 지점 또는 라우터를 사용 하는 경우 Windows 장치에서 실행 되는 Microsoft 팀에서 호출이 손실 되거나 잘못 된 통화 품질이 발생할 수 있습니다. 무선 액세스 지점이 나 라우터를 업그레이드할 수 없는 경우 배터리 전원으로 실행 되는 장치에서 Windows 전원 관리 옵션 설정을 업데이트 해야 합니다. 자세한 내용 및 구성 지침은 다음 [지원 문서](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)에 나와 있습니다.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>조직에 배포할 팀 클라이언트는 무엇 인가요?</li><li>처음에 팀 클라이언트를 사용자에 게 배포 하는 방법은 무엇 인가요?</li><li>끝점 및 장치를 평가 하 여 품질 경험을 위한 팀 요구 사항에 맞는지 확인 하는 책임은 무엇 인가요?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>팀 클라이언트를 배포 하기 위해 팔 로우 하는 프로세스를 문서화 합니다.</li><li>끝점 및 장치를 평가 하 고 필요한 경우 업데이트를 수행 합니다.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>팀 장치

Microsoft 팀은 모임 또는 전화 시스템에 사용할 수 있습니다. 이러한 기능을 사용 하는 경우 팀에 사용 되는 인터페이스 디바이스는 사용자 환경에서 중요 한 역할을 합니다.

기본 제공 PC 스피커와 마이크를 사용 하는 것은 해당 구성을 가진 사용자가 수용할 수 있는 음질입니다. 그러나 일반적으로 이러한 장치는 노이즈 취소에 최적화 되지 않으며, 모든 유형의 앰비언트 노이즈는 통화 중에 다른 사용자에 게 다운스트림에 영향을 줄 수 있습니다. 이러한 시나리오에 최적화 된 장치를 활용 하면 고품질 환경을 유지할 수 있습니다.

각 장치는 사용자의 요구 사항을 충족 해야 합니다. 조직의 다른 가상 사용자 및 사용 사례에 대 한 헤드셋 등의 장치를 조직에 맞게 조정 해야 합니다.
사용자 대 장치 매핑 연습은 계획 프로세스의 일부로 완료 해야 합니다.

장치를 선택한 후 파일럿 테스트 계획에 최종 유효성 검사에 포함 합니다. 파일럿에서 설문 조사를 활용 하 여 피드백을 수집 하 여 디바이스 전략이 최적화 되었는지 확인 합니다.

> [!NOTE]
> 이번에는 비즈니스용 Skype 인증 프로그램을 통해 인증 된 오디오 장치를 사용 하는 것이 좋습니다. 이 프로그램에서 인증 된 장치를 찾으려면 [Microsoft 팀 디바이스](https://products.office.com/microsoft-teams/across-devices/devices) 및 [USB 오디오 및 비디오 장치](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices)를 참조 하세요.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>사용자 및 회의실 환경에 대 한 조직의 전반적인 디바이스 전략을 결정 합니다.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>조직에 대 한 가상 사용자 대 장치 매핑 연습을 완료 합니다.</li><li>사용자 및 회의실에 대 한 장치를 가져오기 위한 프로세스를 문서화 합니다.</li><li>사용자 및 회의실에 맞게 장치를 배포 하 고 구성 하는 프로세스를 문서화 합니다.</li><li>배포를 시작 하는 초기 장치를 조달 하세요.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
