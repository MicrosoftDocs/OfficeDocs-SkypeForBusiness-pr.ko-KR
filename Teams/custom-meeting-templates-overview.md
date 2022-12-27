---
title: Microsoft Teams의 사용자 지정 모임 템플릿 개요
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
appliesto:
- Microsoft Teams
description: Microsoft Teams Premium의 사용자 지정 모임 템플릿에 대해 알아봅니다.
ms.openlocfilehash: 0ed766141e09b9c26d8e8c6f5e8fdd12195ddb78
ms.sourcegitcommit: 4fdbd93aacb52a4fca68e31eb04d0495d4e27a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/27/2022
ms.locfileid: "69672918"
---
# <a name="overview-of-custom-meeting-templates-in-microsoft-teams"></a>Microsoft Teams의 사용자 지정 모임 템플릿 개요

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Microsoft Teams Premium에는 사용자 지정 모임 템플릿을 만드는 기능이 포함되어 있습니다. 모임 서식 파일을 사용하여 모임 이끌이가 일반적으로 제어하는 모임 설정을 제어할 수 있습니다. 템플릿을 사용하면 조직에서 일관된 모임 환경을 만들고 규정 준수 요구 사항 및 비즈니스 규칙을 적용할 수 있습니다.

모임 템플릿을 사용하여 설정을 적용하거나 기본값을 설정할 수 있습니다. 모임 이끌이가 변경할 수 없도록 각 템플릿 설정을 잠글 수도 있고, 필요한 경우 모임 이끌이가 변경할 수 있도록 잠금 해제된 상태로 두면 됩니다.

다음 모임 설정은 모임 템플릿을 사용하여 제어할 수 있습니다.

|설정|설명|
|:------|:----------|
|채팅|모임 채팅을 사용할 수 있는지를 지정합니다. 모임 전후에 채팅을 방지하는 데 사용할 수도 있습니다.|
|엔드 투 엔드 암호화|모임이 암호화되는지를 지정합니다.|
|로비|로비를 우회하고 모임에 직접 참가할 수 있는 사용자를 지정합니다.|
|참석자가 보는 내용 관리|모임 이끌이가 다른 모임 참가자가 볼 수 있기 전에 화면에서 공유되는 콘텐츠를 미리 보고 승인할 수 있는지를 지정합니다.|
|참석자를 위한 마이크 및 카메라|참석자가 음소거를 해제하고 카메라를 사용할 수 있는지를 지정합니다.|
|발신자가 가입하고 나갈 때 알림|전화를 통해 전화를 걸 때 소리가 재생되는지 또는 모임을 나갈지 여부를 지정합니다.|
|Q&A|참석자가 Q&A 기능을 사용하여 모임 중에 질문을 할 수 있는지를 지정합니다.|
|반응|참석자가 반응을 사용하거나 모임에서 손을 들 수 있는지 여부를 지정합니다.|
|녹음/녹화|녹음/녹화할 수 있는 사용자와 모임이 자동으로 기록되는지를 지정합니다.|
|민감도 레이블|모임에 사용할 민감도 레이블을 지정합니다.|
|워터 마크|모임의 화면에서 공유되는 카메라 피드 및 콘텐츠에 워터마크가 사용되는지 지정합니다.|

템플릿이 유용할 수 있는 경우의 몇 가지 예는 다음과 같습니다.

- 특정 유형의 모임에 대해 자동 모임 녹음/녹화를 적용합니다.
- 채팅 및 참석자 카메라 및 오디오를 제한하고 프레젠테이션 스타일 모임에 Q&A 기능을 사용합니다.
- 로비를 우회할 수 있지만 필요한 경우 모임 이끌이가 설정을 변경할 수 있도록 허용하는 사람에 대해 더 엄격한 기본값을 사용합니다.

모임 템플릿을 만드는 방법을 알아보려면 [Microsoft Teams에서 사용자 지정 모임 템플릿 만들기를 참조하세요](create-custom-meeting-template.md).

## <a name="templates-with-sensitivity-labels"></a>민감도 레이블이 있는 템플릿

템플릿에는 민감도 레이블을 지정하는 옵션이 있습니다. 레이블은 템플릿과 관계없이 모임에 직접 적용할 수도 있습니다. 민감도 레이블은 템플릿과 동일한 설정 중 일부를 제어할 수 있습니다.

- 엔드 투 엔드 암호화
- 모임 채팅
- 자동으로 기록
- 로비를 우회할 수 있는 사용자
- 프레젠테이션할 수 있는 사람
- 기록할 수 있는 사람
- 워터 마크

이러한 설정이 레이블에 구성된 경우 템플릿에서 이러한 설정을 재정의합니다.

## <a name="templates-included-with-teams"></a>Teams에 포함된 템플릿

Teams Premium에는 사용자가 사용할 수 있는 몇 가지 기본 모임 템플릿이 포함되어 있습니다.

- 대규모 모임
- 보호된 모임
- 타운 홀
- [가상 약속](virtual-appointment-meeting-template.md)
- 세미나

또한 이러한 템플릿은 교육용 Teams 사용할 수 있습니다.

- 클래스
- 토론 그룹
- 강의
- 학부모 교사 회의

필요한 경우 이러한 템플릿의 설정을 업데이트할 수 있습니다.

## <a name="related-topics"></a>관련 주제

[세 가지 보호 계층으로 Teams 모임 구성](configure-meetings-three-tiers-protection.md)

[Teams 모임 템플릿, 민감도 레이블 및 관리자 정책을 함께 사용](meeting-templates-sensitivity-labels-policies.md)
