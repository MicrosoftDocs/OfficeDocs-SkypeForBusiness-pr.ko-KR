---
title: Microsoft 팀에 대 한 통신 준수
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Microsoft 팀 관점에서의 참가자 위험 솔루션 집합의 일부인 통신 준수에 대해 자세히 알아보세요 (이는 M365 통신 준수 기능의 일부).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf97f4adc33b0855e986cf2baed54f69de91f4f0
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077700"
---
# <a name="communication-compliance-for-microsoft-teams"></a>Microsoft 팀에 대 한 통신 준수

통신 준수는 조직의 부적절 한 메시지에 대 한 검색, 캡처, 재구성 작업을 수행 하 여 통신 위험을 최소화 하는 데 도움이 되는 Microsoft 365에서 설정 된 새로운 참가자 위험 솔루션의 일부입니다. 이를 통해 공격적인 언어를 식별 하 고 팀 채널이 나 1:1 및 그룹 채팅에서 harassment 수 있습니다. 또한 정책을 설정 하 여 중요 한 정보가 팀 채널 또는 1:1 및 그룹 채팅의 일부로 공유 되 고 있는지 확인할 수 있습니다. 다양 한 유형의 정책 및 설정 방법에 대 한 자세한 내용은 [M365 문서](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)를 참조 하세요.

## <a name="how-to-use-communication-compliance-in-teams"></a>팀에서 통신 준수를 사용 하는 방법

### <a name="identify-inappropriate-messages"></a>부적절 한 메시지 식별

Microsoft 팀 (1:1, 그룹 채팅 또는 채널 대화)에서 전송 된 메시지를 식별 하려는 경우 정책을 사용 하 여이를 식별 하 고, 검토자가 메시지를 보고, 교육 자료 보내기 또는 올바른 인증 기관으로 harassment 하는 것과 같은 필요한 단계를 수행할 수 있습니다.

### <a name="identify-sensitive-or-regulatory-information"></a>중요 또는 규정 정보 확인

Microsoft 팀에서 보낸 메시지 (1:1, 그룹 채팅 또는 채널 대화)를 중요 한 정보나 규정 유형에 대해 검색 하려는 경우 미리 정의 된 중요 또는 규정 유형을 지 원하는 정책을 선택할 수 있습니다.

> [!NOTE]
> 통신 준수는 개인 채널을 지원 하지 않습니다.

### <a name="custom-policy"></a>사용자 지정 정책

이 템플릿을 사용 하 여 조직의 특정 통신 채널, 개별 검색 조건, 모니터링 하 고 검토할 콘텐트의 양을 구성할 수 있습니다.

### <a name="custom-trainable-classifier"></a>사용자 지정 Trainable 분류자

상자 분류자 중 하나가 사용자의 요구를 충족 하지 않는 경우 trainable 분류자를 사용 합니다. Microsoft 365 분류자는 다양 한 형식의 콘텐츠를 볼 수 있도록 교육을 제공 하는 도구입니다. 분류자에 대 한 교육에서는 먼저 사람이 선택 하 고 범주와 긍정적인 일치 하는 샘플을 제공 합니다. 그런 다음 샘플을 처리 한 후에는 양수 및 음수 샘플을 함께 제공 하 여 예측을 테스트 합니다. 이에 대 한 자세한 내용은이 항목에 대 한 자세한 [M365 문서](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) 를 참조 하세요.

> [!NOTE]
> 통신 준수는 이제 Exchange 하이브리드 배포를 지원 합니다.

통신 준수는 정책과 일치 하는 메시지에 대 한 대화 기록을 지원 합니다. 조사 관리자에 게 컨텍스트를 제공 합니다.

:::image type="content" source="media/communication-compliance-1.png" alt-text="Microsoft 팀의 의사 소통 준수 화면":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a>팀에서 통신 정책을 적용할 수 있는 위치

통신 준수 정책은 팀에서 보낸 메시지에 대해 다음 수준으로 설정할 수 있습니다.

- 사용자 수준: 관리자는 개별 사용자 수준에서 정책을 설정 하거나 테 넌 트의 모든 사용자에 게 적용할 수 있습니다. 이는 사용자가 1:1 또는 그룹 채팅에서 보낸 메시지만 다룹니다.
- 팀 수준: 관리자가 팀에 정책을 설정할 수도 있습니다. 이는 해당 팀의 채널에서 전송 된 모든 메시지 (개인 채널 메시지가 지원 되지 않음)를 포함 합니다.
