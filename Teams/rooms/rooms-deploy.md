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
description: 배포 단계를 포함하여 Microsoft Teams 회의실을 배포하는 방법에 대해 알아보는 이 문서를 읽어 읽습니다.
ms.openlocfilehash: 53c4c94717f10dadbad802cff3f233a3a771d166
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662253"
---
# <a name="deployment-overview"></a>배포 개요

Microsoft Teams 회의실 배포는 기본적으로 다음 단계로 나아 니다.

- 배포 위치(회의실)가 배포 종속성에 충족하는지 확인
- Microsoft Teams 또는 비즈니스용 Skype 및 Exchange 계정 만들기 및 콘솔 장치에 [할당(Microsoft Teams 회의실에](rooms-configure-accounts.md)대한 계정 구성 참조)
- Microsoft Teams 회의실 콘솔로 작동하도록 Microsoft Surface 태블릿을 다시 설치합니다(Microsoft [Teams 회의실](console.md) 콘솔 구성 또는 [Microsoft Teams 회의실](rooms-scale.md)대량 배포 가이드 참조).
- (선택 사항) 시스템에 대한 Microsoft Operations Management Suite 설정(Azure Monitor를 사용하여 [Microsoft Teams 회의실 관리 배포 참조)](azure-monitor-deploy.md)
- 회의실에서 본체를 설정하고 필요한 주변 장치 연결(장치 집합에 대한 OEM 설명서 참조)

AV 기술은 마지막 작업에 사용할 수 있지만 조직의 IT 부서는 프로세스의 다른 부분을 수행해야 합니다. 


## <a name="site-readiness"></a>사이트 준비 

주문된 디바이스가 조직에 전달되는 동안 네트워킹 및 시설 및 AV 팀과 협의하여 배포 종속성에 맞고 각 사이트와 방이 전원, 네트워킹 및 표시 측면에서 준비되어 있는지 확인합니다. 또한 물리적 설치 요구 사항을 충족하는지 확인합니다. 물리적 설치 고려 사항은 공급업체 사이트를 방문하여 화면을 설치 및 탑재하고 케이블을 실행하는 경우 AV 팀의 환경을 활용하세요.

이러한 종속성에 대한 자세한 내용은 아래 계획 지침 링크에서 찾을 수 있습니다.

-   [네트워크 가용성 확인](rooms-prep.md#check-network-availability)
-   [인증서](rooms-prep.md#certificates)
-   [프록시](rooms-prep.md#proxy)

**팁** - 프록시 서버를 사용하여 Teams 또는 비즈니스용 Skype Online에 대한 액세스를 제공하려는 경우 먼저 이 [문서를 검토하세요.](../proxy-servers-for-skype-for-business-online.md) 프록시 서버를 통해 비즈니스용 Skype 트래픽의 경우 프록시 서버를 모두 우회하는 것이 좋습니다. 비즈니스용 Skype 트래픽은 이미 암호화되어 있으므로 프록시 서버는 보안을 유지하지 않습니다. 광범위한 배포의 일부로 대역폭 계획 및 실시간 트래픽에 대한 네트워크의 적합성을 평가하기 위해 [Teams용](../prepare-network.md) 네트워크 준비의 지침을 따르는 것이 좋습니다.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트가 Microsoft Teams 회의실의 주요 요구 사항을 충족하는지 확인합니다.</li><li>각 사이트에 대해 충분한 대역폭을 제공해야 합니다.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 배포 및 구성을 계획하기 시작하세요.</li></ul>| 

## <a name="service-readiness"></a>서비스 준비

Microsoft Teams Rooms 배포를 준비하기 위해 다음 주요 중앙 작업을 수행합니다.

-   Microsoft Teams Rooms 서비스 계정 기능을 정의합니다.
-   Microsoft Teams 회의실 컴퓨터 및 서비스 계정을 보유할 조직 구성 단위 및 Active Directory 그룹을 준비하고, 선택적으로 PowerShell 리모팅을 사용하도록 GPOS(그룹 정책 개체)를 준비합니다.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Microsoft Teams Rooms 서비스 계정 기능 정의 

Microsoft Teams Rooms 배포를 사용하도록 결정한 공동 작업 시나리오에 따라 사용하도록 설정한 각 Microsoft Teams Rooms 서비스 계정에 할당하는 기능 및 기능을 결정해야 합니다.

| **시나리오** | **설명** | **Microsoft Teams Rooms 서비스 계정 기능** |
|---------- |------------- | --- |
| 대화형 모임            | 음성, 비디오 및 화면 공유 사용 Microsoft Teams 회의실을 예약 가능한 리소스로 만들기                     | 비즈니스용 Skype를 사용하도록 설정하고 Exchange(리소스 사서함)에 사용하도록 설정 |
| 전화 접속 회의            | 전화 접속 회의  좌표를 사용하여 Microsoft Teams 회의실 콘솔에서 직접 시작된 모임 사용 | 오디오 회의 사용                                          |
| 아웃바운드/인바운드 PSTN 통화 | Microsoft Teams 회의실 콘솔에서 PSTN 통화를 걸고 받을 수 있도록 설정                                         | 전화 시스템에 대해 사용하도록 설정                                                |

Microsoft Teams 회의실 계정에 대한 자세한 내용은 Microsoft Teams 회의실에 대한 [계정 구성을 참조하세요.](rooms-configure-accounts.md)


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>지원할 시나리오를 결정하고 Microsoft Teams Rooms 서비스 계정에 대한 라이선스 요구 사항을 식별합니다.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>컴퓨터 및 서비스 계정을 호스트할 준비를 합니다.</li></ul>| 


_샘플 Microsoft Teams Rooms 서비스 계정 계획 표_

| **사이트**  | **방 이름** | **방 유형** | **향후 방 기능**                                                 | **Microsoft Teams 회의실 계정 기능**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London HQ | Curie         | 중형        | 1 화면, 오디오 및 비디오 및 프레젠테이션 <br>전화 접속 회의 액세스<br> PSTN 액세스  | 비즈니스용 Skype를 사용하도록 설정하고 Exchange(리소스 사서함)에 사용하도록 설정 <br>오디오 회의 사용 <br>전화 시스템에 대해 사용하도록 설정 |
| 시드니 HQ | Hill          | 대형         | 2 화면, 오디오 및 비디오 및 프레젠테이션<br>전화 접속 회의 액세스<br> PSTN 액세스  | 비즈니스용 Skype를 사용하도록 설정하고 Exchange(리소스 사서함)에 사용하도록 설정<br> 오디오 회의 사용 <br>전화 시스템에 대해 사용하도록 설정 |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Microsoft Teams Rooms 컴퓨터 및 서비스 계정 호스트 준비(선택 사항)

Microsoft Teams Rooms 컴퓨터 및 서비스 계정을 관리하고 보고할 수 있도록 설정하려면 Azure AD(Azure Active Directory)를 준비합니다. 

모든 Microsoft Teams Rooms 서비스(사용자) 계정을 추가하는 Azure AD 그룹을 정의한 다음 Microsoft Teams Rooms 배포에서 Get-CSUserSession PowerShell cmdlet을 사용하여 사용 보고서를 만들 수 있습니다. 예를 들어 SkypeRoomSystemsv2-Service-Accounts라는 그룹을 만들 수 있습니다. 


모든 Microsoft Teams Rooms 컴퓨터 계정(도메인에 가입된 경우)을 보유할 조직 구성 단위를 하나씩, 모든 Microsoft Teams Rooms 사용자 계정을 보유할 조직 구성 단위를 1개로 구성합니다. Microsoft Teams Rooms 컴퓨터 계정에 대한 조직 구성 단위를 만드는 경우 도메인에 가입된 Microsoft Teams 회의실에 적용하려는 정책만 적용하도록 상속을 사용 안 하도록 하는 것이 좋습니다. 

Microsoft Teams 회의실 컴퓨터 계정이 포함된 조직 단위에 할당된 그룹 정책 개체를 만듭니다. 이 기능을 사용하여 다음을 할 수 있습니다. 

-   [전원 및 로컬 계정 설정을 선택합니다.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Windows 업데이트를 사용하도록 설정
-   PowerShell 리모팅을 사용하도록 설정 간단한 스크립트를 실행하도록 시작 스크립트를 구성할 수 있습니다. Enable-PSRemoting -Force

PowerShell을 사용하여 구성 정보를 받고 설정하는 등 다양한 원격 관리 작업을 수행할 수 있습니다. PowerShell 원격 관리가  실행되기 전에 PowerShell 원격을 사용하도록 설정해야 합니다. 배포 프로세스의 일부로 간주하거나 그룹 정책을 통해 구성해야 합니다. 이러한 기능 및 사용 설정에 대한 자세한 내용은 유지 관리 및 [작업을 참조하세요.](rooms-operations.md#remote-management-using-powershell) 


## <a name="configuration-and-deployment"></a>구성 및 배포 

구성 및 배포 계획에는 다음과 같은 주요 영역이 있습니다.

-   계정 프로비전
-   디바이스 소프트웨어 설치
-   디바이스 배포
-   Microsoft Teams Rooms 애플리케이션 및 주변 장치 구성
-   테스트
-   자산 관리

### <a name="account-provisioning"></a>계정 프로비전 

각 Microsoft Teams 회의실 장치에는 Microsoft Teams 또는 비즈니스용 Skype 및 Exchange 모두에 대해 사용하도록 설정해야 하는 고유한 전용 리소스 계정이 필요합니다. 이 계정에는 Exchange에서 호스팅되는 회의실 사서함이 있어야 합니다. Teams 또는 비즈니스용 Skype 배포에서 회의실로 사용하도록 설정해야 합니다. Exchange 쪽에서는 장치에서 들어오는 모임 요청을 자동으로 수락할 수 있도록 일정 처리를 구성해야 합니다. 이러한 계정 만들기에 대한 자세한 내용은 Microsoft Teams 회의실에 대한 계정 [구성을 참조하세요.](rooms-configure-accounts.md) 

**Pro 팁** – 이러한 계정에 대한 표시 이름을 설명하고 이해하기 쉽게 합니다. 다음은 Microsoft Teams 회의실 시스템을 검색하고 모임에 추가할 때 사용자에게 표시될 이름입니다. 일부 조직에서는 사이트 회의실 이름(최대 회의실 용량)-RS 규칙을 사용하기 때문에 런던의 12인용 회의실인 Curie에는 표시 이름이 - LON-CURIE(12)-RS일 수 있습니다. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>Microsoft Teams 회의실 계정에 대한 이름 규칙 결정</li><li>개별 계정을 만들지 또는 대량 프로비전 스크립트를 사용할지 여부를 결정할 수 있습니다.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 배포를 계획하기 시작하세요.</li></ul>| 


### <a name="device-software-installation"></a>디바이스 소프트웨어 설치 

Microsoft Teams 회의실을 배포할 때 필요한 소프트웨어를 설치하기 위해 고려해야 할 다양한 옵션이 있습니다. 일반적인 시나리오 및 접근 방식은 다음 표에 설명되어 있습니다. 

| **시나리오**            | **접근 방식**         |
|-------------------------|-----------------------|   
|소수의 Microsoft Teams 회의실 장치 배포(<10개). | Surface Pro 기반 Microsoft Teams 회의실을 사용하는 경우 장치별 설치에 대한 설치 [지침을 따릅니다.](console.md) [이 편리한 비디오에서는 프로세스를 진행하는 과정을 진행합니다.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) 통합 솔루션을 사용하는 경우 공급업체 이미지를 사용하여 배포하고 필요한 설정을 구성합니다. |
| 단일 공급업체에서 10~50개 디바이스 배포     | WIM 기반 이미지를 만들고, [지침의 6단계](console.md)후에 일시 중지하고, 복제 배포 기술과 함께 사용할 배포 이미지를 캡처합니다.    |
| 50개가 넘는 Microsoft Teams Rooms 디바이스를 배포하거나, 여러 공급업체에서 디바이스를 배포하거나, 배포의 일부로 조직별 에이전트를 요구합니다. | [Microsoft Endpoint Configuration Manager와](rooms-scale.md)같은 작업 시퀀스러 기반 소프트웨어 빌드 및 배포 플랫폼을 사용합니다.  |


**Pro 팁** - 각 Microsoft Teams 회의실에는 네트워크에 유효하고 고유한 컴퓨터 이름이 있어야 합니다. 많은 모니터링 및 경고 시스템에서 컴퓨터 이름을 키 식별자로 표시하기 때문에 지원 담당자가 작업 요구로 플래그가 지정된 Microsoft Teams 회의실을 쉽게 찾을 수 있도록 Microsoft Teams 회의실 배포에 대한 명명 규칙을 개발하는 것이 중요합니다. 예를 들어 MTR- 사이트 방 - 이름(MTR-LON-CURIE)의 패턴을 사용할 수 있습니다. 

배포의 일부로 Microsoft Teams 회의실 애플리케이션 설치 관리자에서 만든 로컬 [](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) 계정을 관리하고 구성하기 위한 전략도 고려해야 합니다.

[Microsoft Azure Monitor를](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) 사용하여 Microsoft Teams Rooms 배포를 모니터링하고 가용성, 하드웨어/소프트웨어 오류 및 Microsoft Teams Rooms 애플리케이션 버전을 보고하는 방법에 대한 지침을 제공합니다. Microsoft Operations Management Suite를 사용하기로 결정한 경우 소프트웨어 설치 프로세스의 일부로 Operations Management Suite 에이전트를 설치하고 작업 영역의 작업 영역 연결 정보를 구성해야 합니다. 

Microsoft Teams 회의실을 도메인에 가입할지 여부를 추가로 고려해야 합니다. 도메인 가입의 이점에 대한 정보는 Skype 채팅방 시스템 도메인 가입 고려 [사항에서 찾을 수 있습니다.](domain-joining-considerations.md) 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>배포하는 동안 사용할 Microsoft Teams Rooms 장치 이름 지정 규칙을 결정하세요.</li><li>Microsoft Teams Rooms 디바이스를 도메인에 가입할지 여부와 로컬 계정을 관리하고 구성하는 방법을 결정할 수 있습니다. </li><li>Operations Management Suite를 사용하여 Microsoft Teams Rooms 배포를 모니터링할지 여부를 결정할 수 있습니다.</li><li>디바이스 배포를 준비하기 위해 Microsoft Teams 회의실 시스템에 소프트웨어 및 에이전트를 배포하는 데 사용할 방법을 결정하세요. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 배포 방법을 계획하기 시작하세요.</li></ul>| 


### <a name="device-deployment"></a>디바이스 배포

Microsoft Teams 회의실 단위에 소프트웨어를 배포한 후 장치와 할당된 주변 장치를 회의실에 배송할 계획을 만든 다음 설치 및 구성을 진행합니다. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트당 배포를 관리할 사용자 결정</li><li> 사이트에 Microsoft Teams 회의실 장치를 설치하고 구성 및 테스트를 진행할 리소스를 식별합니다.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>디바이스 테스트를 시작하세요.</li></ul>| 

_샘플 배포 테이블_

| **사이트**  | **방 이름** | **방 유형** | **Microsoft Teams 회의실 시스템**  | **주변 장치**  | **Microsoft Teams 회의실 컴퓨터 이름**  | **Microsoft Teams Rooms 리소스 계정**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London HQ | Curie         | 중형        |                                   |                  |                                          |                                             |
| 시드니 HQ | Hill          | 대형         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams Rooms 애플리케이션 및 주변 장치 구성 

각 Microsoft Teams 회의실 시스템이 물리적으로 배포되고 지원되는 주변 장치가 연결되면 Microsoft Teams 회의실 시스템이 Microsoft Teams 또는 비즈니스용 Skype 및 Exchange에 로그인할 수 있도록 앞에서 만든 Microsoft Teams Rooms 리소스 계정 및 암호를 할당하도록 Microsoft Teams 회의실 응용 프로그램을 구성해야 합니다. 문서의 다른 곳에 연결된 인증된 USB 오디오 및 비디오 주변 장치를 활용하는 것이 중요합니다. 이렇게 하지 않는 경우 예측할 수 없는 동작이 될 수 있습니다. 

각 Microsoft Teams 회의실 시스템을 수동으로 구성할 수 있습니다. 또는 중앙에 저장된 Microsoft Teams 회의실 XML 구성 파일을 사용하여 애플리케이션 설정을 관리하고 시작 GPO 스크립트를 활용하여 Microsoft Teams 회의실 시스템이 부팅될 때마다 원하는 구성을 다시 적용할 수 있습니다. 

XML 구성 파일을 사용하는 방법에 대한 자세한 내용은 XML 구성 파일을 사용하여 원격으로 Microsoft Teams 회의실 콘솔 설정 관리를 [참조하세요.](xml-config-file.md) 

원격 [PowerShell을](rooms-operations.md#remote-management-using-powershell) 사용하여 보고 요구 사항을 위해 Microsoft Teams 회의실 구성을 끌어오면 됩니다. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>각 Microsoft Teams 회의실 시스템을 수동으로 구성할지 또는 중앙 XML 파일(Microsoft Teams 회의실 장치당 하나)을 사용할지 여부를 결정하세요.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>원격 관리 방법을 정의합니다.</li></ul>| 

### <a name="testing"></a>테스트

Microsoft Teams Rooms 시스템이 배포된 후 테스트해야 합니다. [Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 회의실 도움말에 나열된 기능이 배포된 장치에서 작동하고 있는지 확인합니다. 배포 팀에서 Microsoft Teams 회의실이 Microsoft Operations Management Suite(사용되는 경우)에 로깅하는지 확인하는 것이 좋습니다. 품질을 확인하기 위해 여러 테스트 통화 및 모임을 하는 것이 중요합니다. 자세한 내용은 이 유용한 배포 검사 [목록을 참조하세요.](console.md#microsoft-teams-rooms-deployment-checklist)

일반적인 Teams 또는 비즈니스용 Skype 롤아웃의 일부로 CQD(통화 품질 대시보드)에 대한 파일 작성을 구성하고, 품질 추세를 모니터링하고, 환경 품질 검토 프로세스에 참여하는 것이 좋습니다. 자세한 내용은 Teams의 통화 품질 개선 [및 모니터링을 참조하세요.](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>자산 관리

배포의 일부로 방 이름, Microsoft Teams Room 장치 이름, 로그인한 Microsoft Teams Room 리소스 계정 및 할당된 주변 장치(및 사용하는 USB 포트)를 사용하여 자산 레지스터를 업데이트할 수 있습니다. 

_샘플 자산 테이블_

| **사이트**  | **방 이름** | **방 유형** | **Microsoft Teams Rooms 직렬 번호**  | **주변 장치/직렬 nos./ 포트**  | **Microsoft Teams 회의실 컴퓨터 이름**  | **Microsoft Teams Rooms 서비스 계정**  | **배포된 날짜** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London HQ | Curie         | 중형        |                                          |                                          |                                          |                                            |                   |
| 시드니 HQ | Hill          | 대형         |                                          |                                          |                                          |                                            |                   |


