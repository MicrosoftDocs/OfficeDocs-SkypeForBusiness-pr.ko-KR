---
title: 법적 Microsoft Teams 사용자 또는 팀을 법적 보류에 두기
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 사용자 또는 Microsoft Teams 사용자 또는 팀을 법적 보류에 Microsoft 365 규정 준수 센터 데이터 요구 사항에 따라 법적 보류가 필요한지 알아보는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06b3ea009e538b8796a9e55b277dc4ec12f5a3a4
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711562"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>법적 Microsoft Teams 사용자 또는 팀을 법적 보류에 두기

소송에 대한 합리적인 기대가 있는 경우 조직은 사례와 관련된 채팅 메시지를 포함하여 ESI(전자적으로 저장된 Teams 유지해야 합니다. 조직은 특정 조사 또는 특정 사용자에 대한 모든 메시지를 보존해야 할 수 있습니다. 이 문서에서는 법적 보존을 사용하여 콘텐츠 보존에 대해 Microsoft Teams. 다른 서비스에서 콘텐츠를 Microsoft 365 [eDiscovery 보류 만들기를 참조하세요](/microsoft-365/compliance/create-ediscovery-holds).

> [!NOTE]
> 2020년 2월에는 개인 채널에 대한 법적 보류를 설정했습니다. 개인 채널 채팅은 사용자 사서함에 저장되고 표준 채널 채팅은 부모 팀과 연결된 사서함에 저장됩니다. 사용자 사서함에 대한 법적 보류가 이미 있는 경우 보류 정책은 이제 해당 사서함에 저장된 개인 채널 메시지에 자동으로 적용됩니다. 관리자가 이 기능을 켜는 데 필요한 추가 작업이 없습니다. 개인 채널에서 공유되는 파일의 법적 보류도 지원됩니다.

이 Microsoft Teams 전체 팀 또는 선택 사용자를 법적 보류에 넣을 수 있습니다. 이렇게 하면 해당 팀에서 교환된 모든 메시지(개인 및 공유 채널 포함) 또는 해당 개인이 교환한 메시지는 조직의 규정 준수 관리자 또는 관리자에게 검색할 수 Teams 합니다.

> [!NOTE]
> 사용자를 보류 중이면 그룹이 자동으로 보류되거나 그 반대의 경우도 마찬가지입니다.
> 활동 피드로 전송된 알림은 보류 중일 수 없습니다.

Core eDiscovery 사례에서 사용자 또는 팀을 법적으로 보류하는 경우:

1. 다음으로 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com). 새 사례를 만들 때 사서함 또는 사이트를 보류할 수 있는 옵션이 표시됩니다.

2. **eDiscoveryCore** > 로 **이동** 하여 사례 만들기를 클릭하여 사례 **를 만들 수 있습니다**. 대소문자 생성 후 열립니다.
  
   ![Microsoft Teams eDiscovery 탭이 선택되어 사례 만들기 단추가 표시됩니다.](media/LegalHold1.png)

   > [!NOTE]
   > 또한 사용자 대소문자와 연결된 보류에 사용자를 Advanced eDiscovery 있습니다. 자세한 내용은 에서 보류 [Advanced eDiscovery](/microsoft-365/compliance/managing-holds).

3. 위쪽 **메뉴의 보** 류 탭으로 이동하고 만들기를 클릭하여  보류를 만드세요. 사용자 또는 팀을 보류 중으로 배치하면 해당 사용자가 교환한 모든 메시지가 유지됩니다. 새 사례를 만들 때 사서함 또는 사이트를 보류할 수 있는 옵션이 표시됩니다.

   ![선택된 보류 탭과 아래 만들기 단추를 보여주는 이미지입니다.](media/LegalHold2.png)

   1. **보류 이름을 지정합니다**. 만들 보류에 대한 설명이 있는 고유한 이름을 선택합니다.
  
       ![이 스크린샷은 보류 탭의 이름과 만드는 보류에 대한 설명과 이름에 입력할 수 있는 이름을 보여줍니다.](media/LegalHold3.png)

   2. **위치를 선택하세요**. 사용자 또는 전체 팀에 보류를 적용할지 여부를 선택하세요(현재는 개별 채널에 보류를 적용할 수 없습니다). 사용자가 보류 중이면 1:1 채팅, 그룹 채팅 및 개인 채널의 메시지를 포함하여 모든 메시지가 유지됩니다. 표준 및 공유 채널의 메시지는 부모 팀이 보류 중일 때 유지됩니다.

      ![보류할 데이터 위치를 선택하세요.](media/LegalHold4.png)

   3. **쿼리를 만들 수 있습니다**. 보류 정책에서 더 세분화하려는 경우 보류를 사용자 지정할 수 있습니다. 예를 들어 검색할 키워드를 지정하거나 보류가 적용될 때 만족해야 하는 조건을 더 추가할 수 있습니다.

   4. **보류를 만들기** 전에 설정을 검토합니다.

보류를 만든 후 보존 정책에 의해 보존된 콘텐츠를 검색할 수 있습니다. 자세한 내용은 전자 메일에서 [eDiscovery 조사 수행을 Teams](eDiscovery-investigation.md).

> [!IMPORTANT]
> 사용자 또는 그룹이 보류 중이면 메시지의 모든 준수 복사본이 유지됩니다. 예를 들어 사용자가 채널에 메시지를 게시한 다음 메시지를 수정하면 두 메시지 복사본이 모두 유지됩니다. 보류가 없는 경우 최신 메시지만 유지됩니다.

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>콘텐츠를 보존하기 위해 보류할 콘텐츠 Teams 위치

유용한 가이드로 다음 표를 사용하여 다양한 유형의 콘텐츠를 보존하기 위해 보류할 콘텐츠 위치(예: 사서함 또는 사이트)를 Teams 있습니다.

|시나리오  |콘텐츠 위치  |
|---------|---------|
|사용자에 대한 채팅 메시지(예: 1:1 채팅, 1:N 그룹 채팅 및 개인 채널 대화)     |사용자 사서함         |
|표준 및 공유 채널에서 채팅 메시지    |부모 팀과 연결된 사서함         |
|표준 채널의 파일(예: Wiki 콘텐츠 및 파일)     |SharePoint 팀과 연결된 사이트        |
|개인 및 공유 채널의 파일     |채널과 SharePoint 전용 사이트
|사용자의 개인 콘텐츠     |사용자의 비즈니스용 OneDrive 계정       |
|채팅의 카드 콘텐츠|1:1 채팅, 1:N 그룹 채팅 및 개인 채널 대화에 대한 사용자 사서함; 표준 및 공유 채널 메시지의 카드 콘텐츠에 대한 부모 팀 사서함입니다. 자세한 내용은 [eDiscovery](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content) 보류 만들기의 "카드 콘텐츠 보존" 섹션을 참조하세요.|
|||

> [!NOTE]
> 개인 채널에서 메시지 콘텐츠를 유지하려면 사용자 사서함(개인 채널의 구성원)을 보류해야 합니다. 및 eDiscovery 도구를 사용하여 개인 채널 메시지를 검색할 때 사용자의 사서함을 검색해야 합니다. 앞에서 말한 대로 개인 채널 채팅은 부모 팀과 연결된 그룹 사서함이 아닌 사용자 사서함에 저장됩니다.
