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
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 이 문서에서는 배포 단계를 포함하여 Microsoft Teams 룸 방법을 알아보고자 합니다.
ms.openlocfilehash: 6c35b8c8456659c10f444defc9ff9f4809c032965f01a85c59d41cc67e6fa367
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342813"
---
# <a name="deployment-overview"></a>배포 개요

기본적으로 Microsoft Teams 룸 배포는 다음 단계로 세분화됩니다.

- 배포 위치(회의실)가 배포 종속성에 충족하는지 확인
- Microsoft Teams 또는 비즈니스용 Skype Exchange 계정을 만들고 콘솔 디바이스에 할당합니다 [Microsoft Teams 룸(계정](rooms-configure-accounts.md)구성 참조)
- Microsoft Surface 태블릿을 콘솔로 Microsoft Teams 룸 다시 구현합니다(Microsoft Teams 룸 콘솔 구성 또는 대량 Microsoft Teams 룸 배포 가이드 [참조)](rooms-scale.md) [](console.md)
- (선택 사항) 시스템에 대한 Microsoft Operations Management Suite [설정(Azure Monitor를](azure-monitor-deploy.md) 사용하여 Microsoft Teams 룸 관리 배포 참조)
- 회의실에서 콘솔 설정 및 필요한 주변 장치 연결(디바이스 집합에 대한 OEM 설명서 참조)

AV 기술은 마지막 작업에 사용할 수 있지만 조직의 IT 부서는 프로세스의 다른 부분을 수행해야 합니다. 


## <a name="site-readiness"></a>사이트 준비 

주문된 디바이스가 조직에 전달되는 동안 네트워킹 및 시설 및 AV 팀과 함께 작업하여 배포 종속성이 충족되고 각 사이트와 방이 전원, 네트워킹 및 표시 측면에서 준비되어 있는지 확인합니다. 또한 물리적 설치 요구 사항을 충족하는지 확인합니다. 물리적 설치 고려 사항은 공급업체 사이트를 방문하여 화면을 설치 및 탑재하고 케이블을 실행하는 경우 AV 팀의 환경을 활용합니다.

이러한 종속성에 대한 자세한 내용은 아래 계획 지침 링크에서 찾을 수 있습니다.

-   [네트워크 가용성 확인](rooms-prep.md#check-network-availability)
-   [인증서](rooms-prep.md#certificates)
-   [프록시](rooms-prep.md#proxy)

**Pro 팁** - 프록시 서버를 사용하여 온라인 또는 Teams 비즈니스용 Skype 먼저 이 문서를 [검토합니다.](../proxy-servers-for-skype-for-business-online.md) 프록시 서버를 통해 트래픽을 비즈니스용 Skype 경우 프록시 서버를 모두 우회하는 것이 좋습니다. 비즈니스용 Skype 트래픽이 이미 암호화되어 있으므로 프록시 서버는 보안이 더 이상 유지되지 않습니다. 광범위한 배포의 일환으로 대역폭 계획 및 실시간 트래픽에 대한 네트워크의 Teams 네트워크의 적합성을 평가하기 위해 네트워크 [준비의](../prepare-network.md) 지침을 따르는 것이 좋습니다.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![사이트 확인](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트가 웹 사이트에 대한 주요 요구 사항을 충족하는지 Microsoft Teams 룸.</li><li>각 사이트에 충분한 대역폭을 제공한지 확인 합니다.</li></ul>| 
| ![디바이스 배포 계획](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 배포 및 구성을 계획하기 시작하세요.</li></ul>| 

## <a name="service-readiness"></a>서비스 준비

배포에 Microsoft Teams 룸 다음 키, 중앙 작업을 수행합니다.

-   서비스 Microsoft Teams 룸 기능을 정의합니다.
-   조직 단위 및 Active Directory 그룹을 준비하여 Microsoft Teams 룸 컴퓨터 및 서비스 계정을 보유하고, 선택적으로 PowerShell 리모팅을 사용하도록 GPOS(그룹 정책 개체)를 준비합니다.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>서비스 Microsoft Teams 룸 기능 정의 

배포에서 사용하도록 결정한 공동 작업 시나리오에 따라 Microsoft Teams 룸 각 서비스 계정에 할당하는 기능과 Microsoft Teams 룸 결정해야 합니다.

| **시나리오** | **설명** | **Microsoft Teams 룸 계정 기능** |
|---------- |------------- | --- |
| 대화형 모임            | 음성, 비디오 및 화면 공유 사용; 예약 가능한 Microsoft Teams 룸 만들기                     | 비즈니스용 Skype 사용하도록 설정되어 Exchange(리소스 사서함) |
| 전화 접속 회의            | 전화 접속 회의  좌표를 사용하여 Microsoft Teams 룸 본체에서 직접 시작된 모임 사용 | 오디오 회의에 사용하도록 설정                                          |
| 아웃바운드/인바운드 PSTN 호출 | PSTN Microsoft Teams 룸 콘솔에서 PSTN 호출을 걸고 받을 수 있도록 설정                                         | 전화 시스템                                                |

계정의 Microsoft Teams 룸 자세한 내용은 에 대한 계정 [구성을 Microsoft Teams 룸.](rooms-configure-accounts.md)


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![시나리오 지원](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>지원할 시나리오를 결정하고 서비스 계정에 대한 Microsoft Teams 룸 식별합니다.</li></ul>| 
| ![호스트 머신 준비](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>컴퓨터 및 서비스 계정을 호스트할 준비를 합니다.</li></ul>| 


_샘플 Microsoft Teams 룸 계정 계획 테이블_

| **사이트**  | **방 이름** | **룸 유형** | **향후 방 기능**                                                 | **Microsoft Teams 룸 계정 기능**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 런던 본사 | Curie         | 중형        | 1 화면, 오디오 및 비디오 및 프레젠테이션 <br>전화 접속 회의 액세스<br> PSTN 액세스  | 비즈니스용 Skype 사용하도록 설정되어 Exchange(리소스 사서함) <br>오디오 회의에 사용하도록 설정 <br>전화 시스템 |
| 시드니 본사 | 힐          | 대형         | 2 화면, 오디오 및 비디오 및 프레젠테이션<br>전화 접속 회의 액세스<br> PSTN 액세스  | 비즈니스용 Skype 사용하도록 설정되어 Exchange(리소스 사서함)<br> 오디오 회의에 사용하도록 설정 <br>전화 시스템 |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>컴퓨터 및 서비스 Microsoft Teams 룸 호스트 준비(선택 사항)

컴퓨터 및 서비스 계정을 관리하고 보고할 수 Microsoft Teams 룸 Azure AD(On-Premises Active Directory 또는 Azure Active Directory 준비하세요. 

모든 Microsoft Teams 룸 서비스(사용자) 계정을 추가하기 위해 프레미스 Active Directory 또는 Azure AD 그룹을 정의한 다음, Get-CSUserSession PowerShell cmdlet을 사용하여 사용 Microsoft Teams 룸 합니다. 예를 들어 SkypeRoomSystemsv2-Service-Accounts라는 그룹을 만들 수 있습니다. 


모든 컴퓨터 계정(도메인에 Microsoft Teams 룸 경우)을 보유하도록 모든 조직 단위를 보유하도록 프레미스 Active Directory 또는 Azure AD 계층 구조에서 하나의 조직 단위를 정의하고 모든 사용자 계정을 Microsoft Teams 룸 있습니다. 컴퓨터 계정에 대한 조직 단위를 Microsoft Teams 룸 상속을 사용 안 하도록 고려하여 도메인에 조인된 도메인에 적용하려는 정책만 적용하도록 Microsoft Teams 룸. 

사용자 컴퓨터 계정이 포함된 조직 단위에 할당된 그룹 Microsoft Teams 룸 만듭니다. 다음에 이 기능을 사용 합니다. 

-   [전원 및 로컬 계정 설정을 설정합니다.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   업데이트 Windows 사용하도록 설정합니다.
-   PowerShell 리모팅을 사용하도록 설정합니다. 스크립트를 실행하도록 시작 스크립트를 구성할 수 있습니다. Enable-PSRemoting -Force

PowerShell을 사용하여 구성 정보를 받고 설정하는 등 여러 원격 관리 작업을 수행할 수 있습니다. PowerShell 원격 관리가  실행되기 전에 PowerShell 리모컨을 사용하도록 설정해야 합니다. 배포 프로세스의 일부로 간주하거나 그룹 정책을 통해 구성해야 합니다. 이러한 기능에 대한 자세한 내용은 유지 관리 및 작업을 [참조하세요.](rooms-operations.md#remote-management-using-powershell) 


## <a name="configuration-and-deployment"></a>구성 및 배포 

구성 및 배포 계획은 다음 주요 영역을 다를 수 있습니다.

-   계정 프로비전
-   디바이스 소프트웨어 설치
-   디바이스 배포
-   Microsoft Teams 룸 및 주변 장치 구성
-   테스트
-   자산 관리

### <a name="account-provisioning"></a>계정 프로비전 

각 Microsoft Teams 룸 디바이스에는 전용 및 고유 리소스 계정이 Microsoft Teams 또는 비즈니스용 Skype Exchange. 이 계정에는 회의실 사서함이 Exchange 있어야 Teams 또는 비즈니스용 Skype 수 있습니다. Exchange 장치에서 들어오는 모임 요청을 자동으로 수락할 수 있도록 일정 처리를 구성해야 합니다. 이러한 계정 만들기에 대한 자세한 내용은 에 대한 계정 [구성을 Microsoft Teams 룸.](rooms-configure-accounts.md) 

**Pro 팁** – 이러한 계정에 대한 표시 이름을 설명하고 쉽게 이해할 수 있도록 합니다. 다음은 사용자가 모임에 시스템을 검색하고 추가하는 Microsoft Teams 룸 이름입니다. 일부 조직에서는 컨벤션 *Site* Room Name(최대 회의실 용량)-RS를 사용하기 때문에, 예를 들어 - 런던에 있는 12인용 회의실인 Curie에는 표시 이름 LON-CURIE(12)-RS가 있을 수 있습니다. 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![이름 규칙 결정](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>계정의 이름 Microsoft Teams 룸 결정합니다.</li><li>개별 계정을 만들지 대량 프로비전 스크립트를 사용할지 여부를 결정합니다.</li></ul>| 
| ![다음 단계](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 배포를 계획하기 시작하세요.</li></ul>| 


### <a name="device-software-installation"></a>디바이스 소프트웨어 설치 

배포를 계획할 Microsoft Teams 룸 필요한 소프트웨어를 설치하는 방법을 고려해야 합니다. 일반적인 시나리오 및 접근 방식은 다음 표에 설명되어 있습니다. 

| **시나리오**            | **접근 방식**         |
|-------------------------|-----------------------|   
|몇 가지 Microsoft Teams 룸(<10). | Surface Pro 기반 Microsoft Teams 룸 사용하는 경우 장치별 설치에 대한 설치 지침을 [따릅니다.](console.md) [이 편리한 비디오는 프로세스를 진행합니다.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) 통합 솔루션을 사용하는 경우 공급업체 이미지를 사용하여 배포하고 필요한 경우 설정을 구성합니다. |
| 단일 공급업체에서 10~50대의 디바이스를 배포합니다.     | WIM 기반 이미지를 만들고, [지침에서 6단계](console.md)후 일시 중지하고 복제 배포 기술과 함께 사용할 배포 이미지를 캡처합니다.    |
| 50개 Microsoft Teams 룸 디바이스를 배포하거나, 여러 공급업체에서 디바이스를 배포하거나, 배포의 일부로 조직별 에이전트를 요구합니다. | 작업 시퀀서 기반 소프트웨어 빌드 [및](rooms-scale.md)배포 플랫폼(예: Microsoft Endpoint Configuration Manager.  |


**Pro 팁** - 각 Microsoft Teams 룸 네트워크에 유효한 고유한 컴퓨터 이름이 있어야 합니다. 많은 모니터링 및 경고 시스템은 컴퓨터 이름을 키 식별자로 표시하기 때문에 지원 담당자가 작업을 요구하는 것으로 플래그가 지정된 Microsoft Teams 룸 쉽게 찾을 수 있는 이름 지정 규칙을 개발하는 것이 Microsoft Teams 룸 중요합니다. 예를 들어 MTR-Site Room -  Name(MTR-LON-CURIE)의 패턴을 사용할 수 있습니다. 

배포의 일부로 애플리케이션 설치 관리자에서 만든 로컬 계정을 관리하고 구성하기 위한 Microsoft Teams 룸 고려해야 합니다. [](/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts)

애플리케이션 모니터를 사용하여 Microsoft Azure [](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) 배포를 모니터링하고 가용성Microsoft Teams 룸 하드웨어/소프트웨어 오류 및 애플리케이션 버전에 대한 보고를 Microsoft Teams 룸 지침을 제공합니다. Microsoft Operations Management Suite를 사용하려면 소프트웨어 설치 프로세스의 일부로 Operations Management Suite 에이전트를 설치하고 작업 영역의 작업 영역 연결 정보를 구성해야 합니다. 

추가 고려 사항은 도메인에 도메인 Microsoft Teams 룸 여부입니다. 도메인 가입의 이점에 대한 정보는 Room System 도메인 Skype 고려 사항에서 [찾을 수 있습니다.](domain-joining-considerations.md) 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![의사 결정 지점 디바이스 이름](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>배포 Microsoft Teams 룸 사용할 디바이스 이름 지정 규칙을 확인합니다.</li><li>도메인에 디바이스를 Microsoft Teams 룸 여부와 로컬 계정을 관리하고 구성하는 방법을 결정합니다. </li><li>Operations Management Suite를 사용하여 배포를 모니터링할지 Microsoft Teams 룸 합니다.</li><li>디바이스 배포에 대비하여 소프트웨어 및 에이전트를 Microsoft Teams 룸 방법을 결정합니다. </li></ul>| 
| ![다음 단계 계획 디바이스](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 배포 방법을 계획하기 시작하세요.</li></ul>| 


### <a name="device-deployment"></a>디바이스 배포

소프트웨어가 Microsoft Teams 룸 배포한 후 디바이스 및 할당된 주변 장치를 회의실에 배송할 계획을 만든 다음 설치 및 구성을 진행합니다. 


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![사이트 내 배포 관리](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트당 배포를 관리할 인원을 결정합니다.</li><li> 사이트에 디바이스를 Microsoft Teams 룸 리소스를 식별하고 구성 및 테스트를 수행합니다.</li></ul>| 
| ![디바이스 테스트 시작](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 테스트를 시작하세요.</li></ul>| 

_샘플 배포 테이블_

| **사이트**  | **방 이름** | **룸 유형** | **Microsoft Teams 룸 시스템**  | **주변 장치**  | **Microsoft Teams 룸 이름**  | **Microsoft Teams 룸 리소스 계정**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 런던 본사 | Curie         | 중형        |                                   |                  |                                          |                                             |
| 시드니 본사 | 힐          | 대형         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams 룸 및 주변 장치 구성 

각 Microsoft Teams 룸 시스템이 물리적으로 배포되고 지원되는 주변 디바이스가 연결된 후 Microsoft Teams 룸 애플리케이션을 구성하여 Microsoft Teams 룸 리소스 계정 및 암호를 할당하여 Microsoft Teams 룸 시스템에 로그인하거나 Microsoft Teams 비즈니스용 Skype Exchange. 문서의 다른 곳에 연결된 인증된 USB 오디오 및 비디오 주변 장치를 활용하는 것이 중요합니다. 이렇게 하지 않을 경우 예측할 수 없는 동작이 될 수 있습니다. 

각 시스템마다 수동으로 Microsoft Teams 룸 수 있습니다. 또는 중앙에 저장된 XML Microsoft Teams 룸 XML 구성 파일을 사용하여 애플리케이션 설정을 관리하고 시작 GPO 스크립트를 활용하여 시스템 부팅 시마다 원하는 구성을 Microsoft Teams 룸 수 있습니다. 

XML 구성 파일을 사용하는 방법에 대한 자세한 내용은 XML 구성 파일을 사용하여 원격으로 Microsoft Teams 룸 콘솔 설정 관리를 [참조하세요.](xml-config-file.md) 

원격 [PowerShell을](rooms-operations.md#remote-management-using-powershell) 사용하여 보고 요구에 Microsoft Teams 룸 구성을 끌어오면 됩니다. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![의사 결정 지점 구성](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>각 시스템별로 수동으로 구성할지 Microsoft Teams 룸 중앙 XML 파일(디바이스당 하나씩)을 Microsoft Teams 룸 합니다.</li></ul>| 
| ![다음 단계 원격 접근 방식](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>원격 관리 방법을 정의합니다.</li></ul>| 

### <a name="testing"></a>테스트

시스템 Microsoft Teams 룸 배포한 후 테스트해야 합니다. 배포된 디바이스에서 Microsoft Teams 룸 [도움말에](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 나열된 기능이 작동하고 있는지 확인합니다. 배포 팀에서 Microsoft Operations Management Suite에 Microsoft Teams 룸 있는지 확인하는 것이 좋습니다. 또한 품질을 확인하기 위해 여러 테스트 호출 및 모임을 만드는 것이 중요합니다. 자세한 내용은 이 유용한 배포 검사 [목록을 참조하세요.](console.md#microsoft-teams-rooms-deployment-checklist)

일반 배포 또는 Teams 비즈니스용 Skype CQD(전화 품질 대시보드)에 대한 구성 파일을 구성하고, 품질 추세를 모니터링하고, 환경 품질 검토 프로세스에 참여하는 것이 좋습니다. 자세한 내용은 에 대한 통화 [품질 향상 및 모니터링을 Teams.](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>자산 관리

배포의 일부로 룸 이름, 디바이스 이름, Microsoft Teams 룸 로그인한 리소스 계정 및 할당된 주변 장치(Microsoft Teams 룸 USB 포트)로 자산 레지스터를 업데이트해야 합니다. 

_샘플 자산 테이블_

| **사이트**  | **방 이름** | **룸 유형** | **Microsoft Teams 룸 아니요.**  | **주변 장치/ 직렬 nos./ 포트**  | **Microsoft Teams 룸 이름**  | **Microsoft Teams 룸 서비스 계정**  | **배포된 날짜** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 런던 본사 | Curie         | 중형        |                                          |                                          |                                          |                                            |                   |
| 시드니 본사 | 힐          | 대형         |                                          |                                          |                                          |                                            |                   |