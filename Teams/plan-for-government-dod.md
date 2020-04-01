---
title: Microsoft 365 정부 기관-DoD 배포에 대 한 계획-Microsoft 팀
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 미국 정부의 DoD 규정에 대 한 데이터를 처리 하는 엔터티에서 Office 365 배포를 구동 하는 IT 전문가를 위한 지침입니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82c7c8625ca5fcdab7325cf74fcde0c60049da07
ms.sourcegitcommit: 4e1647d19501b37860d9fc79370fa4347f76f85f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43079450"
---
# <a name="plan-for-microsoft-365-government---dod-deployments"></a>Microsoft 365 정부 기관-DoD 배포 계획

본 가이드는 미국 연방 정부 기관에서 Office 365를 배포 하는 IT 전문가를 위한 것 이며, 정부 규정 및 요구 사항을 준수 하는 데이터를 처리 하는 기타 엔터티에서 이러한 요구 사항을 충족 하는 데 적절 한 Microsoft 365 정부 기관 사용

> [!NOTE]
> 조직에서 이미 Microsoft 365 정부 – DoD 자격 요건을 충족 하 고 해당 프로그램에 적용 한 경우에는 1 ~ 2 단계를 건너뛰고 3 단계로 바로 이동할 수 있습니다.

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---dod-and-meets-eligibility-requirements"></a>1 단계. 조직에 Microsoft 365 정부-DoD를 요구 하 고 자격 요건을 충족 하는지 여부를 확인 합니다. 

Microsoft 365 정부 기관-DoD 환경은 클라우드 서비스에 대 한 미국 정부 요구 사항을 준수 합니다. Office 365의 기능과 기능을 활용할 수 있을 뿐만 아니라, Microsoft 365 정부에 고유한 다음과 같은 기능을 통해 조직에서 혜택을 얻을 수도 있습니다.

- 조직의 고객 콘텐츠는 Microsoft의 상업용 Office 365 서비스에 있는 고객 콘텐츠에서 논리적으로 분리 됩니다.
- 조직의 고객 콘텐츠는 미국 내에 저장 됩니다.
- 조직의 고객 콘텐츠에 대 한 액세스는 차단 된 Microsoft 담당자만 사용할 수 있습니다.
- Microsoft 365 정부 – DoD는 미국 공공 부문 고객에 게 필요한 인증 및 accreditations을 준수 합니다.

[자격 요건](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)을 포함 하 여 [Office 365 정부 계획](https://products.office.com/government/compare-office-365-government-plans)에서 미국 정부의 고객을 위한 Microsoft 365 정부에 대 한 자세한 정보를 확인할 수 있습니다.

[Office 365 미국 정부의 서비스 설명은](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 미국 내의 모임 준수 요구 사항을 중심으로 하는 플랫폼의 이점에 대해 설명 합니다.


> [!Tip]
> 서비스 설명의 정보 테이블을 Excel 통합 문서로 전송 하 고 **조직 y/n과 관련** 된 두 개의 열을 추가 하 고 **조직 y/n의 요구를 충족 하는**것이 좋습니다. 그런 다음 동료와이 목록을 검토 하 여이 서비스가 조직의 요구 사항에 맞는지 확인할 수 있습니다.


|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>Microsoft 365 정부-DoD가 조직에 적합 한지 여부를 결정 합니다.</li><li>조직이 자격 요건을 충족 하는지 확인 합니다.</li></ul> |

> [!Note]
> Microsoft 365 정부-DoD는 미국 에서만 사용할 수 있습니다. 미국 정부의 고객이 아닌 사용자는 다양 한 [Office 365 정부 계획](https://products.office.com/en/government/compare-office-365-government-plans)중에서 선택할 수 있습니다.

## <a name="step-2-apply-for-microsoft-365-government---dod"></a>2 단계. Microsoft 365 정부 기관에 적용-DoD

이 서비스가 조직에 적합 하다 고 결정 한 경우 [이 서비스에 대 한 적용](https://products.office.com/government/eligibility-validation)프로세스를 시작 합니다.


## <a name="step-3-understand-microsoft-365-government---dod-default-security-settings"></a>3 단계. Microsoft 365 정부의 기본 보안 설정에 대해 이해 합니다.

[관리 및 보안 설정을](enable-features-office-365.md) 수정 하기 전에 신중 하 게 검토 하 고 기본 보안 설정을 변경 하기 전에 준수에 영향을 주는 것이 좋습니다.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>판단 요점|<ul><li>기본 Microsoft 365 정부 보안 설정 중 어떤 것을 수정 해야 하는지 결정 합니다. 먼저 변경 사항에 대 한 영향을 이해 하기 위해 확인 합니다.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---dod"></a>4 단계. 현재 Microsoft 365 정부 기관에서 사용할 수 있는 팀 기능 이해-DoD

귀하의 정부 클라우드 고객의 요구 사항을 충족 하기 위해 Microsoft 365 정부-DoD 및 Enterprise 계획의 팀에는 몇 가지 차이점이 있습니다. 사용할 수 있는 기능을 확인 하려면 다음 표를 참조 하세요.

[Microsoft 팀 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>5 단계. 관리 계획

관리에 대 한 요구 사항과이를 충족 하는 방법을 결정 합니다. 자세한 내용은 [팀의 관리 계획](plan-teams-governance.md) 으로 이동 하세요.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|판단 요점 |<ul><li>[팀의 관리 계획에 대 한](plan-teams-governance.md)지침에 따라 관리 요구 사항을 결정 하 고 문서화 합니다. </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>6 단계. 공동 작업을 위해 팀 배포

Microsoft 365 정부 \ e e e – e e onboarded 된 후에는 Microsoft 팀을 배포 하 [는 방법](How-to-roll-out-teams.md)에 대해 설명 하는 권장 되는 배포 경로를 따르세요. 채택 및 변경 관리 팀과 팀이 챔피언을 사용 하 여 참여 해야 합니다.

[Fasttrack](https://www.microsoft.com/fasttrack) 또는 선택한 파트너를 통해 서비스를 온보드 할 수도 있습니다.
