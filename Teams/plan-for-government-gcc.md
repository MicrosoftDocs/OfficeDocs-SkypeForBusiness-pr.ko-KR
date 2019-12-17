---
title: Microsoft 365 정부의 GCC 배포 계획-Microsoft 팀
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 미국 정부의 규정에 따라 데이터를 처리 하는 엔터티에서 Office 365 배포를 구동 하는 IT 전문가를 위한 지침
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4228210fa7b6d9518fa060b2bdd555f434ed6f2
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069309"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Microsoft 365 정부의 GCC 배포 계획

이 지침은 Microsoft를 사용 하는 미국 연방, 주, tribal 또는 territorial 정부 기관 또는 정부 규정에 따른 데이터를 처리 하는 기타 엔터티에서 제공 하는 IT 365 전문가를 위한 것입니다. 365 정부-GCC는 이러한 요구 사항을 충족 하는 데 적합 합니다.

> [!NOTE]
> 조직이 Microsoft 365 정부 자격 요건을 충족 하 여 프로그램에 적용 한 경우에는 1 ~ 2 단계를 건너뛰고 3 단계로 바로 이동할 수 있습니다. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>1 단계. 조직에 Microsoft 365 정부 GCC가 필요 하며 자격 요건을 충족 하는지 확인 합니다. 

Microsoft 365 정부-GCC 환경은 FedRAMP 중간을 포함 하 여 클라우드 서비스에 대 한 미국 정부 요구 사항과 범죄 규정 및 납세 정보 시스템 (CJI 및 FTI 데이터 형식)에 대 한 요구 사항을 준수 합니다.

Office 365의 기능과 기능을 활용할 수 있을 뿐만 아니라, Microsoft 365 정부-GCC에는 다음과 같은 기능이 제공 됩니다.

-   조직의 고객 콘텐츠는 Microsoft의 상업용 Office 365 서비스에 있는 고객 콘텐츠에서 논리적으로 분리 됩니다.
-   조직의 고객 콘텐츠는 미국 내에 저장 됩니다.
-   조직의 고객 콘텐츠에 대 한 액세스는 차단 된 Microsoft 담당자만 사용할 수 있습니다.
-   Microsoft 365 정부-GCC는 미국 공공 부문 고객에 게 필요한 인증 및 accreditations을 준수 합니다.

[자격 요건](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)을 포함 하 여 [Office 365 정부 계획](https://products.office.com/government/compare-office-365-government-plans)에서 미국 정부의 고객을 위한 Microsoft 365 정부 GCC 제공에 대 한 자세한 정보를 확인할 수 있습니다.

[Office 365 미국 정부의 서비스 설명은](https://technet.microsoft.com/library/mt774581.aspx) 미국 내의 모임 준수 요구 사항을 중심으로 하는 플랫폼의 이점에 대해 설명 합니다.

> [!Tip]
> 서비스 설명의 정보 테이블을 Excel 통합 문서로 전송 하 고 **조직 y/n과 관련** 된 두 개의 열을 추가 하 고 **조직 y/n의 요구를 충족 하는**것이 좋습니다. 그런 다음 동료와이 목록을 검토 하 여이 서비스가 조직의 요구 사항에 맞는지 확인할 수 있습니다.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>Microsoft 365 정부-GCC가 조직에 적합 한지 여부를 결정 합니다.</li><li>조직이 자격 요건을 충족 하는지 확인 합니다.</li></ul> |

> [!Note]
> Microsoft 365 정부-GCC는 미국 에서만 사용할 수 있습니다. 미국 정부의 고객이 아닌 사용자는 다양 한 [Office 365 정부 계획](https://products.office.com/en/government/compare-office-365-government-plans)중에서 선택할 수 있습니다.


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>2 단계. Microsoft 365 정부 에디션 (GCC)에 적용

이 서비스가 조직에 적합 하다 고 결정 한 경우 [여기에서이 서비스에 적용](https://products.office.com/government/eligibility-validation)하는 프로세스를 시작 합니다.

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>3 단계. Microsoft 365 정부의 GCC 기본 보안 설정에 대해 이해 합니다.

[관리 및 보안 설정을](enable-features-office-365.md) 수정 하기 전에 신중 하 게 검토 하 고 기본 보안 설정을 변경 하기 전에 준수에 영향을 주는 것이 좋습니다.

|    |     |
|-----------|------------|
| ![결정 지점을 가리키는 아이콘](media/audio_conferencing_image7.png) <br/>판단 요점|<ul><li>기본 Microsoft 365 정부-GCC 보안 설정 중 어떤 것을 수정 하 고 있는지 확인 하 고, 먼저 변경 사항에 대 한 영향을 파악 합니다.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>4 단계. 기본적으로 현재 사용할 수 없거나 사용 불가능 한 기능을 파악 합니다. 

귀하의 정부 클라우드 고객의 요구 사항을 충족 하기 위해 Microsoft 365 정부-GCC 및 Enterprise 요금제 간에는 몇 가지 차이점이 있습니다. 사용할 수 있는 기능을 확인 하려면 다음 표를 참조 하세요.

|                             | 기능                     | GCC            |
|-----------------------------|-----------------------------|----------------|
| 기반의 | 로그인 | 공간이 |
| | 현재 상태 | 공간이 |
| | 통합 현재 상태 (비즈니스용 Skype 및 팀 통합) | 공간이 |
| 작동이 | 피드 | 공간이 |
|  | 내 활동 | 공간이 |
| 채팅 | 주제별로 | 공간이 |
| | 파일 | 공간이 |
| | 조직도 | 공간이 |
| | 작동이 | 공간이 |
| | InterOp (1:1 팀-비즈니스용 Skype 채팅) | 공간이 |
| Teams | 채널 메시지 | 공간이 |
| | 채널 파일 | 공간이 |
| | OneNote 탭 | 정부 백로그 |
| | 채널을 전자 메일로 보내기 | 사용할 수 없음 |
| | 구성원 추가 | 공간이 |
| | 게스트 액세스 | 공간이 |
| 모임 | 모임 예약 | 공간이 |
| | 모임 참가 | 공간이 |
| | VoIP 모임 | 공간이 |
| | 데스크톱 공유 | 공간이 |
| | 공유 하 고 제어권을 부여 합니다. | 공간이 |
| | 회의실에서 연결 | 공간이 |
| | 익명 참가 | 공간이 |
| | 클라우드 기록 | 공간이 |
| | 모임 메모 | 공간이 |
| | 라이브 이벤트 | 공간이 |
| | 페더레이션된 모임 | 공간이 |
| | Surface Hub 지원 | 공간이 |
| 전화가 | 연락처 | 공간이 |
| | 역사 | 공간이 |
| | 음성 메일 | 공간이 |
| | VoIP 통화 | 공간이 |
| | 비즈니스용 Skype-팀 전화 | 공간이 |
| | 통화 플랜 | 공간이 |
| | 오디오 회의 (모임 참가자가 PSTN을 통해 참가 하도록 허용) | 공간이 |
| | Microsoft 전화 시스템 다이렉트 라우팅 | 공간이 |
| | PSTN 호출자 용 대기실 | 공간이 |
| | 통화 대기열 | 공간이 |
| | 상사 및 대리인 지원 | 공간이 |
| | Consultative 및 안전한 전송 | 공간이 |
| | 혁신을 방해 하지 않음 | 공간이 |
| | 특수 전화 벨 소리 | 공간이 |
| | 팀, 비즈니스용 Skype, PSTN 참가자와의 그룹 통화 확대 1:1 | 공간이 |
| | 그룹으로 전달 | 공간이 |
| | PSTN 통화로 전송 | 공간이 |
| | 비상 전화 통화 요금제 | 공간이 |
| | 기존 인증 된 SIP 전화 지원 | 공간이 |
| | USB HID | 공간이 |
| | 통화 및 모임 모두에 대해 eDiscovery | 공간이 |
| | 조직 자동 전화 교환 | 공간이 |
| | Skype 소비자-팀 전화 지원 | 공간이 |
| 파일 | 최근 | 공간이 |
| | Microsoft Teams | 공간이 |
| 스토어 | App Store | 정부 백로그 |
| 찾아 | 보내는 | 공간이 |
| | 사용자 | 공간이 |
| | 파일 | 공간이 |
| | 슬래시 명령 | 공간이 |
| 충족 | 콘텐츠 검색 준수 | 공간이 |
| | 보관 | 공간이 |
| | 감사 로그 검색 | 공간이 |
| | 법률 보류 | 공간이 |
| | eDiscovery | 공간이 |

> [!Note]

> 다른 작업을 GCC 클라우드에서 완전히 사용할 수 있게 되 면 모든 추가 통합 작업이 완료 되 면 팀에서 사용할 수 있게 됩니다.


|    |     |
|-----------|------------|
| ![결정 지점을 가리키는 아이콘](media/audio_conferencing_image7.png) <br/>판단 요점|<ul><li>팀 기능 집합이 조직의 요구 사항에 맞는지 여부를 결정 합니다.</li></ul> |

## <a name="step-5-plan-for-governance"></a>5 단계. 관리 계획

관리에 대 한 요구 사항과이를 충족 하는 방법을 결정 합니다. 자세한 내용은 [팀의 관리 계획](plan-teams-governance.md) 으로 이동 하세요.

|    |     |
|-----------|------------|
| ![결정 지점을 가리키는 아이콘](media/audio_conferencing_image7.png) <br/>판단 요점|<ul><li>[팀의 관리 계획에 대 한](plan-teams-governance.md)지침에 따라 관리 요구 사항을 결정 하 고 문서화 합니다.</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>6 단계. 공동 작업을 위해 팀 배포

Microsoft 365 정부-GCC에 onboarded 한 후에 Microsoft 팀을 배포 하 [는 방법](How-to-roll-out-teams.md)에 대해 설명 하는 권장 구축 경로를 따르세요. 채택 및 변경 관리 팀과 팀이 챔피언을 사용 하 여 참여 해야 합니다.

[Fasttrack](https://www.microsoft.com/fasttrack) 또는 선택한 파트너를 통해 서비스를 온보드 할 수도 있습니다.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>7 단계. 모임 및 음성 용 팀 배포

또한 더 광범위 한 관련자 그룹의 팀을 사용 하 여 모임 및 [클라우드 음성 기능](cloud-voice-deployment.md)롤아웃 계획을 시작 하는 데는 상당한 시간이 소요 됩니다.

