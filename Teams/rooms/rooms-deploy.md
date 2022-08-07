---
title: Microsoft Teams 룸 배포
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 배포 단계를 포함하여 Microsoft Teams 룸 배포하는 방법에 대해 알아보려면 이 문서를 참조하세요.
ms.openlocfilehash: 9dbb45581467cb0f948ce7b5fb62dcfea1186918
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271783"
---
# <a name="deployment-overview"></a>배포 개요

Microsoft Teams 룸 배포는 기본적으로 단계로 나뉩니다.

- 배포 위치(공간)가 배포 종속성을 충족하는지 확인
- Microsoft Teams 또는 비즈니스용 Skype 및 Exchange 계정을 만들고 Teams 룸 할당([Microsoft Teams 룸 계정 구성 참조](rooms-configure-accounts.md))
- (선택 사항) 시스템에 대한 Azure Monitor 설정([Azure Monitor를 사용하여 Microsoft Teams 룸 관리 배포](azure-monitor-deploy.md) 참조)
- 모임 공간에서 Teams 룸 설정하고 필요한 주변 장치 연결(디바이스 집합에 대한 OEM 설명서 참조)

## <a name="site-readiness"></a>사이트 준비 상태 

주문된 디바이스가 조직에 배달되는 동안 네트워킹, 시설 및 AV 팀과 협력하여 배포 종속성이 충족되고 각 사이트 및 공간이 전원, 네트워킹 및 표시 측면에서 준비되었는지 확인합니다. 또한 물리적 설치 요구 사항이 충족되는지 확인합니다. 물리적 설치 고려 사항은 공급업체에 문의하고 화면을 설치 및 탑재하고 케이블을 실행할 때 AV 팀의 환경을 활용하세요.

아래 계획 지침 링크에서 이러한 종속성에 대해 자세히 알아볼 수 있습니다.

-   [네트워크 가용성 확인](rooms-prep.md#check-network-availability)
-   [인증서](rooms-prep.md#certificates)
-   [프록시](rooms-prep.md#proxy)

**Pro 팁** - 프록시 서버를 사용하여 Teams에 대한 액세스를 제공해야 하는 경우 먼저 [이 문서를 검토](../proxy-servers-for-skype-for-business-online.md)합니다. 프록시 서버를 통해 Microsoft Teams 실시간 미디어 트래픽에 관해서는 프록시 서버를 모두 우회하는 것이 좋습니다. Microsoft Teams 트래픽은 이미 암호화되어 있으므로 프록시 서버는 보안을 확보하지 못하며 실시간 트래픽에 대기 시간을 추가합니다. 광범위한 배포의 일환으로 대역폭을 계획하고 실시간 트래픽에 대한 네트워크의 적합성을 평가하기 [위해 Teams용 네트워크 준비](../prepare-network.md) 의 지침을 따르는 것이 좋습니다.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![사이트를 확인합니다.](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트가 Microsoft Teams 룸 대한 주요 요구 사항을 충족하는지 확인합니다.</li><li>각 사이트에 충분한 대역폭을 제공했는지 확인합니다.</li></ul>| 
| ![디바이스 배포를 계획합니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 배포 및 구성 계획을 시작합니다.</li></ul>| 

## <a name="service-readiness"></a>서비스 준비

Microsoft Teams 룸 배포를 준비하려면 다음 키, 중앙 작업을 수행합니다.

-   Microsoft Teams 룸 리소스 계정을 정의합니다.
-   azure Active Directory에 Teams 룸 조인하는 경우 동적 멤버 자격을 가진 Azure AD 그룹을 준비하여 모든 Teams 룸 리소스 계정을 보유합니다. 이렇게 하면 조건부 액세스 정책 적용과 같은 향후 관리가 간소화됩니다. Azure AD 동적 그룹을 가장 쉽게 활용하려면 Teams 룸 리소스 계정을 고유하게 식별하는 명명 규칙을 결정합니다.
-   Teams 룸 Active Directory에 조인하는 경우 Microsoft Teams 룸 컴퓨터 및 리소스 계정을 보유하도록 조직 구성 단위 및 Active Directory 그룹을 준비하고 필요에 따라 PowerShell 원격을 사용하도록 GPO(그룹 정책 개체)를 준비합니다.

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>Microsoft Teams 룸 리소스 계정 기능 정의 

Microsoft Teams 룸 배포에서 사용하도록 설정하기로 결정한 공동 작업 시나리오에 따라 사용하도록 설정하는 각 Microsoft Teams 룸 할당하는 기능과 기능을 결정해야 합니다.

| **시나리오** | **설명** | **Microsoft Teams 룸 서비스 계정 기능** |
|---------- |------------- | --- |
| 대화형 모임            | 음성, 비디오 및 화면 공유 사용 Microsoft Teams 룸 예약 가능한 리소스로 만들기                     | Microsoft Teams 또는 exchange에 대해 사용하도록 설정된 비즈니스용 Skype;(리소스 사서함) |
| 전화 접속 회의            | 콘솔에서 "새 모임"을 탭할 때 오디오 회의 전화 번호가 있어야 합니다. | 오디오 회의에 사용하도록 설정                                          |
| 아웃바운드/인바운드 PSTN 호출 | Microsoft Teams 룸 콘솔에서 PSTN 호출을 만들고 받을 수 있도록 설정                                         | 전화 시스템에 사용하도록 설정                                                |

Microsoft Teams 룸 계정에 대한 자세한 내용은 [Microsoft Teams 룸 대한 계정 구성을](rooms-configure-accounts.md) 참조하세요.


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![시나리오 지원.](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>지원할 시나리오를 결정하고 Microsoft Teams 룸 리소스 계정에 대한 라이선스 요구 사항을 식별합니다.</li></ul>| 
| ![호스트 컴퓨터를 준비합니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>컴퓨터 및 리소스 계정을 호스트할 준비를 합니다.</li></ul>| 


_샘플 Microsoft Teams 룸 리소스 계정 계획 테이블_

| **사이트**  | **방 이름** | **회의실 유형** | **향후 회의실 기능**                                                 | **Microsoft Teams 룸 계정 기능**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 런던 본사 | 퀴리         | 중형        | 화면 1개, 오디오 및 비디오 및 프레젠테이션 <br>전화 접속 회의 액세스<br> PSTN 액세스  | Exchange에 사용하도록 설정(리소스 사서함) <br>오디오 회의에 사용하도록 설정 <br>전화 시스템에 사용하도록 설정 |
| 시드니 본사 | 힐          | 대형         | 2 화면, 오디오 및 비디오 플러스 프레젠테이션<br>전화 접속 회의 액세스<br> PSTN 액세스  | 비즈니스용 Skype 사용하도록 설정 <br>Exchange에 사용하도록 설정(리소스 사서함)<br> 오디오 회의에 사용하도록 설정 <br>전화 시스템에 사용하도록 설정 |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>Microsoft Teams 룸 및 리소스 계정 호스트 준비(선택 사항)

Microsoft Teams 룸 및 리소스 계정을 관리하고 보고할 수 있도록 하려면 온-프레미스 Active Directory 또는 Azure Active Directory(Azure AD)를 준비합니다. 

모든 Microsoft Teams 룸 리소스 계정을 추가할 온-프레미스 Active Directory 또는 Azure Active Directory 그룹을 정의합니다. Azure Active Directory를 사용하는 경우 동적 그룹을 사용하여 그룹에서 리소스 계정을 자동으로 추가하고 제거하는 것이 좋습니다.

모든 Microsoft Teams 룸 컴퓨터 계정(도메인에 가입된 경우)을 보유하도록 온-프레미스 Active Directory 계층 구조에 하나의 조직 구성 단위를 정의하고, Microsoft Teams 룸 모든 사용자 계정을 보유하는 하나의 조직 구성 단위를 정의합니다. 도메인에 가입된 Microsoft Teams 룸 적용하려는 정책만 적용하려면 그룹 정책 상속을 사용하지 않도록 설정합니다.

Microsoft Teams 룸 컴퓨터 계정을 포함하는 조직 구성 단위에 할당된 그룹 정책 개체를 만듭니다. 이 작업을 사용하여 다음을 수행합니다. 

-   [전원 및 로컬 계정 설정을 지정합니다](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Windows 업데이트 사용하도록 설정합니다.
-   PowerShell 원격을 사용하도록 설정합니다. 스크립트를 실행하도록 시작 스크립트를 구성할 수 있습니다. Enable-PSRemoting -Force

PowerShell을 사용하여 구성 정보 가져오기 및 설정을 비롯한 여러 원격 관리 작업을 수행할 수 있습니다. PowerShell 원격 관리를 수행 *하려면* 먼저 PowerShell 원격을 사용하도록 설정해야 하며 배포 프로세스의 일부로 간주하거나 그룹 정책 통해 구성해야 합니다. 이러한 기능 및 사용 설정에 대한 자세한 내용은 [유지 관리 및 작업을 참조하세요](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>구성 및 배포 

구성 및 배포 계획은 다음과 같은 주요 영역을 다룹니다.

-   리소스 계정 프로비전
-   디바이스 소프트웨어 설치
-   디바이스 배포
-   Microsoft Teams 룸 애플리케이션 및 주변 장치 구성
-   테스트
-   자산 관리

### <a name="resource-account-provisioning"></a>리소스 계정 프로비전 

각 Microsoft Teams 룸 디바이스에는 Microsoft Teams 또는 비즈니스용 Skype 및 Exchange 둘 다에 대해 사용하도록 설정해야 하는 전용 및 고유한 리소스 계정이 필요합니다. 이 계정에는 Exchange에서 호스트되는 회의실 사서함이 있어야 합니다. 디바이스가 들어오는 모임 요청을 자동으로 수락할 수 있도록 일정 처리를 구성해야 합니다. 이러한 계정을 만드는 방법에 대한 자세한 내용은 [Microsoft Teams 룸 대한 계정 구성](rooms-configure-accounts.md)을 참조하세요. 

**Pro 팁** - 각 Microsoft Teams 룸 네트워크에 유효하고 고유한 컴퓨터 이름이 있어야 합니다. 많은 모니터링 및 경고 시스템은 컴퓨터 이름을 키 식별자로 표시하므로 지원 담당자가 작업이 필요한 것으로 플래그가 지정된 Microsoft Teams 룸 쉽게 찾을 수 있도록 Microsoft Teams 룸 배포에 대한 명명 규칙을 개발하는 것이 중요합니다. 예를 들어 MTR-Site- *Room Name*(MTR-LON-CURIE) 패턴을 사용할 수 있습니다. 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![는 명명 규칙을 결정합니다.](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>Microsoft Teams 룸 리소스 계정에 대한 명명 규칙을 결정합니다.</li><li>개별 계정을 만들 것인지 아니면 대량 프로비전 스크립트를 사용할지 결정합니다.</li></ul>| 
| ![다음 단계를 수행합니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 배포 계획을 시작합니다.</li></ul>| 


### <a name="device-software-installation"></a>디바이스 소프트웨어 설치 

Teams 룸 OEM(원래 장비 제조업체)에 의해 사전 설치됩니다.

[Microsoft Azure Monitor](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor)를 사용하여 Microsoft Teams 룸 배포를 모니터링하고 가용성, 하드웨어/소프트웨어 오류 및 Microsoft Teams 룸 애플리케이션 버전을 보고하는 방법에 대한 지침을 제공합니다. Microsoft Operations Management Suite를 사용하기로 결정한 경우 소프트웨어 설치 프로세스의 일부로 Operations Management Suite 에이전트를 설치하고 작업 영역에 대한 작업 영역 연결 정보를 구성해야 합니다. 

추가 고려 사항은 Microsoft Teams 룸 도메인에 가입될지 여부입니다. 도메인 가입의 이점에 대한 정보는 [Microsoft Teams 룸 대한 그룹 정책 구성](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)에서 찾을 수 있습니다. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![의사 결정 지점 디바이스 이름 지정](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>배포하는 동안 사용할 Microsoft Teams 룸 리소스 계정 명명 규칙을 결정합니다.</li><li>Microsoft Teams 룸 디바이스를 도메인에 가입할지 여부를 결정합니다. </li><li>Azure Monitor를 사용하여 Microsoft Teams 룸 배포를 모니터링할지 여부를 결정합니다.</li> 
| ![다음 단계에서는 디바이스를 계획합니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 배포 방법을 계획하기 시작합니다.</li></ul>| 


### <a name="device-deployment"></a>디바이스 배포

Microsoft Teams 룸 리소스 계정을 만들고 관리하는 방법을 결정한 후 디바이스 및 할당된 주변 장치를 회의실로 배송하는 계획을 만든 다음 설치 및 구성을 진행합니다.


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![사이트별 배포를 관리합니다.](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트별 배포를 관리할 사용자를 결정합니다.</li><li> 사이트에 Microsoft Teams 룸 설치하고 구성 및 테스트를 수행할 리소스를 식별합니다.</li></ul>| 
| ![디바이스 테스트를 시작합니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 테스트를 시작합니다.</li></ul>| 

_샘플 배포 테이블_

| **사이트**  | **방 이름** | **회의실 유형** | **Microsoft Teams 룸 시스템**  | **주변 장치**  | **컴퓨터 이름 Microsoft Teams 룸**  | **리소스 계정 Microsoft Teams 룸**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 런던 본사 | 퀴리         | 중형        |                                   |                  |                                          |                                             |
| 시드니 본사 | 힐          | 대형         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams 룸 애플리케이션 및 주변 장치 구성 

각 Microsoft Teams 룸 시스템을 물리적으로 배포하고 지원되는 주변 장치를 연결한 후에는 Teams 룸 Microsoft Teams에 로그인할 수 있도록 Microsoft Teams 룸 리소스 계정 및 암호를 할당하도록 Microsoft Teams 룸 애플리케이션을 구성해야 합니다. 비즈니스용 Skype 및 Exchange.

각 Microsoft Teams 룸 시스템을 수동으로 구성할 수 있습니다. 또는 중앙에 저장된 Teams 룸 XML 구성 파일을 사용하여 애플리케이션 설정을 관리할 수 있습니다.

XML 구성 파일을 사용하는 방법에 대한 자세한 내용은 XML 구성 파일을 [사용하여 원격으로 Microsoft Teams 룸 콘솔 설정 관리를](xml-config-file.md) 참조하세요. 

[원격 PowerShell](rooms-operations.md#remote-management-using-powershell)을 사용하여 보고 요구 사항에 대한 Microsoft Teams 룸 구성을 끌어올 수 있습니다. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![의사 결정 지점 구성.](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>각 Microsoft Teams 룸 시스템을 수동으로 구성할지 또는 중앙 XML 파일(Microsoft Teams 룸 디바이스당 하나씩)을 사용할지 여부를 결정합니다.</li></ul>| 
| ![원격 접근 방식을 다음 단계로 진행합니다.](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>원격 관리 접근 방식을 정의합니다.</li></ul>| 

### <a name="testing"></a>테스트

Teams 룸 배포된 후에는 테스트해야 합니다. [Microsoft Teams 룸 도움말](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us)에 나열된 기능이 배포된 디바이스에서 작동하는지 확인합니다. 배포 팀에서 Microsoft Teams 룸 Teams 관리 센터에 표시되는지 확인하는 것이 좋습니다. 또한 품질을 확인하기 위해 여러 번의 테스트 통화 및 모임을 하는 것이 중요합니다. 자세한 내용은 이 [유용한 배포 검사 목록을 참조하세요](console.md#microsoft-teams-rooms-deployment-checklist).

일반 Teams 또는 비즈니스용 Skype 출시의 일환으로 CQD(통화 품질 대시보드)에 대한 파일 빌드를 구성하고, 품질 추세를 모니터링하고, 환경 품질 검토 프로세스에 참여하는 것이 좋습니다. 자세한 내용은 [Teams의 통화 품질 개선 및 모니터링을 참조하세요](../monitor-call-quality-qos.md). 

### <a name="asset-management"></a>자산 관리

배포의 일부로 자산 레지스터를 회의실 이름, Microsoft Teams 룸 이름, Microsoft Teams 룸 리소스 계정 및 할당된 주변 장치로 업데이트하려고 합니다. 

_샘플 자산 테이블_

| **사이트**  | **방 이름** | **회의실 유형** | **Microsoft Teams 룸 직렬 번호입니다.**  | **주변 장치/ 직렬 nos./ 포트**  | **컴퓨터 이름 Microsoft Teams 룸**  | **Microsoft Teams 룸 서비스 계정**  | **배포된 날짜** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 런던 본사 | 퀴리         | 중형        |                                          |                                          |                                          |                                            |                   |
| 시드니 본사 | 힐          | 대형         |                                          |                                          |                                          |                                            |                   |
