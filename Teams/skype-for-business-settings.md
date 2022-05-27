---
title: Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams 관리 센터에서 비즈니스용 Skype 기능에 대한 설정을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: f3c79e40d55319af9a45063893bed285140c6d7f
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681339"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

관리자는 Microsoft Teams 관리 센터에서 조직의 비즈니스용 Skype 사용자에 대한 비즈니스용 Skype 기능을 관리합니다. **비즈니스용 Skype** 페이지에서 [조직의](#manage-skype-for-business-settings-for-your-organization) 설정을 관리하고 사용자 세부 정보 페이지의 **비즈니스용 Skype** 탭에서 [개별 사용자에 대한](#manage-skype-for-business-settings-for-individual-users) 설정을 관리할 수 있습니다.

조직의 공존 모드가 **Teams** 설정되지 않은 경우에만 **비즈니스용 Skype** 페이지가 표시됩니다. 마찬가지로 사용자의 공존 모드가 **Teams** 않는 경우에만 사용자에 대한 **비즈니스용 Skype** 탭이 표시됩니다. 공존 모드에 대한 자세한 내용은 [Teams 및 비즈니스용 Skype 공존 및 상호 운용성 이해 및](teams-and-skypeforbusiness-coexistence-and-interoperability.md) [공존 및 업그레이드 설정 설정을 참조하세요](setting-your-coexistence-and-upgrade-settings.md).

> [!NOTE]
> 비즈니스용 Skype 설정은 이전에 Microsoft Teams 관리 센터의 **레거시 포털** 에 있었습니다. 레거시 포털이 사용 중지되면 비즈니스용 Skype 관리를 위해 Teams 관리 센터의 이러한 새 위치로 설정을 마이그레이션했습니다.

[Microsoft Teams 관리 센터에서 비즈니스용 Skype](/azure/active-directory/roles/permissions-reference) 기능을 관리하려면 전역 관리자 또는 비즈니스용 Skype 관리자의 Azure AD 관리자 역할이 할당되어야 합니다.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>조직의 비즈니스용 Skype 설정 관리

Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **조직 전체 설정** > **비즈니스용 Skype** 이동합니다. 여기에서 조직의 모든 비즈니스용 Skype 사용자에 대해 Skype 모임 브로드캐스트, 현재 상태 개인 정보 및 모바일 디바이스 알림을 구성하고 관리할 수 있습니다.

### <a name="skype-meeting-broadcast"></a>Skype 모임 브로드캐스트

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

다음 설정을 사용하여 조직에서 [Skype 모임 브로드캐스트](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d)를 관리합니다.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="관리 센터의 Skype 모임 브로드캐스트 설정 스크린샷":::

- **Skype 모임 브로드캐스트**: 조직에서 Skype 모임 브로드캐스트를 사용하도록 설정하려면 이 기능을 켭니다. 이 기능을 사용하도록 설정한 후에는 [Skype 모임 Broadcast에 대한 네트워크를 설정해야 합니다](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).
- **미리 보기 기능 보기**: 이 기능을 켜면 새 기능에 조기에 액세스할 수 있습니다.
- **이끌이는 익명 모임을 예약할 수 있습니다**. 이끌이가 조직 외부의 모든 사용자가 로그인하지 않고도 참가할 수 있는 브로드캐스트 이벤트를 만들도록 하려면 이 기능을 켭니다. 
- **Skype 모임 브로드캐스트 모임 기록**: 이끌이와 발표자가 모임을 녹음/녹화할 수 있도록 하려면 이 기능을 켭니다.  
- **참석자에 대한 기술 지원 URL**: 모임 참석자가 모임 중에 도움이 필요한 경우 사용할 수 있는 조직의 지원 URL을 입력합니다.

### <a name="presence-and-mobile-notifications"></a>현재 상태 및 모바일 알림

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


다음 설정을 사용하여 조직에서 비즈니스용 Skype 현재 상태 개인 정보 및 모바일 알림을 관리합니다.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="관리 센터의 현재 상태 설정 스크린샷":::

#### <a name="presence"></a>현재 상태

기본적으로 조직의 비즈니스용 Skype 사용자는 다른 비즈니스용 Skype 사용자의 현재 상태(예: 사용 가능, 사용 중 또는 어웨이)를 볼 수 있습니다. 다음 중 하나를 선택하여 비즈니스용 Skype 사용자의 현재 상태를 볼 수 있는 사용자를 설정합니다.

- **자동으로 현재 상태 정보 표시**: 조직의 **외부 또는** **차단된** 목록에 추가되지 않은 모든 비즈니스용 Skype 사용자가 해당 사용자의 현재 상태를 볼 수 있습니다.
- **사용자의 연락처에만 현재 상태 정보 표시**: **외부 또는** **차단 목록에** 추가되지 않은 사용자의 연락처 목록에 있는 모든 비즈니스용 Skype 사용자는 해당 사용자의 현재 상태를 볼 수 있습니다. 사용자는 비즈니스용 Skype 설정 도구 옵션 **으로 이동하여** 이 설정을 재정 **의** > 할  >  수 **있습니다**.

#### <a name="mobile-notifications"></a>모바일 알림

비즈니스용 Skype 모바일 사용자가 푸시 알림 서비스를 통해 수신 및 누락된 인스턴트 메시지, 음성 메일 메시지 및 부재 중 통화에 대한 경고를 받을지 여부를 설정할 수 있습니다. 조직에서 사용되는 모바일 디바이스에 따라 **Microsoft 푸시 알림 서비스**, **Apple 푸시 알림 서비스** 또는 둘 다를 사용할 수 있습니다.

다음 사항에 유의하세요.

- 푸시 알림을 해제하면 다음에 모바일 디바이스에서 비즈니스용 Skype 시작할 때 모든 경고가 표시됩니다.
- 기본적으로 푸시 알림은 켜져 있습니다. 개별 사용자는 모바일 디바이스에서 비즈니스용 Skype 해제할 수 있습니다.
- 푸시 알림을 끄면 사용자가 다시 켤 수 없습니다. 

> [!IMPORTANT]
> Microsoft는 다른 회사를 사용하여 Windows Phone, iPhone 및 iPad 사용자에게 실시간 비즈니스용 Skype 모바일 알림을 제공합니다. [이 개인정보처리방침](https://go.microsoft.com/fwlink/p/?linkid=247732)을 참조하세요.

## <a name="manage-skype-for-business-settings-for-individual-users"></a>개별 사용자에 대한 비즈니스용 Skype 설정 관리

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

개별 사용자에 대한 비즈니스용 Skype 설정을 관리하려면 Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동하여 사용자의 표시 이름을 클릭하여 사용자 세부 정보 페이지를 연 다음 **비즈니스용 Skype 설정** 탭을 선택합니다. 여기에서 사용자에 대한 외부 액세스 및 모임 설정을 구성할 수 있습니다.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="사용자 세부 정보 페이지의 비즈니스용 Skype 탭 스크린샷":::

### <a name="external-access-settings"></a>외부 액세스 설정

사용자가 조직 외부의 사용자와 통신할 수 있는지 여부를 선택적으로 허용하거나 차단할 수 있습니다.

- **외부 비즈니스용 Skype 사용자**: 사용자가 페더레이션된 도메인의 비즈니스용 Skype 사용자와 통신할 수 있도록 하려면 이 기능을 켭니다.
- **외부 Skype 사용자: 사용자가** Skype 사용자와 통신할 수 있도록 허용하려면 이 기능을 켭니다. 

### <a name="meeting-settings"></a>모임 설정

사용자에 대해 다음 모임 설정을 구성할 수 있습니다.

- **오디오 & 비디오**: 다음 오디오 및 비디오 설정 중 하나를 선택합니다.

    - **없음**: 사용자는 오디오 또는 비디오를 사용할 수 없습니다.
    - **오디오만**: 사용자는 오디오를 사용할 수 있지만 비디오는 사용할 수 없습니다.
    - **오디오 및 비디오**: 사용자가 오디오 및 비디오를 사용할 수 있습니다.
    - **오디오 및 비디오(HD)**: 사용자는 오디오 및 고화질 비디오를 사용할 수 있습니다.
    
- **& 대화 기록**: 사용자가 대화 및 모임을 녹음/녹화할 수 있도록 하려면 이 기능을 켭니다.
- **규정 준수**: 전자적으로 저장된 정보를 보존해야 하는 경우 이를 켭니다.