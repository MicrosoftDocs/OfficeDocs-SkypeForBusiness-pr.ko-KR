---
title: 정보 장벽 및 공유 채널(미리 보기)
description: 이 문서에서는 공유 채널의 정보 장벽이 Microsoft Teams 방법을 설명합니다.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: information-barriers
ms.openlocfilehash: c65da8b9b04296a7377f29aead811e1efcfb4048
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712144"
---
# <a name="information-barriers-and-shared-channels-preview"></a>정보 장벽 및 공유 채널(미리 보기)

[공동 작업의](shared-channels.md) Microsoft Teams 팀에 없는 사용자들을 초대할 수 있는 공동 작업 공간을 만들 수 있습니다. [정보 장벽](/microsoft-365/compliance/information-barriers) 은 사용자와 그룹이 조직 안팎에서 서로 통신하지 못하도록 제한하고 방지하도록 구현할 수 있는 정책입니다.

공유 채널은 기본적으로 Teams. 사용자가 공유 채널을 만들 수 있는지, 조직 외부 사용자와 공유할 수 있는지, 채널 정책을 만들어 외부 공유 채널에 참여할 수 있는지 선택할 수 있습니다. 조직에서 정보 장벽 정책이 구성되면 공유 채널을 구성할 때 기존 채널 구성원과 공유 채널에 추가된 새 사용자가 정보 장벽 정책 조건을 위반하지 않는지 확인하는 검사가 수행됩니다.

다음 표를 사용하여 정보 장벽 정책이 통신에 영향을 미치고 공유 채널을 구성할 때 특정 동작이 어떻게 영향을 미칠 수 있는지 이해합니다.

|**시나리오**|**정보 장벽 동작**|
|:-----------|:--------------------------------|
| **조직의 사용자와 채널 공유** | 사용자가 정보 장벽 정책에 따라 공유 채널 구성원과 통신할 수 없는 경우 사용자는 사용자 검색에 표시되지 않습니다. 채널은 팀과 공유되지 않습니다. <br><br> 정보 장벽 정책에 따라 사용자를 추가할 수 없는 경우 다음과 같은 메시지가 *표시됩니다. 일치를 찾지 못했습니다. 검색 범위를* 확장하는 방법을 IT 관리자에게 문의하세요. |
| **소유한 다른 팀과 조직의 채널 공유** | 다른 팀에 정보 장벽 정책당 공유 채널 구성원과 통신할 수 없는 사용자가 있는 경우 채널은 팀과 공유되지 않습니다. <br><br> 정보 장벽 정책에 따라 통신이 허용되지 않는 경우 채널을 이 팀과 공유할 *수 없습니다. 자세한 내용은 다른 팀을 선택하거나 관리자에게 문의하세요.* |
| **소유하지 않은 다른 팀과 조직의 채널 공유** | 팀 소유자 또는 다른 팀의 사용자가 정보 장벽 정책에 따라 공유 채널 구성원과 통신할 수 없는 경우 채널을 팀과 공유할 수 없습니다. <br><br> 정보 장벽 정책에 따라 통신이 허용되지 않는 경우 채널을 이 팀과 공유할 *수 없습니다. 자세한 내용은 다른 팀을 선택하거나 관리자에게 문의하세요.* |
| **팀이 다른 팀과 채널을 공유한 경우 팀에 새 사용자 추가** | 새 사용자가 정보 장벽 정책에 따라 공유 채널 팀 구성원과 통신할 수 없는 경우 사용자를 팀에 추가할 수 없습니다. 6개 이상의 공유 채널이 있는 팀에 사용자를 추가하는 경우 사용자가 채널에 즉시 추가하고 공유가 지원됩니다. 새 사용자가 정보 장벽 정책을 준수하지 않는 것으로 발견된 경우 팀 및 이전에 공유한 채널에 대한 공유가 중지될 수 있습니다.<br><br> 정보 장벽 정책에 따라 사용자를 추가할 수 없는 경우 정보 장벽 정책으로 인해 사용자를 추가할 수 *없습니다.* |
| **외부 팀과 채널 공유** | 내부 및 외부 테넌트에 대한 정보 장벽 정책은 다른 테넌트의 사용자 간의 통신을 제한하지 않습니다. 공유 채널은 외부 사용자와 공유할 수 있습니다. |