---
title: Microsoft 팀 보존 정책 FAQ
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: prvijay
audience: admin
description: Microsoft 팀의 보존 정책에 대해 자주 묻는 질문
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b3d2ed05459c6866c73b0f49b128eea3980605f
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968309"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Microsoft 팀 보존 정책 FAQ

> [!NOTE]
> 아직 개인 채널 메시지 보존에 대 한 구성은 지원 하지 않습니다. 개인 채널에서 공유 된 파일을 보존 하는 기능이 지원 됩니다.

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>보존 정책에 설정할 수 있는 정책의 종류는 무엇 이며 어떻게 작동 하나요?

보안 & 준수 센터에서 보존 정책, 팀 또는 기타 작업 부하를 설정할 때 다음과 같은 두 가지 기본 정책 유형을 설정할 수 있습니다. 
- 보존: 이러한 정책은 최종 사용자 도구에서 발생 하는 작업에 관계 없이 지정 된 기간 동안 데이터가 보존 되도록 합니다. 규정 준수 이유를 유지 하 고이 시간이 만료 될 때까지 eDiscovery에서 데이터를 사용할 수 있도록 보장 합니다. 시간이 만료 된 후에는 정책에 아무 작업도 수행 하지 않거나 데이터를 삭제할지 여부를 지정할 수 있습니다. 팀에서 7 년 동안 보존 정책을 만드는 경우 최종 사용자가 팀 메시지를 삭제 하는 경우에도 해당 메시지는 eDiscovery 기간 동안에도 계속 유지 됩니다.
- 삭제: 이러한 정책은 데이터가 조직에 대 한 책임이 되지 않도록 합니다. 지정 된 기간이 지나면 팀의 모든 관련 저장소에서 데이터가 삭제 됩니다. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>조직 차원의 정책에 팀을 포함할 수 있나요? 

아니요, 현재는 그렇지 않습니다. 팀 위치 행 또는 이러한 팀 cmdlet: [new-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [new-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)를 사용 하 여 팀 채팅 및 채널 메시지에 대 한 특정 정책을 만들어야 합니다. 이러한 cmdlet에는 get 및 set 버전도 있습니다.

### <a name="are-these-retention-policies-retroactive"></a>이 보존 정책은 소급? 

예, 그렇습니다. 60 일 보다 오래 된 데이터를 삭제 하는 보존 정책을 만들면 60 일이 지난 팀 데이터가 삭제 됩니다. 

### <a name="what-is-the-default-retention-policy"></a>기본 보존 정책은 무엇입니까? 

기본적으로 팀 채팅, 채널 및 파일 데이터는 영구적으로 유지 됩니다.

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>정책에서 사용자 또는 팀 집합을 대상으로 지정할 수 있습니까? 

그래, 그렇게 할 수 있습니다. 정책 만들기 마법사의 위치 단계에서 팀 (**팀 채널 메시지**) 또는 사용자 (**팀 채팅**)를 포함 하거나 제외 하 고 조직에 대 한 대상 지정 된 정책을 만들 수 있습니다. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>보존 정책의 그룹 사서함 위치 행과 팀 채널 메시지 위치 행을 사용 하는 경우의 주요 차이점은 무엇 인가요? 

Exchange Online의 그룹 사서함 및 사용자 사서함 위치 행을 사용 하는 경우 팀 데이터가 지정 된 사서함에서 삭제 됩니다. 그러나 사서함의 데이터만 제거 됩니다. 채팅 서비스와 같은 다른 팀 데이터는 삭제 되지 않습니다. 팀 보존 정책을 사용 하 여 모든 팀 데이터를 올바르게 관리 하는 것이 좋습니다. 팀 보존 정책은 모든 저장소 위치-사서함, 채팅 서비스, 팀 클라이언트에서 팀 데이터를 제거 합니다. 

참고: 팀에 대 한 보존 정책 기능을 시작 하면 팀 정책만 Exchange 사서함 위치 (사용자 또는 그룹)에 저장 된 팀 항목을 삭제 합니다. 사서함의 다른 정책 설정은 팀 항목에 영향을 줄 수 없습니다. 이는 과거에는 사실 이지만 보존 정책 시작 기능을 사용 하 여 수정 되었습니다. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>비즈니스용 Skype Online 및 팀 interop 채팅은 보존 정책의 영향을 받습니까?

예, 비즈니스용 Skype Online 및 팀 interop 채팅은 동일한 방식으로 작동 합니다. 비즈니스용 Skype Online 채팅이 팀에 들어오면 팀 채팅 스레드에서 메시지가 되 고 적절 한 사서함으로 ingested 됩니다. 따라서 동일한 흐름이 작동 하 고 팀 삭제 정책은 팀 스레드에서 이러한 메시지를 삭제 합니다. 그러나 비즈니스용 Skype Online이 켜져 있고 비즈니스용 Skype Online 클라이언트측에서 대화 내용이 사서함에 저장 되어 있는 경우에는이 채팅 데이터가 팀 보존 정책에 의해 처리 되지 않습니다.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>보안 & 준수 센터 cmdlet을 통해 이러한 작업을 수행할 수 있나요? 무엇을 사용 해야 하나요? 

확신할. [보안 & 준수 센터 Powershell cmdlet]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)을 사용 하 여 팀 보존 정책을 만들 수 있습니다. Exchange Online cmdlet이 아니라는 점에 유의 하세요. 팀에 대해 만든 cmdlet은 다음과 같습니다. 보안 & 준수 센터에서 현재 사용 가능한 보존 cmdlet의 기존 명명법과 스타일을 따릅니다.

|Policy|노트|
|---|---|
|[새로운 TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [새로운 TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[제거-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [제거-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>다른 기간을 사용 하는 팀에 대해 여러 보존 정책이 있는 경우 어떤 항목이 적용 되나요?

[보존 정책의 원칙](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)을 따르고 있으며,이를 수행 하는 것이 좋습니다. 답은 다음과 같습니다. 
-   보존을 통해 항상 우선 적용 됩니다.
-   가장 오래 유지 되는 기간이 항상 우선 적용 됩니다.
-   명시적 포함 wins는 위치 측면에서 암시적으로 포함 됩니다.
-   가장 짧은 삭제 기간 wins
