---
title: 회의를 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26dff7d8-242a-4576-9870-d6d461758a37
description: '요약: 이 항목을 읽고 회의를 배포하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 5b16afdd4530b111f34fd07ad7851c84200fca2b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845951"
---
# <a name="deploy-conferencing-in-skype-for-business-server"></a>회의를 비즈니스용 Skype 서버

**요약:** 이 항목을 읽고 회의를 배포하는 방법을 비즈니스용 Skype 서버.

웹 회의, A/V(오디오 및 비디오) 회의, 전화 접속 회의 및 IM(인스턴트 메시지) 회의 등 비즈니스용 Skype 서버 네 가지 유형의 회의를 사용할 수 있습니다. 모든 회의 유형을 사용하도록 설정하거나 요구에 따라 하나의 유형만 사용하도록 선택할 수 있습니다.

사용자 비즈니스용 Skype 서버 IM 회의 기능이 자동으로 배포됩니다. 토폴로지 작성기를 사용하여 새 토폴로지 만들기 및 게시할 때 다음 검사 목록에 설명된 바와 같이 웹, A/V 및 전화 접속 회의를 배포할지 여부를 지정합니다.

- [웹 및 오디오/비디오 회의 배포 검사 목록](deploy-conferencing.md#BKMK_ChecklistWebConferencing)

- [전화 접속 회의 배포 흐름도 및 검사 목록](deploy-conferencing.md#BKMK_DialinConferencing)

회의를 배포하기 전에 다음 계획 항목을 읽어야 합니다.

- [2016년 8월 회의 비즈니스용 Skype 서버](../../plan-your-deployment/conferencing/conferencing.md)

- [회의의 하드웨어 및 소프트웨어 요구 비즈니스용 Skype 서버](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)

- [회의 토폴로 비즈니스용 Skype 서버지 계획](../../plan-your-deployment/conferencing/conferencing-topology.md)

- [2016년 8월 전화 접속 회의 비즈니스용 Skype 서버](../../plan-your-deployment/conferencing/dial-in-conferencing.md)

- [대규모 모임 비즈니스용 Skype 서버 계획](../../plan-your-deployment/conferencing/large-meetings.md)

## <a name="deployment-checklist-for-web-and-audiovideo-conferencing"></a>웹 및 오디오/비디오 회의 배포 검사 목록
<a name="BKMK_ChecklistWebConferencing"> </a>

다음 표에서는 기존 토폴로지로 웹 및 오디오/비디오 회의를 배포하는 데 필요한 단계에 대한 개요를 제공합니다. 관련 계획 및 프로시저 설명서에 대한 링크가 포함됩니다.

|**작업 단계**|**단계**|**역할 및 그룹 구성원 자격**|**설명서**|
|:-----|:-----|:-----|:-----|
|**필요한 하드웨어 및 소프트웨어 설치** <br/> |회의는 프런트 엔드 풀 및 프런트 엔드 서버의 프런트 엔드 서버에서 Standard Edition 실행됩니다. 프런트 엔드 서버에 대한 서버 및 환경 요구 사항을 참조하세요.  <br/> 웹 회의를 사용하도록 설정하는 경우 비즈니스용 Skype 서버 프레젠테이션의 공유 및 렌더링을 처리하는 데 사용되는 Office Web Apps 서버와 통신할 수 PowerPoint 합니다.  <br/> 웹 회의의 경우 파일 저장소로 사용할 파일 공유도 지정해야 합니다.  <br/> 외부 사용자가 비즈니스용 Skype 회의에 참가할 수 있도록 설정하고 싶나요? 이 경우 에지 서버를 배포해야 합니다.  <br/> |로컬 Administrators 그룹의 구성원인 도메인 사용자  <br/> | [2019년 비즈니스용 Skype 서버 서버 요구 사항](../../../SfBServer2019/plan/system-requirements.md) <br> [비즈니스용 Skype 서버 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [2015년 비즈니스용 Skype 서버 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [회의의 하드웨어 및 소프트웨어 요구 비즈니스용 Skype 서버](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [Office Web Apps Server와의 비즈니스용 Skype 서버](office-web-app-server.md) <br/> [파일 공유를 비즈니스용 Skype 서버](../../deploy/install/create-a-file-share.md) <br/> [2015년 에지 서버 배포 비즈니스용 Skype 서버 계획](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) <br/> [2015년 비즈니스용 Skype 서버 에지 서버 배포](../../deploy/deploy-edge-server/deploy-edge-server.md) <br/> |
|**회의를 지원하는 데 적절한 내부 토폴로지 만들기** <br/> |토폴로지 작성기 를 실행하여 토폴로지에 회의를 추가한 다음 토폴로지 게시를 해야 합니다.  <br/> |토폴로지를 정의하려면 로컬 Users 그룹의 구성원 계정 필요  <br/> 토폴로지 게시를 위해 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원인 계정으로, 비즈니스용 Skype 서버 파일 저장소에 사용할 파일 공유에 대한 모든 권한(읽기/쓰기/수정)이 있는 계정(토폴로지 작성기에서 필요한 DACL을 구성할 수 있도록)  <br/> |[새 토폴로지 만들기 및 비즈니스용 Skype 서버](../../deploy/install/create-and-publish-new-topology.md) <br/> |
|**회의 정책 및 구성 설정 구성** <br/> |회의 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 셸을 사용하여 회의 정책 및 구성 설정을 구성합니다.  <br/> |RTCUniversalServerAdmins 그룹(Windows PowerShell만 해당) 또는 사용자를 CSAdministrator 역할에 할당  <br/> |[회의 정책 관리 비즈니스용 Skype 서버](../../manage/conferencing/conferencing-policies.md) <br/> [모임 구성 설정 관리 비즈니스용 Skype 서버](../../manage/conferencing/meeting-configuration-settings.md) <br/> [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> [New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> [Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |

## <a name="deployment-flowchart-and-checklist-for-dial-in-conferencing"></a>전화 접속 회의 배포 흐름도 및 검사 목록
<a name="BKMK_DialinConferencing"> </a>

 전화 접속 회의를 사용하면 사용자가 PSTN(Public Switched Telephone Network)에서 전화 접속하여 오디오/비디오 회의에 참가할 수 있습니다.

전화 접속 회의에 필요한 일부 구성 요소는 전화 접속 회의에 Enterprise Voice. 예를 들어 배포하는 Enterprise Voice 전화 접속 회의에도 필요한 중재 서버 및 PSTN 게이트웨이-구성 요소도 배포해야 합니다. 따라서 전화 접속 회의를 배포하는 방법은 배포 솔루션도 배포하는지 여부에 Enterprise Voice 있습니다.

전화 접속 회의 흐름도 솔루션 배포 여부에 따라 Enterprise Voice 보여줍니다. 다음 표에서는 전화 접속 회의를 배포하는 데 필요한 단계 및 권장 단계에 대한 개요를 제공합니다. 관련 계획 및 프로시저 설명서에 대한 링크도 포함되어 있습니다. 전체 솔루션 계획에 Enterprise Voice 자세한 내용은 [Plan your Enterprise Voice solution in 비즈니스용 Skype 서버.](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)

**전화 접속 회의 흐름도**

![전화 접속 회의 흐름 차트를 배포합니다.](../../media/95d2f963-7705-4930-90bc-df6a71a700bf.png)

**전화 접속 회의 배포 검사 목록**

|**작업 단계**|**단계**|**역할 및 그룹 구성원**|**설명서**|
|:-----|:-----|:-----|:-----|
|**필요한 하드웨어 및 소프트웨어 설치** <br/> | 회의는 프런트 엔드 풀 및 프런트 엔드 서버의 프런트 엔드 서버에서 Standard Edition 실행됩니다. 프런트 엔드 서버에 대한 서버 및 환경 요구 사항을 참조하세요. <br/>  전화 접속 회의를 구성하기 전에 다음을 설치해야 합니다. <br/>  중재 서버 <br/>  PSTN 게이트웨이 <br/>  UCAS(통합 통신 응용 프로그램 서비스)(응용 프로그램 서비스라고도 합니다. <br/>  회의 길잡이 응용 프로그램 <br/>  회의 알림 응용 프로그램 <br/> |로컬 Administrators 그룹의 구성원인 도메인 사용자  <br/> |[비즈니스용 Skype 서버 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [2015년 비즈니스용 Skype 서버 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [회의의 하드웨어 및 소프트웨어 요구 비즈니스용 Skype 서버](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [2016년 8월 전화 접속 회의 비즈니스용 Skype 서버](../../plan-your-deployment/conferencing/dial-in-conferencing.md) <br/> [비즈니스용 Skype 서버](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) <br/> [중재 서버의 토폴로지 작성기에서 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [토폴로지 작성기에서 게이트웨이를 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**중재 서버 및 PSTN 게이트웨이를 포함하여 회의 작업을 포함하는 토폴로지 만들기 및 프런트 엔드 풀 또는 Standard Edition 서버 배포** <br/> |1. 토폴로지 작성기 를 실행하여 토폴로지 구성 토폴로지를 구성할 때 전화 접속 회의 옵션을 선택합니다.  <br/> 2. 토폴로지 게시 및 프런트 엔드 풀 또는 Standard Edition 배포합니다.  <br/> 3. 필요한 경우 독립 실행형 중재 서버를 만들어 PSTN 게이트웨이와 연결합니다.  <br/> **참고:** 이 단계는 중재 서버를 배포하지 Enterprise Voice 프런트 엔드 서버 또는 Enterprise Edition 서버와 함께 배치하지 않는 Standard Edition 필요합니다. 배포 Enterprise Voice 배포의 일부로 중재 서버 및 PSTN 게이트웨이를 Enterprise Voice 구성합니다. 중재 서버를 배치하는 경우 중재 서버를 프런트 엔드 풀 또는 서버 배포의 일부로 Standard Edition 구성합니다. <br/> |DomainAdmins  <br/> RTCUniversalServerAdmins  <br/> 관리자  <br/> |[새 토폴로지 만들기 및 비즈니스용 Skype 서버](../../deploy/install/create-and-publish-new-topology.md) <br/> [중재 서버의 토폴로지 작성기에서 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [토폴로지 작성기에서 게이트웨이를 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**다이얼 플랜을 구성합니다.** <br/> |다이얼 플랜은 특정 위치에서 걸려 온 전화 번호를 전화 권한 부여 및 통화 라우팅을 위해 단일 표준(E.164) 형식으로 변환하는 전화 번호 정규화 규칙 집합입니다. 다른 위치에서 전화 건 동일한 전화 번호는 해당 다이얼 플랜에 따라 각 위치에 적절한 다른 E.164 번호로 확인될 수 있습니다. 배포 Enterprise Voice 해당 배포의 일부로 다이얼 플랜을 설정하고 다이얼 플랜에 전화 접속 회의도 수용할 수 있는지 확인해야 합니다. 배포하지 Enterprise Voice 전화 접속 회의에 대한 다이얼 플랜을 설정해야 합니다.  <br/> 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 셸을 사용하여 다이얼 플랜을 다음과 같이 설정할 수 있습니다.  <br/> 1. 전화 접속 액세스 전화 번호를 라우팅하기 위한 다이얼 플랜을 하나 이상 만들 수 있습니다.  <br/> 2. 각 풀에 기본 다이얼 플랜을 할당합니다. **전화 접속 회의 지역** 을 다이얼 플랜이 적용되는 지리적 위치로 설정합니다. 이 지역은 다이얼 플랜을 전화 접속 액세스 번호와 연결합니다. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[2016에서 전화 접속 회의 비즈니스용 Skype 서버](dial-in-conferencing.md) <br/> [2013에서 다이얼 플랜을 만들거나 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |
|**다이얼 플랜에 지역이 할당되어 있는지 확인** <br/> |**Get-CsDialPlan** 및 **Set-CsDialPlan** cmdlet을 실행하여 모든 다이얼 플랜에 지역이 할당되어 있는지를 확인 합니다. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[2016에서 전화 접속 회의 비즈니스용 Skype 서버](dial-in-conferencing.md) <br/> [2013에서 다이얼 플랜을 만들거나 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> [Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |
|**전화 접속 회의를 지원하도록 회의 정책을 구성합니다.** <br/> | 회의 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 셸을 사용하여 회의 정책 설정을 **구성합니다.** 다음 사항을 지정합니다. <br/>  PSTN 전화 회의 전화 접속 사용 여부 <br/>  사용자가 익명 참가자를 초대할 수 있는지 여부 <br/>  인증되지 않은 사용자가 전화 접속 전화를 사용하여 전화 회의에 참가할 수 있는지 여부. 전화 접속 전화를 사용하면 전화 회의 서버에서 사용자에게 전화를 걸고 사용자는 이 전화에 응답하여 회의에 참가할 수 있습니다.<br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[회의 정책 관리 비즈니스용 Skype 서버](../../manage/conferencing/conferencing-policies.md) <br/> [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |
|**전화 접속 액세스 번호를 구성합니다.** <br/> |비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 사용자가 전화 회의에 전화 접속하기 위해 전화를 걸 수 있는 전화 접속 액세스 번호를 설정하고 액세스 번호를 적절한 다이얼 플랜과 연결되는 지역을 지정합니다. 이끌이의 다이얼 플랜에 지정된 지역에 대한 처음 세 개의 액세스 번호가 전화 회의 초대에 포함됩니다. 모든 액세스 번호는 전화 접속 회의 설정 있습니다.  <br/> **참고:** 전화 접속 액세스 번호를 만든 후 **Set-CsDialInConferencingAccessNumber** cmdlet을 사용하여 사용자가 올바른 액세스 번호를 보다 쉽게 식별할 수 있도록 Active Directory 연락처 개체의 표시 이름을 수정할 수 있습니다. <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[2013에서 다이얼 플랜을 만들거나 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [전화 접속 회의 액세스 번호 비즈니스용 Skype 서버](../../manage/conferencing/access-numbers.md) <br/> [New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**사용자 계정에 줄 URI 할당** <br/> |전화 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 전화 통신 **줄 URI를** 고유한 정규화된 전화 번호(예: )로 구성합니다. `tel:+14255550200` <br/> |RTCUniversalServerAdmins  <br/> CsAdministrator  <br/> CsUserAdministrator  <br/> |[사용자 계정에 줄 URI 할당](dial-in-conferencing.md#BKMK_AssignaLineURI) <br/> |
|**(선택 사항) 사용자 PIN(개인 식별 번호) 요구 사항을 확인하거나 수정합니다.** <br/> |비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 회의 PIN 정책을 보거나 **수정합니다.** 최소 PIN 길이, 최대 로그온 시도 횟수, PIN 만료 날짜 및 공통 패턴 허용 여부를 지정할 수 있습니다.  <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[전화 접속 회의에 대한 PIN 정책 비즈니스용 Skype 서버](../../manage/conferencing/pin-policies.md) <br/> [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |
|**(선택 사항) DTMF 명령의 키 매핑을 수정합니다.** <br/> |**Set-CsDialinConferencingDtmfConfiguration** cmdlet을 사용하여 참가자가 회의 설정(예: 음소거/ 음소거 해제 또는 잠금 및 잠금 해제)을 제어하는 데 사용할 수 있는 DTMF(Dual-Tone Multi-Frequency) 명령에 사용되는 키를 수정할 수 있습니다. <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[2013에서 DTMF 명령에 대한 키 매핑 비즈니스용 Skype 서버](../../manage/conferencing/key-mapping-for-dtmf-commands.md) <br/> [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |
|**(선택 사항) 전화 회의 참가 및 나가기 알림 동작을 수정합니다.** <br/> |**Set-CsDialinConferencingConfiguration** 을 사용하여 참가자가 전화 회의에 참가하고 나갈 때 알림 작동 방식을 변경합니다. <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[회의 참가 및 나가기 공지 사항을 비즈니스용 Skype 서버](../../manage/conferencing/join-and-leave-announcements.md) <br/> [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |
|**(권장) 회의 Director 구성** <br/> |**New-CsConferenceDirectory** cmdlet을 사용하여 풀의 모든 999 사용자에 대해 하나의 회의 디렉터리를 만들 수 있습니다. <br/> |RTCUniversalServerAdmins  <br/> |[(권장) 회의 Director 만들기](/previous-versions/office/lync-server-2013/recommended-create-conference-directories) <br/> [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |
|**(선택 사항) 전화 접속 회의 설정을 확인합니다.** <br/> |**Get-CsDialinConferencingAccessNumber** cmdlet을 사용하여 액세스 번호에 사용되지 않는 전화 접속 회의 지역이 있는 다이얼 플랜 및 할당된 지역이 없는 액세스 번호에 대한 다이얼 플랜을 검색합니다. <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> CsHelpDesk  <br/> |[2016에서 전화 접속 회의 비즈니스용 Skype 서버](dial-in-conferencing.md) <br/> [전화 접속 회의를 테스트합니다비즈니스용 Skype 서버](../../manage/conferencing/tests.md) <br/> [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**(선택 사항) 전화 접속 회의를 확인합니다.** <br/> |**Test-CsDialInConferencing** cmdlet을 사용하여 지정된 풀에 대한 액세스 번호가 올바르게 작동하는지 테스트합니다. <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[전화 접속 회의를 테스트합니다비즈니스용 Skype 서버](../../manage/conferencing/tests.md) <br/> [Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |
|**(선택 사항) 사용자를 전화 접속 회의에 초대하고 초기 PIN을 설정합니다.** <br/> |**Set-CsPinSendCAWelcomeMail** 스크립트를 사용하여 사용자의 초기 PIN을 설정하고 초기 PIN이 포함된 환영 전자 메일과 전화 접속 회의 설정 보낼 수 있습니다. <br/> |RTCUniversalServerAdmins  <br/> |[사용자의 전화 접속 사용자에게 환영 전자 메일을 비즈니스용 Skype 서버](../../manage/conferencing/welcome-emails.md) <br/> |