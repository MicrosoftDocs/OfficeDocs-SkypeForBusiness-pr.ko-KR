---
title: Microsoft 팀을 위한 공동 작업 표시줄 배포
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
description: Microsoft 팀의 공동 작업 모음 배포에 대해 자세히 알아보려면이 문서를 참조 하세요.
ms.openlocfilehash: 4593d6b42e61efbd7d57f27fd0a10ed8f97b82f5
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268057"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>Microsoft 팀을 위한 공동 작업 표시줄 배포

Microsoft 팀에 대 한 공동 작업 표시줄 배포는 다음 단계로 나눌 수 있습니다.

- **사이트 준비** 배포 위치 (회의실)가 배포 요구 사항을 충족 하는지 확인 합니다.
- **서비스 준비** 리소스 계정을 만들고 장치에 할당 합니다 ([Microsoft 365 관리 센터를 사용 하 여 리소스 계정 만들기 참조](resource-account-ui.md)). 전용 회의실 라이선스를 사용 하는 것이 좋지만, 적절 한 라이선스 최종 사용자 계정이 공동 작업 모음에 로그인 할 수도 있습니다.
- **구성 및 배포** 회의실에서 공동 작업 모음을 설정 하 고 필요한 주변 기기를 연결 하세요 (공동 작업 표시줄에 대 한 제조업체 설명서 참조).

## <a name="site-readiness"></a>사이트 준비

순서가 지정 된 디바이스는 조직에 게 전달 되는 반면, 네트워킹, 시설 및 오디오-시각적 팀과 협력 하 여 배포 요구 사항이 충족 되 고 각 사이트와 채팅방이 전원, 네트워킹, 디스플레이 측면에서 준비 되어 있는지 확인 합니다.

공동 작업 모음 사이트에 대 한 권장 사항은 다음과 같습니다.

- 크기가 최대 4 명까지 회의실
- 전용 리소스 계정
- 터치 가능 디스플레이
- 이더넷 케이블 연결
- Microsoft 팀 미디어의 네트워크에서 사용할 수 있는 QoS (서비스 품질)

물리적 설치 고려 사항은 제조업체의 설명서를 참조 하 고, 화면을 설치 및 탑재 하 고 케이블링을 실행 하기 전에 오디오-시각적 팀의 경험을 활용 하세요.

> [!TIP]
> 대역폭 계획 및 네트워크의 실제 시간 트래픽에 대 한 평가에 대 한 [팀 네트워크 준비](../prepare-network.md) 를 참조 하세요.
>
> 팀 장치와 인터넷 간에 프록시 서버를 배치 하지 않는 것이 좋습니다. 프록시 서버와 팀에 대 한 자세한 내용은 [팀에 대 한 프록시 서버](../proxy-servers-for-skype-for-business-online.md)를 참조 하세요.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트가 Microsoft 팀의 공동 작업 모음에 대 한 사이트 준비 요구 사항을 충족 하는지 확인 합니다.</li><li>각 사이트에 충분 한 대역폭을 제공 했는지 확인 합니다.</li></ul>|
| ![다음 단계를 설명 하는 아이콘](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>공동 작업 모음 배포 및 구성 계획을 시작 합니다.</li></ul>|

## <a name="service-readiness"></a>서비스 준비

공동 작업 모음을 배포 하기 전에 Microsoft 365 리소스 계정, 최종 사용자 계정 또는 두 가지 모두를 함께 사용할지 여부를 결정 해야 합니다. Microsoft 365 리소스 계정은 특정 리소스 (예: 회의실, 프로젝터 등)를 전담 하는 사서함 및 팀 계정입니다. 이러한 리소스 계정은 생성 될 때 사용자가 정의한 규칙을 사용 하 여 모임 초대에 자동으로 응답할 수 있습니다. 개인 사용을 위해 공동 작업 모음이 특정 개인에 게 전담 되지 않는 경우에는 Microsoft 365 리소스 계정을 설정 하는 것이 좋습니다.

### <a name="using-a-resource-account"></a>자원 계정 사용

Microsoft 365 리소스 계정을 설정 하기로 결정 한 경우에는이에 대 한 회의실 라이선스를 구입 해야 합니다. 회의실 라이선스에는 조직의 사용자가 Outlook 또는 팀을 통해 회의실을 예약할 수 있도록 하는 리소스 사서함이 포함 됩니다. 또한 라이선스는 모임 참가자 간에 영상 및 오디오 회의와 화면 공유를 가능 하 게 합니다.

외부 전화 번호로 전화를 걸거나 받아야 하는 경우 Microsoft 365 전화 시스템 또는 Microsoft 365 Business 음성 라이선스도 필요 합니다.

자원 계정을 만들 때 계정에서 모임 요청을 자동으로 수락 하거나 거절 하 고, 되풀이 모임을 허용 하 고, 사용자가 리소스를 예약할 수 있는 시간을 지정할 수 있습니다.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Microsoft 365 리소스 계정의 공동 작업 표시줄에 대 한 자세한 내용은 [microsoft 365 관리 센터를 사용 하 여 자원 계정 만들기](resource-account-ui.md)를 참조 하세요.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>외부 전화를 걸거나 받을 수 있으며 리소스 계정에 대 한 라이선스 요구 사항을 확인할 지 여부를 결정 합니다.</li></ul>|
| ![다음 단계를 설명 하는 아이콘](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>리소스 계정 준비</li></ul>|

## <a name="configuration-and-deployment"></a>구성 및 배포

구성 및 배포 계획에는 다음 주요 영역이 포함 됩니다.

- 리소스 계정 프로 비전
- 장치 배포
- Microsoft 팀 응용 프로그램 및 주변 장치 구성에 대 한 공동 작업 모음
- 테스트가
- 자산 관리

### <a name="account-provisioning"></a>계정 프로비저닝

Microsoft 365 리소스 계정을 사용 하 여 사용자를 예약할 계획 이라면 [microsoft 365 관리 센터를 사용 하 여 자원 계정 만들기](resource-account-ui.md) 의 지침에 따라 필요한 각 공동 작업 표시줄에 대 한 microsoft 365 리소스 계정을 만듭니다. 또한 사용자는 리소스 계정에 회의실 라이선스를 추가 하 고 외부 전화 번호, 전화 시스템 또는 비즈니스 음성 라이선스에 대 한 통화를 보내거나 받으려고 합니다.

개인 사용을 위해 개별 사용자에 게 공동 작업 막대를 할당 하려는 경우에는 추가 계정을 설정할 필요가 없습니다. 사용자는 개인 계정을 사용 하 여 공동 작업 모음에 로그인 할 수 있습니다.

> [!TIP]
> Microsoft 365 리소스 계정의 표시 이름을 설명 하 고 이해 하기 쉽게 만듭니다. Microsoft 팀의 공동 작업 막대를 검색 하 고 모임에 추가할 때 사용자에 게 표시 되는 이름입니다. *사이트* - *공간 이름*(*최대 회의실 용량*)과 같은 규칙을 사용할 수 있기 때문에, 예를 들어, London의 4 인칭 모임 채팅방에 표시 이름 LON-curie (4)가 있을 수 있습니다.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>전용 리소스 계정에 대 한 명명 규칙을 결정 합니다.</li><li>개별 계정을 만들지 아니면 대량 프로 비전 스크립트를 사용할지 여부를 결정 합니다.</li></ul>|
| ![다음 단계를 설명 하는 아이콘](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>장치 배포 계획을 시작 합니다.</li></ul>|

### <a name="device-deployment"></a>장치 배포

다음으로, 장치 및 할당 된 주변 기기 장치를 채팅방에 전달 하는 계획을 만든 다음 설치 및 구성을 진행 해야 합니다.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트별 배포를 관리할 사용자를 결정 합니다.</li><li> 사이트에서 Microsoft 팀에 대 한 공동 작업 모음을 설치할 리소스를 식별 하 고 구성 및 테스트를 안내 합니다.</li></ul>|
| ![다음 단계를 설명 하는 아이콘](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>장치 테스트를 시작 합니다.</li></ul>|

### <a name="testing"></a>테스트가

Microsoft 팀의 공동 작업 모음을 배포한 후에는 테스트 해야 합니다. 장치에 로그인 하 고 예상 되는 기능이 배포 된 장치에서 작동 하는지 확인 합니다. Microsoft 팀 관리 센터의 **장치** 탭에 있는 **공동 작업 모음** 섹션에 장치가 표시 되는지 확인 하는 것이 좋습니다. 품질과 성능을 확인 하기 위해 다양 한 테스트 통화와 모임을 수행 하는 것도 중요 합니다.

일반 Microsoft 팀을 출시 하는 동안, 통화 품질 대시보드 (CQD)에 대 한 빌드 파일을 구성 하 고, 품질 추세를 모니터링 하 고, 경력의 품질 검토 프로세스에 참여 하는 것이 좋습니다. 자세한 내용은 [경험 치 리뷰 가이드](https://aka.ms/qerguide)를 참조 하세요.

### <a name="asset-management"></a>자산 관리

배포의 일환으로, 자산 이름, 로그인 한 리소스 계정 및 할당 된 주변 기기 장치를 사용 하 여 자산 등록기를 업데이트 하는 것이 좋습니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 팀 관리 센터를 사용 하 여 Microsoft 팀의 공동 작업 모음에 대 한 계정 구성](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
