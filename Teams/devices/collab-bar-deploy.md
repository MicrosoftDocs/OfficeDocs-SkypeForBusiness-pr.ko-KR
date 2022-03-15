---
title: Android에서 Microsoft Teams 룸 배포
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Android에서 배포하는 방법을 알아보 Microsoft Teams 룸 문서를 읽어보아야 합니다.
ms.openlocfilehash: 55e410b1863effd671f08cba663211b78f76e30f
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503545"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Android에서 Microsoft Teams 룸 배포

Android에서 Microsoft Teams 룸 배포는 다음 단계로 세분화할 수 있습니다.

- **사이트 준비** 배포 위치(회의실)가 배포 요구 사항을 충족하는지 확인합니다.
- **서비스 준비** 리소스 계정을 만들고 디바이스에 [할당합니다(](resource-account-ui.md)Microsoft 365 관리 센터. 전용 룸 라이선스를 사용하는 것이 좋습니다. 제대로 라이선스가 부여된 최종 사용자 계정은 Android에서 로그인할 Teams 룸 있습니다.
- **구성 및 배포** 필요한 Teams 룸 디바이스를 설정하고 연결합니다(자세한 내용은 제조업체의 설명서 참조).

Teams 룸 관리하려면 전역 관리자, Teams 서비스 관리자 또는 디바이스 Teams 해야 합니다. 관리자 역할에 대한 자세한 내용은 관리자 Microsoft Teams [Teams](../using-admin-roles.md) 관리자 역할 사용을 참조하세요.

## <a name="site-readiness"></a>사이트 준비

주문된 디바이스가 조직에 전달되는 동안 네트워킹, 시설 및 시청각 팀과 함께 작업하여 배포 요구 사항이 충족되고 각 사이트와 방이 전원, 네트워킹 및 표시 측면에서 준비되어 있는지 확인합니다.

공동 작업 표시줄 사이트에 대한 권장 사항은:

- 최대 5인실
- 전용 리소스 계정
- 터치 지원 디스플레이
- 이더넷 케이블링
- 네트워크에서 미디어에 대해 사용하도록 설정된 QoS(서비스 품질 Microsoft Teams)

물리적 설치 고려 사항은 제조업체의 설명서를 참조하고, 화면을 설치하고 탑재하고 케이블을 실행하기 전에 시청각 팀의 환경을 활용합니다.

> [!TIP]
> 실시간 트래픽에 대한 대역폭 [](../prepare-network.md) Teams 네트워크의 적합성을 평가하기 위해 네트워크 준비를 체크 아웃해야 합니다.
>
> 프록시 서버는 Teams 설치하지 않는 것이 좋습니다. 프록시 서버 및 Teams 대한 자세한 내용은 [프록시](../proxy-servers-for-skype-for-business-online.md) 서버를 Teams.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트가 공동 작업 막대에 대한 사이트 준비 요구 사항을 충족하는지 Microsoft Teams.</li><li>각 사이트에 충분한 대역폭을 제공한지 확인 합니다.</li></ul>|
| ![다음 단계를 표시하는 아이콘입니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>공동 작업 표시줄 배포 및 구성을 계획하기 시작합니다.</li></ul>|

## <a name="service-readiness"></a>서비스 준비

Teams 룸 배포하기 전에 리소스 계정, 최종 Microsoft 365 또는 둘 다 혼합을 사용할지 결정해야 합니다. Microsoft 365 리소스 계정은 Teams, 프로젝터 등 특정 리소스에 전념하는 사서함 및 계정입니다. 이러한 리소스 계정은 사용자가 만들 때 정의한 규칙을 사용하여 모임 초대에 자동으로 응답할 수 있습니다. 개인 Teams 룸 특정 개인에 전념하지 않는 한 해당 리소스 계정을 Microsoft 365 것이 좋습니다.

### <a name="using-a-resource-account"></a>리소스 계정 사용

리소스 계정을 설정하기로 Microsoft 365 경우 해당 리소스에 대한 미팅룸 구입해야 합니다. 미팅룸 라이선스에는 조직의 사용자가 모임 또는 모임을 통해 회의실을 예약할 수 있는 리소스 사서함이 Outlook Teams. 또한 이 라이선스를 사용하면 모임 참가자 간 비디오 및 오디오 회의 및 화면 공유를 사용할 수 있습니다.

외부 전화 번호로 또는 외부 전화 번호로 전화를 걸거나 통화해야 하는 경우 통화 계획 또는 추가 Microsoft 365 Business Voice 라이선스가 필요할 [수 있습니다](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business). 조직에서 직접 라우팅을 사용하도록 설정한 경우 SKU만 미팅룸 필요합니다.

리소스 계정을 만들 때 계정에서 모임 요청을 자동으로 수락하거나 거부할지 여부를 선택할 수 있으며, 모임을 다시 허용하고, 리소스를 예약할 수 있는 시간을 미리 지정할 수 있습니다.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

리소스 계정에 대한 Microsoft 365 자세한 내용은 리소스 계정을 사용하여 리소스 계정 [만들기를 Microsoft 365 관리 센터](resource-account-ui.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>외부 전화 통화를 만들거나 받을지 여부를 결정하고 리소스 계정에 대한 라이선스 요구 사항을 식별합니다.</li></ul>|
| ![다음 단계를 표시하는 아이콘입니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>리소스 계정을 준비합니다.</li></ul>|

## <a name="configuration-and-deployment"></a>구성 및 배포

구성 및 배포 계획은 다음 주요 영역을 다를 수 있습니다.

- 리소스 계정 프로비전
- 디바이스 배포
- Teams 룸 및 주변 장치 구성
- 테스트
- 자산 관리

### <a name="account-provisioning"></a>계정 프로비전

Microsoft 365 리소스 계정을 사용하여 사용자가 공동 작업 표시줄을 예약할 수 있도록 계획하는 경우 이 Microsoft 365 관리 센터 사용하여 리소스 계정 [](resource-account-ui.md) 만들기의 지침에 Microsoft 365 필요한 각 공동 작업 표시줄에 대한 Microsoft 365 리소스 계정을 만들 수 있습니다. 또한 리소스 계정에 미팅룸 라이선스를 추가해야 하고, 외부 전화 번호로 전화를 걸거나 수신하려는 경우 조직에서 직접 라우팅을 사용하지 않는 경우 통화 계획 또는 비즈니스 음성 라이선스를 추가해야 합니다.

개인 사용을 위해 개별 사용자에게 Teams 룸 할당하려는 경우 추가 계정을 설정할 필요가 없습니다. 사용자는 자신의 개인 계정을 사용하여 공동 작업 막대에 로그인할 수 있습니다.

> [!TIP]
> 리소스 계정에 대한 표시 이름을 Microsoft 365 설명하고 쉽게 이해할 수 있도록 합니다. 모임을 검색하고 모임에 추가할 때 사용자가 볼 Teams 룸 이름입니다. *SiteRoom*- *Name**(최대* 회의실 용량)과 같은 규칙을 사용할 수 있으므로 예를 들어 런던의 4인 회의실인 Curie에는 표시 이름 LON-CURIE(4)가 있을 수 있습니다.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>전용 리소스 계정에 대한 이름 규칙을 결정합니다.</li><li>개별 계정을 만들지 대량 프로비전 스크립트를 사용할지 여부를 결정합니다.</li></ul>|
| ![다음 단계를 표시하는 아이콘입니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 배포를 계획하기 시작하세요.</li></ul>|

### <a name="device-deployment"></a>디바이스 배포

다음으로, 디바이스 및 할당된 주변 장치를 회의실에 배달하기 위한 계획을 만든 다음 설치 및 구성을 진행해야 합니다.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트당 배포를 관리할 인원을 결정합니다.</li><li> 사이트에 설치하고 구성 및 Teams 룸 수행할 리소스를 식별합니다.</li></ul>|
| ![다음 단계를 표시하는 아이콘입니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 테스트를 시작하세요.</li></ul>|

### <a name="testing"></a>테스트

배포한 후 Teams 룸 테스트해야 합니다. 로그인하여 Teams 룸 기능이 작동하고 있는지 검사합니다. 관리 센터의 디바이스 탭의 공동 **작업 Teams** 표시 Microsoft Teams 것이 좋습니다. 또한 품질 및 성능을 확인하기 위해 여러 테스트 호출 및 모임을 만드는 것이 중요합니다.

일반 배포의 일부로 Microsoft Teams CQD(전화 품질 대시보드)에 대한 파일 작성을 구성하고 품질 추세를 모니터링하고, 환경 품질 검토 프로세스에 참여하는 것이 좋습니다. 자세한 내용은 환경 품질 검토 [가이드를 참조하세요](../quality-of-experience-review-guide.md).

### <a name="asset-management"></a>자산 관리

배포의 일부로 룸 이름, 로그인된 리소스 계정 및 할당된 주변 장치로 자산 레지스터를 업데이트해야 합니다.

## <a name="related-topics"></a>관련 항목

[관리 센터를 사용하여 Microsoft Teams 룸 계정 Microsoft Teams 구성](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->