---
title: Office 365 정부-GCC 배포
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 미국 정부의 규정에 따라 데이터를 처리 하는 엔터티에서 Office 365 배포를 구동 하는 IT 전문가를 위한 지침
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fb916b30a26694debf8d699fc05cc3fcc8c8c77
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581249"
---
# <a name="plan-for-office-365-government---gcc-deployments"></a>Office 365 정부의 GCC 배포 계획

이 지침은 office 365의 배포를 미국 연방, 주, tribal 또는 territorial 정부 기관에 제공 하는 IT 전문가를 위한 것 이며 365, 정부 규정 및 요구 사항을 준수 하는 데이터를 처리 하는 기타 엔터티에서 이러한 요구 사항을 충족 하는 데 적합 합니다. 신규 3 월 26 일: 다운로드 가능한 [GCC 용 빠른 시작 가이드](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)2020를 놓치지 마세요.

> [!IMPORTANT]
> Microsoft 팀은 coronavirus (COVID-19) pandemic으로 인해 온라인 통화 및 오디오/비디오 회의에서 스파이크가 발생 합니다.<br/>
> 
>Microsoft는 microsoft 팀의 GCC 오디오/비디오 서버를 사용 하 여 향상 된 통화를 개선 하 고 현재 정부 데이터 센터와 함께 상업용 데이터 센터에서 처리 용량을 활용할 수 있도록 합니다.<br/>
> 
>이러한 오디오/비디오 서버는 미국 내 Microsoft Azure FedRAMP High 인정 경계 서버 내에 있으며 고객 콘텐츠를 저장 하지 않습니다. 그러나 이러한 서버는 통화와 회의에 대 한 오디오 및 비디오를 처리 하 고 있으며,이 중간 기간 동안 상업적 담당자에 게 서 작동 하 고 있습니다.<br/>
> 
>선별 된 직원은 이러한 서버에 대 한 모든 대화형 로그 기능을 검토 하 여 고객 데이터에 대 한 잠재적인 액세스를 위해 이러한 서버를 모니터링 하 고 있습니다. 고객의 콘텐츠에 대 한 액세스를 위한 GCC 요구 사항을 충족 하는 자격을 갖춘 사람. 차단 요구 사항에 대 한 자세한 내용은 [GCC 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)참조 하세요.<br/>
> 
>이 특별 시간에 서비스가 사용 가능 하 고 안정적으로 유지 되도록 조치를 취할 때의 지원을 요청 해 주셔서 감사 합니다.<br/>


> [!NOTE]
> 조직이 이미 Office 365 정부 자격 요건을 충족 하 여 프로그램에 적용 한 경우 1 ~ 2 단계를 건너뛰고 3 단계로 바로 이동할 수 있습니다. 

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-and-meets-eligibility-requirements"></a>1 단계. 조직에 Office 365 정부-GCC가 필요 하며 자격 요건을 충족 하는지 확인 합니다. 

Office 365 정부-GCC 환경은 FedRAMP 중간을 포함 하 여 클라우드 서비스에 대 한 미국 정부 요구 사항과 범죄 규정 및 납세 정보 시스템 (CJI 및 FTI 데이터 형식)에 대 한 요구 사항을 준수 합니다.

Office 365의 기능과 기능을 활용할 수 있을 뿐만 아니라 Office 365 정부-GCC에 고유 하 게 제공 되는 기능은 다음과 같습니다.

-   조직의 고객 콘텐츠는 Microsoft의 상업용 Office 365 서비스에 있는 고객 콘텐츠에서 논리적으로 분리 됩니다.
-   조직의 고객 콘텐츠는 미국 내에 저장 됩니다.
-   조직의 고객 콘텐츠에 대 한 액세스는 차단 된 Microsoft 담당자만 사용할 수 있습니다.
-   Office 365 정부-GCC는 미국 공공 부문 고객에 게 필요한 인증 및 accreditations을 준수 합니다.

[자격 요건](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)을 포함 하 여 [Office 365 정부 기관](https://products.office.com/government/compare-office-365-government-plans)에서 미국 정부의 고객을 위한 OFFICE 365 정부-GCC 제공에 대 한 자세한 정보를 확인할 수 있습니다.

[Office 365 미국 정부의 서비스 설명은](https://technet.microsoft.com/library/mt774581.aspx) 미국 내의 모임 준수 요구 사항을 중심으로 하는 플랫폼의 이점에 대해 설명 합니다.

> [!Tip]
> 서비스 설명의 정보 테이블을 Excel 통합 문서로 전송 하 고 **조직 y/n과 관련** 된 두 개의 열을 추가 하 고 **조직 y/n의 요구를 충족 하는**것이 좋습니다. 그런 다음 동료와이 목록을 검토 하 여이 서비스가 조직의 요구 사항에 맞는지 확인할 수 있습니다.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>Office 365 정부-GCC가 조직에 적합 한지 여부를 결정 합니다.</li><li>조직이 자격 요건을 충족 하는지 확인 합니다.</li></ul> |

> [!Note]
> Office 365 정부-GCC는 미국 에서만 사용할 수 있습니다. 미국 정부의 고객이 아닌 사용자는 다양 한 [Office 365 정부 계획](https://products.office.com/en/government/compare-office-365-government-plans)중에서 선택할 수 있습니다.


## <a name="step-2-apply-for-office-365-government---gcc"></a>2 단계. Office 365 정부-GCC 용 적용

이 서비스가 조직에 적합 하다 고 결정 한 경우 [여기에서이 서비스에 적용](https://products.office.com/government/eligibility-validation)하는 프로세스를 시작 합니다.

## <a name="step-3-understand-office-365-government---gcc-default-security-settings"></a>3 단계. Office 365 정부 및 GCC 기본 보안 설정에 대해 이해 합니다.

[관리 및 보안 설정을](enable-features-office-365.md) 수정 하기 전에 신중 하 게 검토 하 고 기본 보안 설정을 변경 하기 전에 준수에 영향을 주는 것이 좋습니다.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>판단 요점|<ul><li>기본 Office 365 정부 보안 설정을 수정 하 고, 먼저 변경 사항에 대 한 영향을 확인 하기 위해 해결 하도록 할 것인지 여부를 결정 합니다.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>4 단계. 기본적으로 현재 사용할 수 없거나 사용 불가능 한 기능을 파악 합니다.

귀하의 정부 클라우드 고객의 요구 사항을 충족 하기 위해 Office 365 정부-GCC와 엔터프라이즈 요금제에는 몇 가지 차이점이 있습니다. 사용할 수 있는 기능을 확인 하려면 다음 표를 참조 하세요.

[Microsoft 팀 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> 다른 작업을 GCC 클라우드에서 완전히 사용할 수 있게 되 면 모든 추가 통합 작업이 완료 되 면 팀에서 사용할 수 있게 됩니다.


|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>판단 요점|<ul><li>팀 기능 집합이 조직의 요구 사항에 맞는지 여부를 결정 합니다.</li></ul> |

## <a name="step-5-plan-for-governance"></a>5 단계. 관리 계획

관리에 대 한 요구 사항과이를 충족 하는 방법을 결정 합니다. 자세한 내용은 [팀의 관리 계획](plan-teams-governance.md) 으로 이동 하세요.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>판단 요점|<ul><li>[팀의 관리 계획에 대 한](plan-teams-governance.md)지침에 따라 관리 요구 사항을 결정 하 고 문서화 합니다.</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>6 단계. 공동 작업을 위해 팀 배포

Office 365 정부-GCC에 onboarded 한 후에 Microsoft 팀을 배포 하 [는 방법](How-to-roll-out-teams.md)에 대해 설명 하는 권장 구축 경로를 따르세요. 채택 및 변경 관리 팀과 팀이 챔피언을 사용 하 여 참여 해야 합니다.

[Fasttrack](https://www.microsoft.com/fasttrack) 또는 선택한 파트너를 통해 서비스를 온보드 할 수도 있습니다.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>7 단계. 모임 및 음성 용 팀 배포

또한 더 광범위 한 관련자 그룹의 팀을 사용 하 여 모임 및 [클라우드 음성 기능](cloud-voice-deployment.md)롤아웃 계획을 시작 하는 데는 상당한 시간이 소요 됩니다.

