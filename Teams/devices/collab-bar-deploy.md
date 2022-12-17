---
title: Android에서 Microsoft Teams 룸 배포
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Devices
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Android에서 Microsoft Teams 룸 배포하는 방법에 대해 알아보려면 이 문서를 참조하세요.
ms.openlocfilehash: 52b865879db3941b5631d7b22c25bd8f6e4d3ce6
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438416"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Android에서 Microsoft Teams 룸 배포

Android에서 Microsoft Teams 룸 배포는 다음 단계로 나눌 수 있습니다.

- **사이트 준비 상태** 배포 위치(룸)가 배포 요구 사항을 충족하는지 확인합니다.
- **서비스 준비 상태** 리소스 계정을 만들고 디바이스에 할당합니다([Microsoft 365 관리 센터 사용하여 리소스 계정 만들기 참조](resource-account-ui.md)). 전용 회의실 라이선스를 사용하는 것이 좋지만, 적절하게 라이선스가 부여된 최종 사용자 계정은 Android에서 Teams 룸 로그인할 수도 있습니다.
- **구성 및 배포** Teams 룸 설정하고 필요한 주변 장치를 연결합니다(자세한 내용은 제조업체 설명서 참조).

Teams 룸 관리하려면 전역 관리자, Teams 서비스 관리자 또는 Teams 디바이스 관리자여야 합니다. 관리자 역할에 대한 자세한 내용은 [Microsoft Teams 관리자 역할을 사용하여 Teams 관리를 참조하세요](../using-admin-roles.md).

## <a name="site-readiness"></a>사이트 준비 상태

주문된 디바이스가 조직에 배달되는 동안 네트워킹, 시설 및 시청각 팀과 협력하여 배포 요구 사항이 충족되고 각 사이트와 공간이 전원, 네트워킹 및 디스플레이 측면에서 준비되었는지 확인합니다.

Android 사이트의 Teams 룸 권장 사항은 다음과 같습니다.

- 최대 5명까지 객실
- 전용 리소스 계정
- 터치 사용 디스플레이
- 이더넷 케이블 연결
- Microsoft Teams 미디어에 대해 네트워크에서 사용할 수 있는 QoS(서비스 품질)

물리적 설치 고려 사항은 제조업체의 설명서를 참조하세요. 이 설명서가 있는 경우 화면을 설치 및 탑재하고 케이블을 실행하기 전에 시청각 팀의 환경을 활용하세요.

> [!TIP]
> 대역폭 계획 및 실시간 트래픽 [에 대한 네트워크의](../prepare-network.md) 적합성을 평가하기 위해 Teams용 네트워크 준비를 확인하세요.
>
> Teams 디바이스와 인터넷 사이에 프록시 서버를 배치하지 않는 것이 좋습니다. 프록시 서버 및 Teams에 대한 자세한 내용은 [Teams용 프록시 서버를 확인하세요](../proxy-servers-for-skype-for-business-online.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트가 Android에서 Teams 룸 대한 사이트 준비 요구 사항을 충족하는지 확인합니다.</li><li>각 사이트에 대해 충분한 대역폭을 제공했는지 확인합니다.</li></ul>|
| ![다음 단계를 보여 주는 아이콘입니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>Android 배포 및 구성에서 Teams 룸 계획하기 시작합니다.</li></ul>|

## <a name="service-readiness"></a>서비스 준비

Teams 룸 배포하기 전에 Microsoft 365개의 리소스 계정, 최종 사용자 계정 또는 둘 다의 혼합을 사용할지 결정해야 합니다. Microsoft 365개의 리소스 계정은 회의실, 프로젝터 등과 같은 특정 리소스 전용의 사서함 및 Teams 계정입니다. 이러한 리소스 계정은 만들 때 정의하는 규칙을 사용하여 모임 초대에 자동으로 응답할 수 있습니다. Teams 룸 개인 전용인 경우가 아니면 Microsoft 365 리소스 계정을 설정하는 것이 좋습니다.

### <a name="using-a-resource-account"></a>리소스 계정 사용

Microsoft 365 리소스 계정을 설정하려는 경우 회의실 라이선스를 구입해야 합니다. 회의실 라이선스에는 조직의 사용자가 Outlook 또는 Teams를 통해 회의실을 예약할 수 있는 리소스 사서함이 포함되어 있습니다. 또한 라이선스를 통해 모임 참가자 간에 비디오 및 오디오 회의 및 화면 공유가 가능합니다.

외부 전화 번호를 받거나 전화를 걸어야 하는 경우 통화 플랜 또는 Microsoft 365 Business Voice [추가 기능 라이선스](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)가 필요할 수 있습니다. 조직에서 직접 라우팅을 사용하도록 설정한 경우 회의실 SKU만 필요합니다.

리소스 계정을 만들 때 계정에서 모임 요청을 자동으로 수락하거나 거부할지, 되풀이 모임을 허용할지, 사용자가 리소스를 미리 예약할 수 있는 정도를 지정할지 선택할 수 있습니다.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Microsoft 365개 리소스 계정에 대한 자세한 내용은 [Microsoft 365 관리 센터 사용하여 리소스 계정 만들기를](resource-account-ui.md) 참조하세요.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>외부 전화를 걸거나 받을지 여부를 결정하고 리소스 계정에 대한 라이선스 요구 사항을 식별합니다.</li></ul>|
| ![다음 단계를 보여 주는 아이콘입니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>리소스 계정을 준비합니다.</li></ul>|

## <a name="configuration-and-deployment"></a>구성 및 배포

구성 및 배포 계획은 다음과 같은 주요 영역을 다룹니다.

- 리소스 계정 프로비저닝
- 디바이스 배포
- 애플리케이션 및 주변 장치 구성 Teams 룸
- 테스트
- 자산 관리

### <a name="account-provisioning"></a>계정 프로비저닝

사용자가 Android 디바이스에서 Teams 룸 예약할 수 있도록 Microsoft 365 리소스 계정을 사용하려는 경우 [Microsoft 365 관리 센터 사용하여 리소스 계정 만들기](resource-account-ui.md)의 지침에 따라 Android 디바이스에서 필요한 각 Teams 룸 대한 Microsoft 365 리소스 계정을 만듭니다. 또한 리소스 계정에 회의실 라이선스를 추가해야 하며, 조직에서 직접 라우팅을 사용하지 않는 경우 외부 전화 번호로 전화를 걸거나 외부 전화 번호로 전화를 걸거나 받으려면 통화 플랜 또는 Business Voice 라이선스를 추가해야 합니다.

개인 용도로 개별 사용자에게 Teams 룸 할당하려는 경우 추가 계정을 설정할 필요가 없습니다. 사용자는 개인 계정을 사용하여 Android 디바이스에서 Teams 룸 로그인할 수 있습니다.

> [!TIP]
> Microsoft 365 리소스 계정의 표시 이름을 설명적이고 이해하기 쉽게 만듭니다. 다음은 모임에 Teams 룸 검색하고 추가할 때 사용자에게 표시되는 이름입니다. *사이트*-*룸 이름*(*최대 회의실 용량*)과 같은 규칙을 사용할 수 있으므로 예를 들어 런던의 4인용 회의실인 Curie에는 표시 이름 LON-CURIE(4)가 있을 수 있습니다.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>전용 리소스 계정에 대한 명명 규칙을 결정합니다.</li><li>개별 계정을 만들 것인지 아니면 대량 프로비저닝 스크립트를 사용할지 결정합니다.</li></ul>|
| ![다음 단계를 보여 주는 아이콘입니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 배포 계획을 시작합니다.</li></ul>|

### <a name="device-deployment"></a>디바이스 배포

다음으로, 디바이스와 할당된 주변 장치를 회의실로 배달하는 계획을 만든 다음 설치 및 구성을 진행해야 합니다.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트별 배포를 관리할 사용자를 결정합니다.</li><li> 사이트에 Teams 룸 설치하고 구성 및 테스트를 수행할 리소스를 식별합니다.</li></ul>|
| ![다음 단계를 보여 주는 아이콘입니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 테스트를 시작합니다.</li></ul>|

### <a name="testing"></a>테스트

Teams 룸 배포한 후에는 테스트해야 합니다. Teams 룸 로그인하고 예상 기능이 작동하는지 확인합니다. Microsoft Teams 관리 센터의 **Teams 디바이스** 탭 아래에 있는 **Android의 Teams 룸 섹션에** 표시되는지 확인하는 것이 좋습니다. 또한 품질 및 성능을 확인하기 위해 여러 테스트 호출 및 모임을 만드는 것도 중요합니다.

일반적인 Microsoft Teams 출시의 일환으로 CQD(통화 품질 대시보드)에 대한 빌드 파일을 구성하고, 품질 추세를 모니터링하고, 환경 품질 검토 프로세스에 참여하는 것이 좋습니다. 자세한 내용은 [환경 품질 검토 가이드](../quality-of-experience-review-guide.md)를 참조하세요.

### <a name="asset-management"></a>자산 관리

배포의 일부로 자산 레지스터를 회의실 이름, 로그인한 리소스 계정 및 할당된 주변 장치 디바이스로 업데이트하려고 합니다.

## <a name="related-topics"></a>관련 주제

[회의실 및 공유 Teams 디바이스에 대한 리소스 계정 만들기](../rooms/with-office-365.md)