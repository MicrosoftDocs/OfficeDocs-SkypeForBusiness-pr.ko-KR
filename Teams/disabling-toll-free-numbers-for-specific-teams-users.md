---
title: 특정 팀 사용자를 위해 무료 번호를 사용 하지 않도록 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 관리자는 이끌이가 무료 전화 번호를 모임에 사용 하는 방법을 제어할 수 있습니다.
ms.openlocfilehash: 7bc830529fc24a61be914998e923ad2d5288b7c5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837268"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>특정 팀 사용자를 위해 무료 번호를 사용 하지 않도록 설정

조직의 Microsoft 오디오 회의 브리지에 무료 번호가 있는 경우 특정 이끌이의 모임에서 사용을 허용 하거나 방지할 수 있습니다.  

기본적으로 조직의 모든 사용자는 무료 번호를 사용할 수 있으며, 해당 번호 (사용 가능한 경우)를 참가자가 모임에 참가 하는 데 사용 하는 것을 의미 합니다. 조직의 일부 사용자가이 동작을 원하지 않는 경우에는 무료 번호 사용 제어를 통해 특정 사용자가 모임에서 해당 번호를 사용 하지 못하도록 제한할 수 있습니다. 

특정 이끌이의 무료 전화 번호를 사용 하지 않는 경우 다음을 수행 합니다. 
 - 무료 번호는 귀하의 모임 초대에 더 이상 포함 되지 않습니다. 
 - 무료 번호는 귀하의 모임 초대에서 참조 되는 "지역 번호 찾기" 페이지에 더 이상 나열 되지 않습니다. 
 - 무료 조직의 번호로 전화를 걸어야 하는 경우 참가자가 지정 된 이끌이의 모임에 참가할 수 없습니다. 
 - 이끌이의 모든 모임이 자동으로 재조정 되 고 무료 번호가 해당 번호에서 제거 됩니다.  

    > [!IMPORTANT]
    > 이렇게 하면 해당 모임의 모든 참가자에 게 이끌이의 전자 메일 초대가 모두 다시 전송 됩니다. 

 - 참가자는 유료 전화 번호를 사용 하 여 이끌이 모임에 계속 참가할 수 있습니다. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>특정 사용자의 무료 전화 번호 사용 안 함 

**Microsoft 팀 관리 센터**에서 다음을 수행 합니다.

1. 왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

2. **오디오 회의**옆에 있는 **편집**을 클릭 합니다.

3. **이 사용자의 모임 요청에 무료 전화 번호 포함** 을 **Off**로 설정 합니다. 

4. **저장을 클릭 합니다.** 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**PowerShell 사용**  

자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.
