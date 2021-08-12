---
title: 초대에 포함할 전화 번호 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
- seo-marvel-mar2020
description: 다음 단계에 따라 발신자들이 모임에 참가할 수 있는 기본 전화 번호를 Microsoft Teams 있습니다.
ms.openlocfilehash: 11c9a31d723b5da63152f1a8a79d54938f9ecc31644afbe3421a2bd59f0f5626
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335898"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>초대에 포함된 전화 번호를 Microsoft Teams

조직에서 Microsoft 365 Office 365 오디오 회의를 사용하면 조직의 사용자가 Microsoft Teams 모임을 만든 다음 사용자가 전화를 사용하여 해당 모임에 전화를 걸 수 있습니다.
  
회의 브리지는 조직에 대한 전화 접속 전화 번호 집합을 제공합니다. 모두 모임 이끌이가 만든 모임에 참가하는 데 사용할 수 있지만 모임 초대에 포함될 모임을 선택할 수 있습니다.
  
> [!NOTE]
> 모임 이끌이에 대한 모임 초대에는 최대 1개의 전화 번호와 무료 전화 번호가 있을 수 있지만, 각 모임 초대의 아래쪽에 모임에 참가하는 데 사용할 수 있는 모든 전화 접속 전화 번호의 전체 목록을 여는 링크도 있습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>새 사용자를 위한 모임 초대에 포함된 전화 번호의 초기 할당

오디오 회의에 사용하도록 설정된 사용자의 모임 초대에 포함된 전화 번호는 기본 회의 요금 전화 번호 및 기본 회의 무료 전화 번호 사용자 설정에 의해 정의됩니다. 각 설정은 지정한 사용자의 모임 초대에 포함될 요금 및 무료 번호를 지정합니다. 위에서 설명한 대로 각 모임 초대에는 하나의 전화 번호, 하나의 선택적 무료 전화 번호 및 특정 모임에 참가하는 데 사용할 수 있는 모든 전화 접속 전화 번호의 전체 목록을 여는 링크가 포함되어 있습니다.

새 사용자의 경우 사용자가 오디오 회의 서비스에 대해 사용하도록 설정되어 있는 경우 사용자의 Microsoft 365 관리 센터에 설정된 사용 현황 위치를 기반으로 기본 회의 전화 번호가 할당됩니다. 사용자의 국가와 일치하는 전화 회의 브리지에 전화 번호가 있는 경우 해당 번호는 사용자의 기본 전화 번호로 자동으로 할당됩니다. 전화 회의 브리지의 기본 전화 번호로 정의된 번호는 사용자의 기본 전화 번호로 할당됩니다.  

사용자가 오디오 회의 서비스에 사용하도록 설정되면 사용자의 기본 전화 번호 및 무료 전화 번호를 테넌트 관리자가 초기 값에서 변경할 수 있습니다.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>모임 이끌이 또는 사용자의 기본 오디오 회의 전화 번호 설정 또는 변경

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다. 관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](./using-admin-roles.md)을 참조하세요.

1. 관리 센터에 Microsoft Teams 로그인합니다.

2. 왼쪽 탐색에서 사용자 를 **클릭합니다.**

    ![관리 센터에서 사용자 Microsoft Teams 표시](media/Admin-users.png)

3. 사용 가능한 사용자 목록에서 사용자 이름을 클릭합니다.

4. 오디오 **회의** 옆에 있는 편집을 **클릭합니다.**

    ![오디오 회의 옆의 편집을 클릭합니다.](media/teams-set-phone-numbers-on-invites-image3.png)

5. 전화 번호 **또는**  무료 번호 필드를 사용하여 사용자에 대한 번호를 입력합니다.

> [!IMPORTANT]
> 사용자의 오디오 회의 설정을 변경하면 모임을 다시 Microsoft Teams 모임을 업데이트하고 참석자에게 보내야 합니다.

## <a name="want-to-use-windows-powershell"></a>Windows PowerShell

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.

- [PowerShell을 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.
  
## <a name="related-topics"></a>관련 항목

[오디오 회의를 시도하거나 Microsoft 365 또는 Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[오디오 회의 브리지에서 전화 번호 변경](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)