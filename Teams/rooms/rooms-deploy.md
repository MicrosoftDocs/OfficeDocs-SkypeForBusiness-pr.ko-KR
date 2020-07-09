---
title: Microsoft Teams 룸 배포
ms.author: v-lanac
author: lanachin
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
description: 배포 단계를 포함 하 여 Microsoft 팀 대화방을 배포 하는 방법에 대해 자세히 알아보려면이 문서를 참조 하세요.
ms.openlocfilehash: ee8ff755674828b4a2635316227f9cc27189a110
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085964"
---
# <a name="deployment-overview"></a>배포 개요

Microsoft 팀 회의실 구축은 본질적으로 다음 단계로 분류 됩니다.

- 배포 위치 (회의실)가 배포 종속성을 충족 하는지 확인
- Microsoft 팀 또는 비즈니스용 Skype 및 Exchange 계정을 만들어 콘솔 장치에 할당 ( [Microsoft 팀 대화방에 대 한 계정 구성](rooms-configure-accounts.md)참조)
- Microsoft Surface 태블릿이 팀 대화방 콘솔로 작동 하도록 Reimaging ( [Microsoft 팀 대화방 콘솔 구성](console.md) 또는 [microsoft 팀 회의실 대량 배포 가이드 배포](rooms-scale.md)참조)
- ) 시스템에 대 한 Microsoft Operations Management Suite 설정 ( [Azure Monitor를 사용 하 여 Microsoft 팀 대화방 관리 배포](azure-monitor-deploy.md) 참조
- 회의실에서 콘솔 설정 및 필요한 주변 장치 연결 (장치 집합에 대 한 OEM 설명서 참조)

마지막 작업에는 AV techs 사용할 수 있지만, 조직의 IT 부서는 프로세스의 다른 부분을 수행 해야 합니다. 


## <a name="site-readiness"></a>사이트 준비 

순서가 지정 된 디바이스는 조직에 제공 되는 동안에는 네트워킹 및 시설 및 AV 팀과 협력 하 여 배포 종속성이 충족 되 고 각 사이트와 채팅방이 전력, 네트워킹, 디스플레이 측면에서 준비 되어 있는지 확인 합니다. 또한 실제 설치 요구 사항이 충족 되는지 확인 합니다. 물리적 설치 고려 사항은 공급 업체의 사이트를 방문 하 여 화면을 설치 및 장착 하 고 케이블링을 실행할 때 AV 팀의 경험을 활용 하십시오.

아래의 계획 지침 링크에서 이러한 종속성에 대해 자세히 알 수 있습니다.

-   [네트워크 가용성 확인](rooms-prep.md#check-network-availability)
-   [인증](rooms-prep.md#certificates)
-   [가상본](rooms-prep.md#proxy)

**Pro 팁** -프록시 서버를 사용 하 여 팀 또는 비즈니스용 Skype Online에 대 한 액세스를 제공 하려는 경우 먼저 [이 문서를 검토](../proxy-servers-for-skype-for-business-online.md)하세요. 프록시 서버를 통해 비즈니스용 Skype 트래픽에 대 한 정보를 제공 하는 경우 프록시 서버를 우회 하는 것이 좋습니다. 비즈니스용 Skype 소통량이 이미 암호화 되어 있으므로 프록시 서버에서 더 이상 보안을 유지할 수 없습니다. 광범위 한 배포의 일환으로 대역폭 계획을 위한 [팀을 위해 네트워크 준비](../prepare-network.md) 및 네트워크에서 실시간 트래픽에 적합 한지 평가에 대 한 지침을 따르는 것이 좋습니다.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트가 Microsoft 팀 대화방의 주요 요구 사항을 충족 하는지 확인 합니다.</li><li>각 사이트에 충분 한 대역폭을 제공 했는지 확인 합니다.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>장치 배포 및 구성 계획을 시작 합니다.</li></ul>| 

## <a name="service-readiness"></a>서비스 준비

Microsoft 팀 회의실 배포를 준비 하려면 다음 키의 중앙 작업을 수행 합니다.

-   Microsoft 팀 대화방 서비스 계정 기능을 정의 합니다.
-   Microsoft 팀 공간 컴퓨터와 서비스 계정을 유지 하기 위해 조직 구성 단위 및 Active Directory 그룹을 준비 하 고, 선택적으로, PowerShell remoting을 사용 하도록 설정 하는 Gpo (그룹 정책 개체)를 준비 합니다.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Microsoft 팀 대화방 서비스 계정 기능 정의 

Microsoft 팀 회의실 배포에 사용 하도록 결정 한 공동 작업 시나리오에 따라 사용 하도록 설정한 각 Microsoft 팀 대화방 서비스 계정에 할당할 기능을 결정 해야 합니다.

| **시나리오** | **설명** | **Microsoft 팀 대화방 서비스 계정 기능** |
|---------- |------------- | --- |
| 대화형 모임            | 음성, 비디오, 화면 공유 사용 Microsoft 팀 회의실을 만들 수 있는 bookable                     | 비즈니스용 Skype, Exchange에 대해 사용 하도록 설정 됨 (리소스 사서함) |
| 전화 접속 회의            | 전화 접속 회의 좌표를 사용 하 여 Microsoft 팀 회의실 콘솔에서 *직접* 모임을 시작 하도록 설정 | 오디오 회의를 사용 하도록 설정                                          |
| 아웃 바운드/인바운드 PSTN 통화 | Microsoft 팀 대화방 콘솔을 사용 하 여 PSTN 통화를 설정 하 고 수신 합니다.                                         | 전화 시스템에서 사용                                                |

Microsoft 팀 대화방 계정에 대 한 자세한 내용은 [Microsoft 팀 대화방 계정 구성을](rooms-configure-accounts.md)참조 하세요.


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>지원할 시나리오를 결정 하 고 Microsoft 팀 대화방 서비스 계정에 대 한 라이선스 요구 사항을 식별 합니다.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>컴퓨터 및 서비스 계정을 호스트할 준비를 합니다.</li></ul>| 


_샘플 Microsoft 팀 대화방 서비스 계정 계획 표_

| **사이트**  | **방 이름** | **방 종류** | **향후 방 용량**                                                 | **Microsoft 팀 대화방 계정 기능**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 런던 사령부 | Curie         | 중형        | 1 화면, 오디오 및 비디오 + 프레젠테이션 <br>전화 접속 회의 액세스<br> PSTN 액세스  | 비즈니스용 Skype, Exchange에 대해 사용 하도록 설정 됨 (리소스 사서함) <br>오디오 회의를 사용 하도록 설정 <br>전화 시스템에서 사용 |
| 시드니 사령부 | 지          | 대형         | 2 개의 화면, 오디오 및 비디오와 프레젠테이션<br>전화 접속 회의 액세스<br> PSTN 액세스  | 비즈니스용 Skype, Exchange에 대해 사용 하도록 설정 됨 (리소스 사서함)<br> 오디오 회의를 사용 하도록 설정 <br>전화 시스템에서 사용 |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Microsoft 팀 대화방 컴퓨터 및 서비스 계정 호스팅 준비 (선택 사항)

Microsoft 팀 공간 컴퓨터와 서비스 계정을 관리 하 고 보고할 수 있도록 하려면 온-프레미스 Active Directory 또는 Azure Active Directory (azure AD)를 준비 합니다. 

온-프레미스 Active Directory 또는 Azure AD 그룹을 정의 하 여 모든 Microsoft 팀 대화방 서비스 (사용자) 계정을 추가 하 고 Microsoft 팀 회의실 배포에서 Get-CSUserSession PowerShell cmdlet을 사용 하 여 사용 현황 보고서를 만듭니다. 예를 들어 SkypeRoomSystemsv2-서비스 계정 이라는 그룹을 만듭니다. 


온-프레미스 Active Directory 또는 Azure AD 계층에 하나의 조직 구성 단위를 정의 하 여 모든 Microsoft 팀 대화방 컴퓨터 계정 (도메인에 가입 되어 있는 경우)과 모든 Microsoft 팀 대화방 사용자 계정을 보유 하는 조직 단위 하나를 지정 합니다. Microsoft 팀 회의실 컴퓨터 계정에 대 한 조직 구성 단위를 만드는 경우 도메인에 가입 된 Microsoft 팀 방에 적용 하도록 의도 한 정책만 적용 하도록 상속을 사용 하지 않도록 설정 하는 것이 좋습니다. 

Microsoft 팀 회의실 컴퓨터 계정이 포함 된 조직 구성 단위에 할당 된 그룹 정책 개체를 만듭니다. 사용할 대상: 

-   [전원 및 로컬 계정 설정을 설정](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)합니다.
-   Windows 업데이트를 사용 하도록 설정 합니다.
-   PowerShell remoting을 사용 하도록 설정 합니다. 간단한 스크립트를 실행 하도록 시작 스크립트를 구성할 수 있습니다: Enable-PSRemoting-Force

PowerShell을 사용 하 여 구성 정보를 가져오고 설정 하는 등의 다양 한 원격 관리 작업을 수행할 수 있습니다. Powershell 원격 관리를 수행 *하기 전에* powershell remoting을 사용 하도록 설정 해야 하며 배포 프로세스의 일부로 간주 하거나 그룹 정책을 통해 구성할 수 있습니다. 이러한 기능에 대 한 자세한 내용은 [유지 관리 및 작업](rooms-operations.md#remote-management-using-powershell)을 참조 하세요. 


## <a name="configuration-and-deployment"></a>구성 및 배포 

구성 및 배포 계획에는 다음 주요 영역이 포함 됩니다.

-   계정 프로비저닝
-   장치 소프트웨어 설치
-   장치 배포
-   Microsoft 팀 대화방 응용 프로그램 및 주변 장치 구성
-   테스트가
-   자산 관리

### <a name="account-provisioning"></a>계정 프로비저닝 

각 Microsoft 팀 대화방 장치에는 Microsoft 팀 또는 비즈니스용 Skype 및 Exchange 모두에 대해 사용 하도록 설정 해야 하는 전용 고유 리소스 계정이 필요 합니다. 이 계정에는 Exchange에서 호스트 되는 채팅방 사서함이 있어야 하며,이를 팀 또는 비즈니스용 Skype 배포에서 회의실으로 사용 하도록 설정 해야 합니다. Exchange 쪽에서는 장치가 들어오는 모임 요청을 자동으로 수락할 수 있도록 일정 처리를 구성 해야 합니다. 이러한 계정을 만드는 방법에 대 한 자세한 내용은 [Microsoft 팀 대화방 계정 구성을](rooms-configure-accounts.md)참조 하세요. 

**Pro 팁** – 이러한 계정에 대 한 표시 이름을 설명 하 고 이해 하기 쉽게 만듭니다. 다음은 사용자가 Microsoft 팀 공간 시스템을 검색 하 고 모임에 추가할 때 표시 되는 이름입니다. 일부 조직에서는 *사이트* - *공간 이름*(*최대 회의실 용량*)을 사용 하 여 (예: London의 12 사람 전화 회의실) 디스플레이 이름 LON-curie (12)-r이 표시 될 수 있습니다. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>Microsoft 팀 대화방 계정에 대 한 명명 규칙을 결정 합니다.</li><li>개별 계정을 만들지 아니면 대량 프로 비전 스크립트를 사용할지 여부를 결정 합니다.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>장치 배포 계획을 시작 합니다.</li></ul>| 


### <a name="device-software-installation"></a>장치 소프트웨어 설치 

Microsoft 팀 회의실을 배포 하려는 경우 필요한 소프트웨어를 설치할 때 고려해 야 할 몇 가지 옵션이 있습니다. 다음 표에서는 일반적인 시나리오 및 방법에 대해 설명 합니다. 

| **시나리오**            | **방식의**         |
|-------------------------|-----------------------|   
|적은 수의 Microsoft 팀 공간 장치 배포 (<10). | Surface Pro 기반 Microsoft 팀 대화방을 사용 하는 경우 [장치 단위 설치에 대 한 설치 지침](console.md)을 따릅니다. [이 편리한 비디오는이 과정을 안내 합니다.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) 통합 된 솔루션을 사용 하는 경우 공급 업체 이미지를 사용 하 여 배포 하 고 필요에 따라 설정을 구성 합니다. |
| 단일 공급 업체에서 10 대 50 장치를 배포 합니다.     | WIM 기반 이미지를 만들고, [지침의 6 단계](console.md)를 수행한 후에 일시 중지 하 고, 복제 배포 기술에 사용할 배포 이미지를 캡처 하세요.    |
| 50 개 이상의 Microsoft 팀 공간 장치 배포, 둘 이상의 공급 업체에서 장치 배포, 배포의 일부로 조직 관련 에이전트 필요 | [Microsoft 끝점 구성 관리자](rooms-scale.md)와 같은 작업 시퀀서 기반 소프트웨어 빌드 및 배포 플랫폼을 사용 합니다.  |


**Pro 팁** -각 Microsoft 팀 방에는 네트워크에 대 한 유효한 고유한 컴퓨터 이름이 있어야 합니다. 많은 모니터링 및 경고 시스템은 컴퓨터 이름을 키 식별자로 표시 하므로 Microsoft 팀 대화방 배포에 대 한 명명 규칙을 개발 하 여 지원 직원이 작업 필요에 따라 플래그가 지정 된 Microsoft 팀 대화방을 쉽게 찾을 수 있도록 하는 것이 중요 합니다. 예를 들어 mtr*사이트* - *방 이름* 패턴 (mtr-LON-curie)을 사용 하 고 있을 수 있습니다. 

배포의 일부로 Microsoft 팀 대화방 응용 프로그램 설치 관리자에서 만든 [로컬 계정을](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) 관리 하 고 구성 하는 방법에 대 한 전략도 함께 고려해 야 합니다.

[Microsoft Azure 모니터](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) 를 사용 하 여 Microsoft 팀 공간 배포를 모니터링 하 고 가용성, 하드웨어/소프트웨어 오류 및 Microsoft 팀 대화방 응용 프로그램 버전을 보고 하는 방법에 대 한 지침을 제공 합니다. Microsoft Operations Management Suite를 사용 하기로 결정 한 경우 소프트웨어 설치 프로세스의 일부로 Operations Management Suite 에이전트를 설치 하 고 작업 영역에 대 한 작업 영역 연결 정보를 구성 해야 합니다. 

추가 고려 사항은 Microsoft 팀 채팅방이 도메인에 가입 되어 있는지 여부입니다. 도메인 가입의 이점에 대 한 정보는 [Skype 룸 시스템 도메인 참가 고려 사항](domain-joining-considerations.md)에 나와 있습니다. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>배포 중에 사용할 Microsoft 팀 공간 장치 이름 지정 규칙을 결정 합니다.</li><li>Microsoft 팀 대화방 장치를 도메인에 연결할지 여부와 로컬 계정을 관리 하 고 구성 하는 방법을 결정 합니다. </li><li>Microsoft 팀 대화방 배포를 모니터링 하기 위해 Operations Management Suite를 사용할지 여부를 결정 합니다.</li><li>장치 배포 준비를 위해 소프트웨어와 에이전트를 Microsoft 팀원에 게 배포 하는 데 사용할 방법을 결정 합니다. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>장치 배포 방법 계획을 시작 합니다.</li></ul>| 


### <a name="device-deployment"></a>장치 배포

Microsoft 팀 회의실 단위에 소프트웨어를 배포한 후에는 장치 및 할당 된 주변 기기 장치를 채팅방에 제공 하는 계획을 만든 다음 설치 및 구성으로 진행 합니다. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>사이트별 배포를 관리할 사용자를 결정 합니다.</li><li> 사이트에 Microsoft 팀 회의실 디바이스를 설치 하 고 구성 및 테스트를 수행할 리소스를 식별 합니다.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>장치 테스트를 시작 합니다.</li></ul>| 

_샘플 배포 테이블_

| **사이트**  | **방 이름** | **방 종류** | **Microsoft 팀 대화방 시스템**  | **주변 기기 장치**  | **Microsoft 팀 공간 컴퓨터 이름**  | **Microsoft 팀 대화방 자원 계정**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 런던 사령부 | Curie         | 중형        |                                   |                  |                                          |                                             |
| 시드니 사령부 | 지          | 대형         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft 팀 대화방 응용 프로그램 및 주변 장치 구성 

각 Microsoft 팀 대화방 시스템을 물리적으로 배포 하 고 지원 되는 주변 장치를 연결한 후에는 microsoft 팀 대화방 응용 프로그램을 구성 하 여 microsoft 팀 대화방 시스템에서 microsoft 팀 또는 비즈니스용 Skype에 로그인 할 수 있도록 microsoft 팀 대화방 리소스 계정 및 암호를 할당 해야 합니다. 문서의 다른 위치에 연결 된 인증 USB 오디오 및 영상 주변 장치를 활용 하는 것이 중요 합니다. 이렇게 하지 않으면 예기치 않은 동작이 발생할 수 있습니다. 

각 Microsoft 팀 대화방 시스템을 수동으로 구성할 수 있습니다. 또는 Microsoft 팀 대화방 시스템을 부팅할 때마다 저장 된 Microsoft 팀의 회의실 XML 구성 파일을 사용 하 여 응용 프로그램 설정을 관리 하 고 시작 GPO 스크립트를 활용 하 여 원하는 구성을 다시 적용할 수 있습니다. 

XML 구성 파일을 사용 하는 방법에 대 한 자세한 내용은 [xml 구성 파일을 사용 하 여 원격으로 Microsoft 팀 공간 콘솔 설정 관리](xml-config-file.md)를 참조 하세요. 

[원격 PowerShell](rooms-operations.md#remote-management-using-powershell) 을 사용 하 여 보고 요구 사항에 맞게 Microsoft 팀 대화방 구성을 가져올 수 있습니다. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>각 Microsoft 팀 공간 시스템을 수동으로 구성 하거나 중앙 XML 파일을 사용할 것인지 여부를 결정 합니다 (Microsoft 팀 대화방 장치 당 하나).</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>원격 관리 방법을 정의 합니다.</li></ul>| 

### <a name="testing"></a>테스트가

Microsoft 팀 대화방 시스템을 배포한 후에는 테스트 해야 합니다. [Microsoft 팀 대화방](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 에 나열 된 기능이 배포 된 장치에서 작동 하는지 확인 합니다. Microsoft 팀 객실이 Microsoft Operations Management Suite (사용 되는 경우)에 기록 되 고 있는지 배포 팀이이를 적극 권장 합니다. 또한 다양 한 테스트 통화와 모임을 통해 품질을 확인 하는 것이 중요 합니다. 자세한 내용은이 [유용한 배포 검사 목록을](console.md#microsoft-teams-rooms-deployment-checklist)참조 하세요.

일반 팀 또는 비즈니스용 Skype 출시의 일부로 서, 통화 품질 대시보드 (CQD)에 대 한 빌드 파일을 구성 하 고, 품질 추세를 모니터링 하 고, 경험 치를 검토 하는 프로세스에 참여 하는 것이 좋습니다. 자세한 내용은 [팀의 통화 품질 개선 및 모니터링](../monitor-call-quality-qos.md)을 참조 하세요. 

### <a name="asset-management"></a>자산 관리

배포의 일부로 자산 이름, Microsoft 팀 대화방 장치 이름, 로그인 한 Microsoft 팀 대화방 리소스 계정, 할당 된 주변 기기 장치 (그리고 해당 사용자가 사용 하는 USB 포트)를 사용 하 여 자산 등록기를 업데이트 하려고 합니다. 

_자산 표 샘플_

| **사이트**  | **방 이름** | **방 종류** | **Microsoft 팀 회의실 직렬 번호**  | **주변 기기 장치/직렬 nos/포트**  | **Microsoft 팀 공간 컴퓨터 이름**  | **Microsoft 팀 대화방 서비스 계정**  | **배포 된 날짜** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 런던 사령부 | Curie         | 중형        |                                          |                                          |                                          |                                            |                   |
| 시드니 사령부 | 지          | 대형         |                                          |                                          |                                          |                                            |                   |


