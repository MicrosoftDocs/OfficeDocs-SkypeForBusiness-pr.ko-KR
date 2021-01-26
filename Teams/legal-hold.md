---
title: Microsoft Teams 사용자 또는 팀에 법적 보류
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
description: Security & 준수 센터를 사용하여 Microsoft Teams 사용자 또는 팀을 법적 보류에 추가하고 데이터 요구 사항에 따라 법적 보류가 필요한 사항을 알아보는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c04f3584aa7207d9d9ee1126df992657f84aa213
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980452"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Microsoft Teams 사용자 또는 팀에 법적 보류
==================================================

소송에 대한 합리적 기대가 있을 경우 조직은 사례와 관련된 Teams 채팅 메시지를 포함하여 ESI(전자적으로 저장된 정보)를 보존해야 합니다. 조직은 특정 토픽 또는 특정 개인과 관련된 모든 메시지를 유지해야 할 수 있습니다. 이 문서에서는 Microsoft Teams의 법적 보류에 대해 설명합니다(M365 공간에서 구현을 보류하기 위해 [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)사례 관리 검토: 콘텐츠 위치 보류.).

> [!NOTE]
> 2020년 2월에 비공개 채널에서 법적 보류 또는 사례 보류를 사용하도록 설정했습니다(개인 채널 채팅은 사용자 사서함에 저장되고 일반 채널 채팅은 팀의 그룹 사서함에 저장). 사용자 사서함에 대한 법적 보류가 이미 있는 경우 이제 해당 사서함에 저장된 개인 채널 메시지에 보류 정책이 자동으로 적용됩니다. 관리자가 이 기능을 설정하는 데 필요한 추가 작업은 없습니다. 비공개 채널에서 공유되는 파일의 법적 보유도 지원됩니다.

Microsoft Teams 내에서 전체 팀 또는 선택 사용자가 보류 또는 법적 보류를 할 수 있습니다. 이렇게 하면 해당 팀에서 교환된 모든 메시지(비공개 채널 포함) 또는 해당 개인이 교환한 메시지를 조직의 규정 준수 관리자 또는 Teams 관리자가 검색할 수 있습니다.

> [!NOTE]
> 사용자를 보류로 설정하면 그룹이 자동으로 보류되거나 그 반대의 경우도 마찬가지입니다.

사용자 또는 팀을 법적 보류에 넣는 경우:

1. Security & [준수 센터로 이동합니다.](https://go.microsoft.com/fwlink/?linkid=854628) 새 사례를 만들면 사서함 또는 사이트를 보류할 수 있는 옵션이 표시됩니다.

2. eDiscovery 또는 Advanced eDiscovery로 이동하고 "사례 만들기"를 클릭하여 사례를 작성합니다. 사례가 만들어지면 열립니다.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Teams eDiscovery 탭이 선택되어 사례 만들기 단추가 표시됩니다.](media/LegalHold1.png)

3. 위쪽 메뉴에서 "보류" 섹션으로 이동하고 "+ 만들기"를 클릭하여 보류를 만드세요. 사용자 또는 팀을 보류하면 해당 사용자 또는 메시지에서 교환된 모든 메시지가 저장됩니다. 새 사례를 만들면 사서함 또는 사이트를 보류할 수 있는 옵션이 표시됩니다.

   > [!div class="mx-imgBorder"]
   > ![보류 탭이 선택된 이미지와 그 아래에 만들기 단추가 있습니다.](media/LegalHold2.png)

   1. **보류 이름을 지정합니다.** 만들 보류에 대한 설명이 있는 고유한 이름을 선택합니다.

      > [!div class="mx-imgBorder"]
      > ![이 스크린샷은 보류 탭의 이름과 만드는 보류에 대한 설명을 입력할 수 있는 이름을 보여줍니다.](media/LegalHold3.png)

    2. **위치를 선택하세요.** 사용자 또는 전체 팀에서 보류를 적용할지(현재는 개별 채널에 적용될 수 없습니다)를 선택하세요. 참고: 사용자가 보류 중이면 1:1 채팅, 1:다 또는 그룹 채팅 또는 채널 대화(비공개 채널 포함)에서 보낸 모든 메시지를 포함하여 모든 메시지가 보류됩니다.
  
       > [!div class="mx-imgBorder"]
       > ![여기서는 보류를 적용하고자 하는 Microsoft Teams를 비롯한 M365 옵션에 대해 결정을 내릴 수 있는 새 보류 만들기의 위치 선택 섹션이 있습니다.](media/LegalHold4.png)

    3. **쿼리 만들기.** 보류 정책에서 더 세분화하려는 경우 보류를 사용자 지정할 수 있습니다. 예를 들어 검색할 키워드를 지정하거나 보류를 적용하기 위해 충족해야 하는 조건을 더 추가할 수 있습니다.
    
    4. **조직에 게시하기** 전에 설정을 검토합니다.

법적 보존이 설정되고 나면 [Teams eDiscovery](eDiscovery-investigation.md) 문서 다음에 보존 정책에 의해 보존되는 모든 콘텐츠를 검색할 수 있습니다.

> [!IMPORTANT]
> 사용자 또는 그룹이 보류된 경우 모든 메시지 복사본이 유지됩니다. 예를 들어 사용자가 채널에 메시지를 게시한 다음 메시지를 수정한 경우 보류 시나리오에서는 두 메시지 복사본이 모두 보존됩니다. 법적 보존이 없는 경우 최신 메시지만 보존됩니다.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Teams 콘텐츠를 보존하기 위해 법적 보존을 할 콘텐츠 위치

유용한 가이드로 다음 표를 사용하여 다양한 유형의 Teams 콘텐츠를 보존하기 위해 법적 보존을 할 콘텐츠 위치(예: 사서함 또는 사이트)를 이해할 수 있습니다.

|시나리오  |콘텐츠 위치  |
|---------|---------|
|사용자를 위한 Teams 채팅(예: 1:1 채팅, 1:N 그룹 채팅 및 비공개 채널 대화)     |사용자 사서함.         |
|Teams 채널 채팅(비공개 채널 제외)    |팀에 사용되는 그룹 사서함입니다.         |
|Teams 파일 콘텐츠(예: Wiki 콘텐츠 및 파일)     |팀에서 사용하는 SharePoint 사이트입니다.         |
|Teams 개인 채널 파일     |비공개 채널을 위한 전용 SharePoint 사이트.     |
|사용자의 개인 콘텐츠     |사용자의 비즈니스용 OneDrive 계정입니다.         |
|채팅의 카드 콘텐츠|1:1 채팅, 1:N 그룹 채팅, 채널 메시지의 카드 콘텐츠에 대한 개인 채널 대화 또는 그룹 사서함에 대한 사용자 사서함입니다. 자세한 내용은 eDiscovery 보류 만들기의 "카드 콘텐츠 [유지" 섹션을 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)
||||

> [!NOTE]
> 개인 채널에서 통신을 유지하려면 사용자 사서함(개인 채널 사용자)을 보류하고 eDiscovery 도구를 사용하여 검색할 때 해당 사용자의 사서함에서 검색해야 합니다. 앞에서 말한 대로 비공개 채널 채팅은 팀의 그룹 사서함이 아닌 사용자 사서함에 저장됩니다.

Microsoft 365의 Teams가 아닌 영역에 대한 이 항목에 대해 자세히 읽으면 [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)사례 관리: 콘텐츠 위치 보류를 검토해야 합니다.
