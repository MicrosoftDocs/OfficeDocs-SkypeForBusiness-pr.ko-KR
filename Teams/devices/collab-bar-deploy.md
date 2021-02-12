---
title: Microsoft Teams에 대한 공동 작업 막대 배포
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Microsoft Teams용 공동 작업 막대를 배포하는 방법을 알아보는 이 문서를 읽어 보십시오.
ms.openlocfilehash: 41eb3335eef78f1da2c64b1df65443ba93d40159
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962909"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>Microsoft Teams에 대한 공동 작업 막대 배포

Microsoft Teams용 공동 작업 막대 배포는 다음 단계로 세분화할 수 있습니다.

- **사이트 준비** 배포 위치(회의실)가 배포 요구 사항을 충족하는지 확인합니다.
- **서비스 준비** 리소스 계정을 만들고 디바이스에 [할당합니다(Microsoft 365](resource-account-ui.md)관리 센터를 사용하여 리소스 계정 만들기 참조). 전용 방 라이선스를 사용하는 것이 좋습니다. 그러나 적절히 라이선스가 부여된 최종 사용자 계정은 공동 작업 표시 막대에 로그인할 수 있습니다.
- **구성 및 배포** 회의실에서 공동 작업 막대를 설정하고 필요한 주변 장치를 연결합니다(공동 작업 막대에 대한 제조업체 설명서 참조).

공동 작업 막대를 관리하려면 전역 관리자, Teams 서비스 관리자 또는 Teams 장치 관리자로 설정해야 합니다. 관리자 역할에 대한 자세한 내용은 Microsoft Teams 관리자 역할을 사용하여 [Teams를 관리하세요.](../using-admin-roles.md)

## <a name="site-readiness"></a>사이트 준비

주문된 디바이스가 조직에 전달되는 동안 네트워킹, 시설 및 오디오 시각 팀과 협의하여 배포 요구 사항이 충족되고 각 사이트와 방이 전원, 네트워킹 및 표시 측면에서 준비되어 있는지 확인합니다.

공동 작업 표시줄 사이트에 대한 권장 사항은

- 최대 4명 크기의 회의실
- 전용 리소스 계정
- 터치 사용 디스플레이
- 이더넷 케이블 연결
- Microsoft Teams 미디어에 대해 네트워크에서 사용하도록 설정된 QoS(서비스 품질)

물리적 설치 고려 사항은 제조업체의 설명서를 참조하고, 있는 경우 화면을 설치 및 탑재하고 케이블을 실행하기 전에 오디오-시각적 팀의 환경을 활용하세요.

> [!TIP]
> 대역폭 계획 및 실시간 트래픽에 대한 네트워크의 적합성을 평가하기 위해 [Teams에](../prepare-network.md) 대한 네트워크 준비를 확인합니다.
>
> Teams 장치와 인터넷 사이에 프록시 서버를 배치하지 않는 것이 좋습니다. 프록시 서버 및 Teams에 대한 자세한 내용은 [Teams용 프록시 서버를 확인하세요.](../proxy-servers-for-skype-for-business-online.md)

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트가 Microsoft Teams의 공동 작업 표시 막대에 대한 사이트 준비 요구 사항을 충족하는지 확인합니다.</li><li>각 사이트에 대해 충분한 대역폭을 제공해야 합니다.</li></ul>|
| ![다음 단계를 표시하는 아이콘](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>공동 작업 표시줄 배포 및 구성을 계획하기 시작 합니다.</li></ul>|

## <a name="service-readiness"></a>서비스 준비

공동 작업 막대를 배포하기 전에 Microsoft 365 리소스 계정, 최종 사용자 계정 또는 둘 다 혼합을 사용할지 결정해야 합니다. Microsoft 365 리소스 계정은 사서함 및 방, 프로젝터 등의 특정 리소스 전용 Teams 계정입니다. 이러한 리소스 계정은 만들 때 정의한 규칙을 사용하여 모임 초대에 자동으로 응답할 수 있습니다. 공동 작업 표시줄이 개인적으로 사용하기 위해 특정 개인에게만 사용되지 않는 한 Microsoft 365 리소스 계정을 설정하는 것이 좋습니다.

### <a name="using-a-resource-account"></a>리소스 계정 사용

Microsoft 365 리소스 계정을 설정하기로 결정한 경우 회의실 라이선스를 구입해야 합니다. 회의실 라이선스에는 조직의 사용자가 Outlook 또는 Teams를 통해 회의실을 예약할 수 있는 리소스 사서함이 포함되어 있습니다. 라이선스를 사용하면 모임 참가자 간 비디오 및 오디오 회의 및 화면 공유도 사용할 수 있습니다.

외부 전화 번호로 받거나 외부 전화 번호로 전화를 걸 필요가 있는 경우 통화 요금제 또는 Microsoft 365 Business Voice 추가 기능 라이선스가 필요할 [수 있습니다.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business) 조직에서 직접 라우팅을 사용하도록 설정한 경우 회의실 SKU만 필요합니다.

리소스 계정을 만들 때 계정에서 모임 요청을 자동으로 수락하거나 거절할지, 모임을 다시 허용할지, 자원을 미리 예약할 수 있는 시간을 지정할지 여부를 선택할 수 있습니다.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Microsoft 365 리소스 계정에 대한 공동 작업 막대에 대한 자세한 내용은 Microsoft 365 관리 센터를 사용하여 리소스 계정 [만들기를 참조하세요.](resource-account-ui.md)

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>외부 전화 통화를 걸거나 받을지 여부를 결정하고 리소스 계정에 대한 라이선스 요구 사항을 식별합니다.</li></ul>|
| ![다음 단계를 표시하는 아이콘](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>리소스 계정을 준비합니다.</li></ul>|

## <a name="configuration-and-deployment"></a>구성 및 배포

구성 및 배포 계획에는 다음과 같은 주요 영역이 있습니다.

- 리소스 계정 프로비전
- 디바이스 배포
- Microsoft Teams 애플리케이션 및 주변 장치 구성에 대한 공동 작업 막대
- 테스트
- 자산 관리

### <a name="account-provisioning"></a>계정 프로비전

사용자가 공동 작업 막대를 예약할 수 있도록 Microsoft 365 리소스 계정을 사용하려면 [Microsoft 365](resource-account-ui.md) 관리 센터를 사용하여 리소스 계정 만들기의 지침에 따라 필요한 각 공동 작업 표시줄에 대해 Microsoft 365 리소스 계정을 만들 수 있습니다. 또한 리소스 계정에 회의실 라이선스를 추가해야 하고, 조직에서 직접 라우팅을 사용하지 않는 경우 외부 전화 번호로 또는 외부 전화 번호로 전화를 걸거나 받으시고 싶은 경우 통화 요금제 또는 Business Voice 라이선스를 추가해야 합니다.

개인적으로 사용할 수 있도록 공동 작업 막대를 개별 사용자에게 할당하려는 경우 추가 계정을 설정할 필요가 없습니다. 사용자는 자신의 개인 계정을 사용하여 공동 작업 막대에 로그인할 수 있습니다.

> [!TIP]
> Microsoft 365 리소스 계정에 대한 표시 이름을 설명하고 이해하기 쉽게 합니다. 다음은 Microsoft Teams의 공동 작업 막대를 검색하고 모임에 추가할 때 사용자에게 표시될 이름입니다. 사이트 회의실 이름(최대 회의실 용량)과 같은 규칙을 사용할 수 있으므로  - 런던의 4인 회의실인 Curie에는 표시 이름 LON-CURIE(4)가 있을 수 있습니다.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>전용 리소스 계정에 대한 이름 규칙 결정</li><li>개별 계정을 만들지 또는 대량 프로비전 스크립트를 사용할지 여부를 결정할 수 있습니다.</li></ul>|
| ![다음 단계를 표시하는 아이콘](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 배포를 계획하기 시작하세요.</li></ul>|

### <a name="device-deployment"></a>디바이스 배포

다음으로, 장치 및 할당된 주변 장치를 회의실에 배달할 계획을 만든 다음 설치 및 구성을 진행해야 합니다.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트당 배포를 관리할 사용자 결정</li><li> 사이트에 Microsoft Teams의 공동 작업 막대를 설치하고 구성 및 테스트를 진행할 리소스를 식별합니다.</li></ul>|
| ![다음 단계를 표시하는 아이콘](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 테스트를 시작하세요.</li></ul>|

### <a name="testing"></a>테스트

Microsoft Teams의 공동 작업 막대가 배포된 후 테스트해야 합니다. 디바이스에 로그인하고 예상되는 기능이 배포된 디바이스에서 작동하고 있는지 확인합니다. Microsoft Teams 관리 센터의 장치 탭 아래에  있는 공동  작업 막대 섹션에 장치가 나타나는지 확인하는 것이 좋습니다. 품질 및 성능을 확인하기 위해 여러 테스트 통화 및 모임을 하는 것이 중요합니다.

일반적인 Microsoft Teams 롤아웃의 일부로 CQD(통화 품질 대시보드)에 대한 파일 작성을 구성하고, 품질 추세를 모니터링하고, 환경 품질 검토 프로세스에 참여하는 것이 좋습니다. 자세한 내용은 환경 품질 [검토 가이드를 참조하세요.](https://aka.ms/qerguide)

### <a name="asset-management"></a>자산 관리

배포의 일부로 방 이름, 로그인한 리소스 계정 및 할당된 주변 장치를 통해 자산 레지스터를 업데이트할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[Microsoft Teams 관리 센터를 사용하여 Microsoft Teams의 공동 작업 막대 계정 구성](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
