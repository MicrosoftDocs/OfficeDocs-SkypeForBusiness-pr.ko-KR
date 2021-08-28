---
title: 특정 사용자에 대한 무료 전화 Teams 사용 안 하도록 지정
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 주최자가 오디오 회의 브리지 모임에 무료 번호를 사용할 수 있는 방법을 제어하는 방법에 대해 알아보습니다.
ms.openlocfilehash: 3d9cd647f8089bd95defe016176dbc236e9f628b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613647"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>특정 사용자에 대한 무료 전화 Teams 사용 안 하도록 지정

조직에서 Microsoft Audio Conferencing Bridge에 무료 번호가 있는 경우 특정 이끌이의 모임에서 해당 번호를 허용하거나 방지할 수 있습니다.  

기본적으로 조직의 모든 사용자는 무료 번호를 사용할 수 있습니다. 즉, 해당 숫자를 사용할 수 있는 경우 참가자가 모임에 참가할 수 있습니다. 조직의 일부 사용자에게 원하는 동작이 아닌 경우 무료 번호 사용 제어를 통해 특정 사용자가 모임에서 해당 번호를 사용하지 못하도록 제한할 수 있습니다. 

주어진 이끌이에 대해 무료 번호가 비활성화된 경우: 
 - 무료 전화 번호는 더 이상 모임 초대에 포함되지 않습니다. 
 - 무료 전화 번호는 모임 초대에 참조되는 "로컬 번호 찾기" 페이지에 더 이상 나열되지 않습니다. 
 - 참가자는 조직의 무료 전화 번호로 전화를 걸면 해당 이끌이의 모임에 참가할 수 없습니다. 
 - 이끌이의 모든 모임이 자동으로 다시 조정되고 무료 전화 번호가 제거됩니다.  

    > [!IMPORTANT]
    > 이렇게 하면 이끌이의 모든 전자 메일 초대가 해당 모임의 모든 참가자에게 다시 전송됩니다. 

 - 참가자는 전화 번호를 사용하여 이끌이의 모임에 계속 참가할 수 있습니다. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>특정 사용자의 무료 전화 번호 사용 안 함 

관리 **Microsoft Teams 센터에서**:

1. 왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 오디오 **회의** 옆에 있는 편집을 **클릭합니다.**

3. 이 사용자의 모임 요청에 무료 전화 번호 포함 을 **Off로** **설정합니다.** 

4. 저장을 **클릭합니다.** 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**PowerShell 사용**  

자세한 [내용은 Microsoft Teams PowerShell 참조를](/powershell/module/teams/?view=teams-ps) 참조하세요.