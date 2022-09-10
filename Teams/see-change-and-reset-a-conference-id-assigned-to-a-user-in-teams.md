---
title: 사용자의 전화 회의 ID 보기, 변경 및 재설정
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Microsoft Teams의 사용자에게 전화 회의 ID를 할당하는 방법과 회의 ID 매개 변수에 대해 알아봅니다.
ms.openlocfilehash: 9ff068a8485f77531ba034ebeaab3e27e1ed42ef
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642119"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Microsoft Teams에서 사용자에게 할당된 회의 ID 보기 및 다시 설정

회의 ID는 Microsoft 365 또는 Office 365 오디오 회의를 위해 설정되고 Microsoft를 오디오 회의 공급자로 사용할 때 Microsoft Teams 사용자에게 자동으로 할당됩니다. 모임이 예약되면 할당된 회의 ID가 모임 초대로 전송됩니다. 사용자가 예약하는 각 모임에는 고유한 회의 ID가 할당됩니다.
  
회의 ID가 자동으로 만들어지고 사용자에게 할당되지만 사용자가 이 ID를 사용하지 않고 특정 번호로 설정하려는 경우 또는 사용자가 전화 회의 ID를 기억하지 못하거나 분실한 경우가 있을 수 있습니다. Microsoft Teams 관리 센터 또는 Windows PowerShell 사용하여 전화 회의 ID를 보고, 변경하고, 다시 설정할 수 있습니다.
  
전화 회의 ID와 기본 오디오 회의 전화 번호가 있는 사용자에게 전자 메일이 전송되거나, 전화 회의 ID를 다시 설정하면 전화 회의 ID가 포함되지만 PIN이 아닌 다른 전자 메일이 전송됩니다. 회의 이끌이의 PIN을 다시 설정하는 방법에 대한 자세한 내용은 Microsoft Teams 사용자에 대한 전화 회의 [ID 재설정](reset-a-conference-id-for-a-user-in-teams.md) 을 참조하세요.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>회의 ID 보기 및 다시 설정

### <a name="to-view-the-conference-id"></a>회의 ID를 보려면

#### <a name="view-the-conference-id-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터를 사용하여 회의 ID 보기

1. 왼쪽 탐색 영역에서 **사용자를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 페이지 위쪽에서 **편집** 을 클릭합니다.

3. **오디오 회의** 아래에서 **회의 ID** 를 확인합니다.

    > [!TIP]
    > 전자 메일 링크에서 회의 정보 보내기를 클릭하여 회의 ID 및 오디오 전화 번호가 포함된 **전자 메일에서** 사용자에게 모든 회의 정보를 보낼 수 있습니다.
  
#### <a name="view-the-conference-id-using-windows-powershell"></a>Windows PowerShell 사용하여 회의 ID 보기

자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps) 를 참조하세요.

### <a name="to-reset-the-conference-id"></a>전화 회의 ID를 다시 설정하려면

예를 들어 사용자가 잊어버린 경우 사용자의 전화 회의 ID를 다시 설정할 수 있습니다.
  
#### <a name="reset-the-conference-id-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터를 사용하여 회의 ID 다시 설정

1. 왼쪽 탐색 영역에서 **사용자를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 페이지 위쪽에서 **편집** 을 클릭합니다.

3. **오디오 회의** 아래에서 **전화 회의 ID 재설정** 을 클릭합니다.

4. **전화 회의 ID 다시 설정** 창에서 **다시 설정을** 클릭합니다. 전화 회의 ID가 자동으로 생성되고 새 전화 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다.
  
#### <a name="reset-the-conference-id-using-windows-powershell"></a>Windows PowerShell 사용하여 회의 ID 다시 설정

자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps) 를 참조하세요.

## <a name="what-else-should-you-know"></a>그 밖에 무엇을 알아야 할까요?

> [!IMPORTANT]
> 새 회의 ID를 만들거나 다시 설정한 후에는 호출자가 이전 회의 ID를 사용할 수 없습니다. 새 회의 ID가 초대에 추가되도록 기존 모임 초대의 일정을 조정하도록 사용자에게 알려야 합니다.

- 회의 ID는 오디오 회의 브리지에 설정된 숫자 길이를 충족해야 합니다. 전화 회의 ID에는 사전순 또는 특수 문자를 사용할 수 없습니다. 숫자만 사용할 수 있습니다.

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell 대해 자세히 알고 싶으신가요?

Windows PowerShell 사용자를 관리하는 것과 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. Windows PowerShell 사용하면 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 관리할 수 있습니다. Windows PowerShell 시작하려면 다음 항목을 참조하세요.

- [Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell 사용하여 Microsoft 365 또는 Office 365 관리하는 가장 좋은 방법](/previous-versions//dn568025(v=technet.10))

Windows PowerShell 대한 자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps)를 참조하세요.

## <a name="related-topics"></a>관련 주제

[Microsoft Teams용 Microsoft 365에서 오디오 회의 체험 또는 구매](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
