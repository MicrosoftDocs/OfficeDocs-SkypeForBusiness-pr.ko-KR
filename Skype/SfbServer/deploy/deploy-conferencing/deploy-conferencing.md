---
title: 비즈니스용 Skype 서버에서 회의 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26dff7d8-242a-4576-9870-d6d461758a37
description: '요약: 비즈니스용 Skype 서버에서 회의를 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: 34405084833bbdc5e65a6cc82ebc310718629296
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768551"
---
# <a name="deploy-conferencing-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 회의 배포

**요약:** 비즈니스용 Skype 서버에서 회의를 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.

비즈니스용 Skype 서버에서 사용할 수 있는 회의에는 웹 회의, 오디오 및 비디오 (A/V) 회의, 전화 접속 회의, 인스턴트 메시지 (IM) 회의의 네 가지 유형이 있습니다. 필요에 따라 모든 회의 유형을 사용 하도록 설정 하거나 한 가지 유형만 사용할 수 있습니다.

비즈니스용 Skype 서버를 배포 하는 경우 메신저 대화 회의 기능이 자동으로 배포 됩니다. 토폴로지 작성기를 사용 하 여 새 토폴로지를 만들고 게시 하는 경우 다음 검사 목록의 설명과 같이 웹, A/V 및 전화 접속 회의를 배포할지 여부를 지정 합니다.

- [웹 및 오디오/비디오 회의를 위한 배포 검사 목록](deploy-conferencing.md#BKMK_ChecklistWebConferencing)

- [전화 접속 회의를 위한 배포 순서도 및 검사 목록](deploy-conferencing.md#BKMK_DialinConferencing)

회의를 배포 하기 전에 다음 계획 항목을 읽어야 합니다.

- [비즈니스용 Skype 서버에서 회의 계획](../../plan-your-deployment/conferencing/conferencing.md)

- [비즈니스용 Skype 서버에서의 회의 하드웨어 및 소프트웨어 요구 사항](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)

- [비즈니스용 Skype 서버에 대 한 회의 토폴로지 계획](../../plan-your-deployment/conferencing/conferencing-topology.md)

- [비즈니스용 Skype 서버의 전화 접속 회의 계획](../../plan-your-deployment/conferencing/dial-in-conferencing.md)

- [비즈니스용 Skype 서버에서 대규모 모임 계획](../../plan-your-deployment/conferencing/large-meetings.md)

## <a name="deployment-checklist-for-web-and-audiovideo-conferencing"></a>웹 및 오디오/비디오 회의를 위한 배포 검사 목록
<a name="BKMK_ChecklistWebConferencing"> </a>

다음 표에서는 기존 토폴로지에 웹 및 오디오/비디오 회의를 배포 하는 데 필요한 단계에 대해 간략하게 설명 합니다. 관련 계획 및 절차 문서에 대 한 링크가 포함 되어 있습니다.

|**단계의**|**방법은**|**역할 및 그룹 구성원**|**설명서**|
|:-----|:-----|:-----|:-----|
|**필수 하드웨어 및 소프트웨어 설치** <br/> |프론트 엔드 풀과 Standard Edition 서버의 프런트 엔드 서버에서 회의가 실행 됩니다. 프런트 엔드 서버에 대 한 서버 및 환경 요구 사항을 참조 하세요.  <br/> 웹 회의를 사용 하도록 설정 하는 경우 비즈니스용 Skype 서버가 PowerPoint 프레젠테이션 공유 및 렌더링을 처리 하는 데 사용 되는 Office Web Apps 서버와 통신할 수 있는지 확인 해야 합니다.  <br/> 웹 회의의 경우 파일 저장소로 사용할 파일 공유도 지정 해야 합니다.  <br/> 비즈니스용 Skype 클라이언트에서 외부 사용자가 회의에 참가할 수 있도록 설정 하 고 싶으신가요? 그렇다면 Edge 서버를 배포 해야 합니다.  <br/> |로컬 관리자 그룹의 구성원 인 도메인 사용자  <br/> | [비즈니스용 Skype 서버 2019에 대 한 서버 요구 사항](../../../SfBServer2019/plan/system-requirements.md) <br> [비즈니스용 Skype 서버 2015의 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [비즈니스용 Skype 서버 2015에 대한 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [비즈니스용 Skype 서버에서의 회의 하드웨어 및 소프트웨어 요구 사항](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [비즈니스용 Skype 서버에서 Office Web Apps 서버와 통합 구성](office-web-app-server.md) <br/> [비즈니스용 Skype 서버에서 파일 공유 만들기](../../deploy/install/create-a-file-share.md) <br/> [비즈니스용 Skype 서버 2015의 Edge 서버 배포 계획](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) <br/> [비즈니스용 Skype 서버 2015에 Edge 서버 배포](../../deploy/deploy-edge-server/deploy-edge-server.md) <br/> |
|**회의를 지원 하기 위해 적절 한 내부 토폴로지 만들기** <br/> |토폴로지 작성기를 실행 하 여 토폴로지에 회의를 추가한 다음 토폴로지를 게시 해야 합니다.  <br/> |토폴로지를 정의 하려면 로컬 사용자 그룹의 구성원 인 계정  <br/> 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원이 며 토폴로지를 비즈니스용 Skype Server 파일 저장소에 사용할 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)을가지고 있는 계정 (토폴로지 작성기가 필수 Dacl을 구성할 수 있도록)을 게시 하려면  <br/> |[비즈니스용 Skype 서버에서 새 토폴로지 만들기 및 게시](../../deploy/install/create-and-publish-new-topology.md) <br/> |
|**회의 정책 및 구성 설정 구성** <br/> |비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 회의 정책 및 구성 설정을 구성 합니다.  <br/> |RTCUniversalServerAdmins 그룹 (Windows PowerShell에만 해당) 또는 CSAdministrator 역할에 사용자 할당  <br/> |[비즈니스용 Skype 서버에서 회의 정책 관리](../../manage/conferencing/conferencing-policies.md) <br/> [비즈니스용 Skype 서버에서 모임 구성 설정 관리](../../manage/conferencing/meeting-configuration-settings.md) <br/> [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> [New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |

## <a name="deployment-flowchart-and-checklist-for-dial-in-conferencing"></a>전화 접속 회의를 위한 배포 순서도 및 검사 목록
<a name="BKMK_DialinConferencing"> </a>

 전화 접속 회의를 통해 사용자는 PSTN (공개 전환 전화 네트워크)에서 전화를 걸어 오디오/비디오 회의에 참가할 수 있습니다.

전화 접속 회의에 필요한 일부 구성 요소는 엔터프라이즈 음성에도 사용 됩니다. 예를 들어 엔터프라이즈 음성을 배포 하는 경우에도 전화 접속 회의에 필요한 중재 서버 및 PSTN 게이트웨이 구성 요소를 배포 해야 합니다. 전화 접속 회의를 배포 하는 방법은 사용자가 엔터프라이즈 음성 솔루션을 배포 하 고 있는지 여부에 따라 달라 집니다.

전화 접속 회의 순서도에는 엔터프라이즈 음성 솔루션을 배포 하 고 있는지 여부에 따라 따라야 할 단계가 나와 있습니다. 순서도 다음의 표에는 전화 접속 회의를 배포 하는 데 필요한 단계 및 권장 되는 단계가 설명 되어 있습니다. 관련 계획 및 절차 문서에 대 한 링크도 포함 되어 있습니다. 전체 엔터프라이즈 음성 솔루션을 계획 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 엔터프라이즈 음성 솔루션 계획](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)을 참조 하세요.

**전화 접속 회의 순서도**

![전화 접속 회의 흐름 차트 배포](../../media/95d2f963-7705-4930-90bc-df6a71a700bf.png)

**전화 접속 회의 배포 검사 목록**

|**단계의**|**방법은**|**역할 및 그룹 구성원**|**설명서**|
|:-----|:-----|:-----|:-----|
|**필수 하드웨어 및 소프트웨어 설치** <br/> | 프론트 엔드 풀과 Standard Edition 서버의 프런트 엔드 서버에서 회의가 실행 됩니다. 프런트 엔드 서버에 대 한 서버 및 환경 요구 사항을 참조 하세요. <br/>  전화 접속 회의를 구성 하기 전에 다음이 설치 되어 있는지 확인 해야 합니다. <br/>  중재 서버 <br/>  PSTN 게이트웨이 <br/>  통합 커뮤니케이션 응용 프로그램 서비스 (c) (응용 프로그램 서비스 라고 함) <br/>  회의 수행자 응용 프로그램 <br/>  회의 알림 신청 <br/> |로컬 관리자 그룹의 구성원 인 도메인 사용자  <br/> |[비즈니스용 Skype 서버 2015의 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [비즈니스용 Skype 서버 2015에 대한 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [비즈니스용 Skype 서버에서의 회의 하드웨어 및 소프트웨어 요구 사항](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [비즈니스용 Skype 서버의 전화 접속 회의 계획](../../plan-your-deployment/conferencing/dial-in-conferencing.md) <br/> [비즈니스용 Skype 서버의 중재 서버 구성 요소](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) <br/> [비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버 배포](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [비즈니스용 Skype 서버의 토폴로지 작성기에서 게이트웨이 정의](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**조정 서버 및 PSTN 게이트웨이를 포함 하 여 회의 작업량을 포함 하는 토폴로지를 만들고 프런트 엔드 풀 또는 Standard Edition 서버를 배포 합니다.** <br/> |1. 토폴로지 작성기를 실행 하 여 토폴로지를 구성 합니다. 토폴로지를 구성 하는 동안 전화 접속 회의 옵션을 선택 합니다.  <br/> 2. 토폴로지를 게시 하 고 프런트 엔드 풀 또는 Standard Edition 서버를 배포 합니다.  <br/> 3. 필요에 따라 독립 실행형 중재 서버를 만들고 PSTN 게이트웨이와 연결 합니다.  <br/> **참고:** 엔터프라이즈 음성을 배포 하지 않고 Enterprise Edition 프런트 엔드 서버 또는 Standard Edition 서버를 사용 하 여 중재 서버를 collocate 하지 않는 경우에만이 단계가 필요 합니다. 엔터프라이즈 음성을 배포 하는 경우 엔터프라이즈 음성 배포의 일부로 중재 서버와 PSTN 게이트웨이를 설치 하 고 구성 합니다. 중재 서버를 collocate 경우에는 프런트 엔드 풀 또는 Standard Edition Server 배포의 일부로 중재 서버를 설치 하 고 구성 합니다. <br/> |도메인 관리자  <br/> RTCUniversalServerAdmins  <br/> 관리자  <br/> |[비즈니스용 Skype 서버에서 새 토폴로지 만들기 및 게시](../../deploy/install/create-and-publish-new-topology.md) <br/> [비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버 배포](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [비즈니스용 Skype 서버의 토폴로지 작성기에서 게이트웨이 정의](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**다이얼 플랜 구성** <br/> |다이얼 플랜은 전화 인증 및 통화 라우팅과 관련 하 여 특정 위치에서 전화를 거는 번호를 단일 표준 (E) 형식으로 변환 하는 일련의 전화 번호 정규화 규칙입니다. 다른 위치에서 전화를 거는 같은 번호는 각각의 다이얼 플랜을 기준으로 각 위치에 따라 다른 전자 164 번호로 확인 될 수 있습니다. 엔터프라이즈 음성을 배포 하는 경우에는 해당 배포의 일부로 다이얼 플랜을 설정 하 고 다이얼 인 회의도 함께 사용할 수 있는지 확인 해야 합니다. 엔터프라이즈 음성을 배포 하지 않는 경우 전화 접속 회의를 위한 다이얼 플랜을 설정 해야 합니다.  <br/> 비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 다음과 같이 다이얼 플랜을 설정 합니다.  <br/> 1. 전화 접속 액세스 전화 번호 라우팅에 대 한 하나 이상의 다이얼 플랜을 만듭니다.  <br/> 2. 각 풀에 기본 다이얼 플랜을 할당 합니다. 전화 접속 **회의 지역을** 다이얼 플랜을 적용할 지리적 위치로 설정 합니다. 지역에서 다이얼 플랜을 전화 접속 액세스 번호와 연결 합니다. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype 서버에서 전화 접속 회의 구성](dial-in-conferencing.md) <br/> [비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [새 CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |
|**다이얼 플랜에 영역이 할당 되어 있는지 확인** <br/> |**Get-CsDialPlan 플랜** 및 **Set-csdialplan 플랜** cmdlet을 실행 하 여 모든 다이얼 플랜에 지역이 지정 되어 있는지 확인 합니다. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype 서버에서 전화 접속 회의 구성](dial-in-conferencing.md) <br/> [비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [가져오기-CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> [Set CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |
|**전화 접속 회의를 지원 하도록 회의 정책 구성** <br/> | Skype for Business Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 **회의 정책** 설정을 구성 합니다. 여부 지정: <br/>  PSTN 회의 전화 접속을 사용할 수 있습니다. <br/>  사용자가 익명 참가자를 초대할 수 있습니다. <br/>  인증 되지 않은 사용자는 전화 걸기 phoning를 사용 하 여 회의에 참가할 수 있습니다. 전화 걸기 phoning를 사용 하 여 회의 서버는 사용자에 게 전화를 걸고 사용자는 해당 휴대폰에 응답 하 여 회의에 참가할 수 있습니다. <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype 서버에서 회의 정책 관리](../../manage/conferencing/conferencing-policies.md) <br/> [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |
|**전화 접속 액세스 번호 구성** <br/> |비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 사용자가 전화 접속으로 전화를 걸고 해당 전화 접속 요금제에 연결 하는 지역 번호를 지정 합니다. 이끌이 다이얼 플랜에서 지정한 영역의 처음 세 개 액세스 번호는 회의 초대에 포함 됩니다. 모든 액세스 번호는 전화 접속 회의 설정 페이지에서 사용할 수 있습니다.  <br/> **참고:** 전화 접속 액세스 번호를 만든 후에는 **CsDialInConferencingAccessNumber** cmdlet을 사용 하 여 Active Directory 연락처 개체의 표시 이름을 수정 하 고 사용자가 올바른 액세스 번호를 더 쉽게 식별할 수 있도록 설정할 수 있습니다. <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호 관리](../../manage/conferencing/access-numbers.md) <br/> [새로운 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**사용자 계정에 줄 URI 지정** <br/> |비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 전화 통신 **회선 URI** 를 고유한 정규화 된 전화 번호로 구성 합니다 (예를 들어, tel: + 14255550200). <br/> |RTCUniversalServerAdmins  <br/> CsAdministrator  <br/> CsUserAdministrator  <br/> |[사용자 계정에 줄 URI 지정](dial-in-conferencing.md#BKMK_AssignaLineURI) <br/> |
|**) 사용자 개인 id 번호 (PIN) 요구 사항 확인 또는 수정** <br/> |Skype for Business Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 회의 **PIN 정책을**보거나 수정 합니다. 최소 PIN 길이, 최대 로그온 시도 횟수, PIN 만료, 공통 패턴 허용 여부를 지정할 수 있습니다.  <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype 서버에서 전화 접속 회의를 위한 PIN 정책 관리](../../manage/conferencing/pin-policies.md) <br/> [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |
|**) DTMF 명령의 키 매핑 수정** <br/> |**CsDialinConferencingDtmfConfiguration** cmdlet을 사용 하 여 참가자가 전화 회의 설정을 제어 하는 데 사용할 수 있는 이중 톤 다중 주파수 (DTMF) 명령에 사용 되는 키를 수정 합니다 (예: 음소거 및 음소거 해제 또는 잠금 및 잠금 해제). <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype 서버의 DTMF 명령에 대 한 키 매핑 관리](../../manage/conferencing/key-mapping-for-dtmf-commands.md) <br/> [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |
|**) 컨퍼런스 참가 및 알림 종료 동작 수정** <br/> |**CsDialinConferencingConfiguration** 를 사용 하 여 참가자가 회의에 참가 하 고 나갈 때 알림이 작동 하는 방식을 변경할 수 있습니다. <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype 서버에서 컨퍼런스 참가 및 공지 사항 관리](../../manage/conferencing/join-and-leave-announcements.md) <br/> [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |
|**권장 컨퍼런스 디렉터리 구성** <br/> |**CsConferenceDirectory** cmdlet을 사용 하 여 풀의 모든 999 사용자에 대해 하나의 회의 디렉터리를 만듭니다. <br/> |RTCUniversalServerAdmins  <br/> |[(권장) 전화 회의 디렉터리 만들기](https://technet.microsoft.com/library/787f4c94-1c96-468a-a74d-e06b7bd4b8a3.aspx) <br/> [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |
|**(선택 사항) 전화 접속 회의 설정 확인** <br/> |**CsDialinConferencingAccessNumber** cmdlet을 사용 하 여 액세스 번호 및 지역이 지정 되지 않은 액세스 번호에 사용 되지 않는 전화 접속 회의 영역이 있는 다이얼 플랜을 검색할 수 있습니다. <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> Csviewadministrator  <br/> CsHelpDesk  <br/> |[비즈니스용 Skype 서버에서 전화 접속 회의 구성](dial-in-conferencing.md) <br/> [비즈니스용 Skype 서버에서 전화 접속 회의 테스트](../../manage/conferencing/tests.md) <br/> [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**(선택 사항) 전화 접속 회의 확인** <br/> |**CsDialInConferencing** cmdlet을 사용 하 여 지정 된 풀에 대 한 액세스 번호가 올바르게 작동 하는지 테스트 합니다. <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype 서버에서 전화 접속 회의 테스트](../../manage/conferencing/tests.md) <br/> [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |
|**) 사용자가 전화 접속 회의를 시작 하 고 초기 PIN 설정** <br/> |**CsPinSendCAWelcomeMail** 스크립트를 사용 하 여 사용자의 초기 핀을 설정 하 고 초기 PIN 및 전화 접속 회의 설정 페이지로 연결 되는 링크가 포함 된 환영 전자 메일을 보낼 수 있습니다. <br/> |RTCUniversalServerAdmins  <br/> |[비즈니스용 Skype 서버에서 전화 접속 사용자에 게 환영 전자 메일 보내기](../../manage/conferencing/welcome-emails.md) <br/> |


