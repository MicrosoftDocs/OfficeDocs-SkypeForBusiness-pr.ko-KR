---
title: Microsoft Teams 사용자 또는 팀을 법적 보류 상태로 유지
description: Microsoft Purview 규정 준수 포털 사용하여 Microsoft Teams 사용자 또는 팀을 법적 보존에 배치하고 데이터 요구 사항에 따라 법적 보존이 필요한 사항을 알아보는 방법을 알아봅니다.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- tier1
- purview-compliance
- M365-collaboration
- ediscovery
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78dcc82c6a02cc702527f2653da131bdb52c8775
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047068"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Microsoft Teams 사용자 또는 팀을 법적 보류 상태로 유지

소송에 대한 합리적인 기대가 있는 경우 조직은 사례와 관련된 Teams 채팅 메시지를 포함하여 ESI(전자 저장 정보)를 보존해야 합니다. 조직은 특정 조사 또는 특정 사용자와 관련된 모든 메시지를 보존해야 할 수 있습니다. 이 문서에서는 법적 보존을 사용하여 Microsoft Teams의 콘텐츠를 보존하는 방법을 설명합니다. Microsoft 365의 다른 서비스에서 콘텐츠를 보존하려면 [eDiscovery 보류 만들기를](/microsoft-365/compliance/create-ediscovery-holds) 참조하세요.

> [!NOTE]
> 2020년 2월에는 비공개 채널에 대한 법적 보류를 설정했습니다. 개인 채널 채팅은 사용자 사서함에 저장되고 표준 채널 채팅은 부모 팀과 연결된 사서함에 저장됩니다. 사용자 사서함에 대한 법적 보존이 이미 있는 경우 해당 사서함에 저장된 개인 채널 메시지에 보존 정책이 자동으로 적용됩니다. 관리자가 이 기능을 켜는 데 필요한 추가 작업은 없습니다. 비공개 채널에서 공유되는 파일의 법적 보존도 지원됩니다.

Microsoft Teams 내에서 전체 팀 또는 선택한 사용자를 법적 보류 상태로 유지할 수 있습니다. 이렇게 하면 해당 팀에서 교환된 모든 메시지(비공개 및 공유 채널 포함) 또는 해당 개인이 교환한 메시지를 조직의 규정 준수 관리자 또는 Teams 관리자가 검색할 수 있습니다.

> [!NOTE]
> 사용자를 보류 상태로 두면 그룹이 자동으로 보류되거나 그 반대의 경우도 마찬가지입니다.
> 활동 피드에서 전송된 알림은 보류할 수 없습니다.

eDiscovery(표준) 사례에서 사용자 또는 팀을 법적 보존에 배치하려면 다음을 수행합니다.

1. [Microsoft Purview 규정 준수 포털](https://compliance.microsoft.com) 이동합니다. 새 사례를 만들 때 사서함 또는 사이트를 보류할 수 있는 옵션이 표시됩니다.

2. **eDiscovery** > **Core** 로 이동하여 사례 만들기를 클릭하여 **사례를 만듭니다**. 사례를 만든 후 엽니다.
  
   ![사례 만들기 단추를 보여 주는 Microsoft Teams eDiscovery 탭이 선택되었습니다.](media/LegalHold1.png)

   > [!NOTE]
   > eDiscovery(프리미엄) 사례와 연결된 보류에 사용자를 배치할 수도 있습니다. 자세한 내용은 [eDiscovery의 보류 관리(프리미엄)](/microsoft-365/compliance/managing-holds)를 참조하세요.

3. 위쪽 메뉴의 **보류** 탭으로 이동하고 **만들기** 를 클릭하여 보류를 만듭니다. 사용자 또는 팀을 보류하면 해당 사용자가 교환한 모든 메시지가 유지됩니다. 새 사례를 만들 때 사서함 또는 사이트를 보류할 수 있는 옵션이 표시됩니다.

   ![보류 탭이 선택되고 그 아래에 만들기 단추가 표시된 이미지입니다.](media/LegalHold2.png)

   1. **보류 이름을 지정합니다**. 만들 보류의 설명적이고 고유한 이름을 선택합니다.
  
       ![이 스크린샷은 사용자가 만드는 보류에 대한 이름 및 설명을 입력할 수 있는 보류 이름 탭을 보여줍니다.](media/LegalHold3.png)

   2. **위치를 선택합니다**. 보류를 사용자 또는 팀 전체에 적용할지 여부를 선택합니다(지금은 개별 채널에 보류를 적용할 수 없습니다). 사용자가 대기 중인 경우 1:1 채팅, 그룹 채팅 및 개인 채널의 메시지를 포함하여 모든 메시지가 유지됩니다. 표준 및 공유 채널의 메시지는 부모 팀이 보류될 때 유지됩니다.

      ![보류할 데이터 위치를 선택합니다.](media/LegalHold4.png)

   3. **쿼리를 만듭니다**. 보류 정책에서 더 세분성을 원하는 경우 보류를 사용자 지정할 수 있습니다. 예를 들어 찾을 키워드를 지정하거나 보류가 적용되려면 충족해야 하는 조건을 더 추가할 수 있습니다.

   4. 보류를 만들기 전에 **설정을 검토합니다**.

보류가 만들어지면 보류 정책에 의해 보존된 콘텐츠를 검색할 수 있습니다. 자세한 내용은 [Teams에서 eDiscovery 조사 수행을 참조하세요](eDiscovery-investigation.md).

> [!IMPORTANT]
> 사용자 또는 그룹이 보류되면 메시지의 모든 준수 복사본이 유지됩니다. 예를 들어 사용자가 채널에 메시지를 게시한 다음 메시지를 수정하는 경우 메시지의 두 복사본이 모두 유지됩니다. 보류가 없으면 최신 메시지만 유지됩니다.

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>Teams 콘텐츠를 보존하기 위해 보류할 콘텐츠 위치

유용한 가이드로 다음 표를 사용하여 다양한 유형의 Teams 콘텐츠를 보존하기 위해 보류할 콘텐츠 위치(예: 사서함 또는 사이트)를 이해합니다.

|시나리오  |콘텐츠 위치  |
|---------|---------|
|사용자에 대한 채팅 메시지(예: 1:1 채팅, 1:N 그룹 채팅 및 개인 채널 대화)     |사용자 사서함         |
|표준 및 공유 채널의 채팅 메시지    |부모 팀과 연결된 사서함         |
|표준 채널의 파일(예: Wiki 콘텐츠 및 파일)     |부모 팀과 연결된 SharePoint 사이트        |
|프라이빗 및 공유 채널의 파일     |채널과 연결된 전용 SharePoint 사이트
|사용자의 개인 콘텐츠     |사용자의 비즈니스용 OneDrive 계정       |
|채팅의 카드 콘텐츠|1:1 채팅, 1:N 그룹 채팅 및 개인 채널 대화에 대한 사용자 사서함 표준 및 공유 채널 메시지의 카드 콘텐츠에 대한 부모 팀 사서함입니다. 자세한 내용은 [eDiscovery 보류 만들기](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)의 "카드 콘텐츠 보존" 섹션을 참조하세요.|
|||

> [!NOTE]
> 개인 채널에서 메시지 콘텐츠를 유지하려면 사용자 사서함(개인 채널의 구성원)을 보류해야 합니다. eDiscovery 도구를 사용하여 프라이빗 채널 메시지를 검색하는 경우 사용자의 사서함을 검색해야 합니다. 앞에서 설명한 것처럼 개인 채널 채팅은 부모 팀과 연결된 그룹 사서함이 아닌 사용자 사서함에 저장됩니다.
