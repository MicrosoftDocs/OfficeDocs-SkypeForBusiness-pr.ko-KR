---
title: 관리 비즈니스용 Skype 관리 센터에서 Microsoft Teams 관리
author: cichur
ms.author: v-mahoffman
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
description: 관리 센터에서 비즈니스용 Skype 기능에 대한 설정을 관리하는 Microsoft Teams 대해 자세히 알아보습니다.
ms.openlocfilehash: 90748d968b2540ea6ee7e5c542623ceb0bc0fbb1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767136"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>관리 비즈니스용 Skype 관리 센터에서 Microsoft Teams 관리

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

관리자인 Microsoft Teams 관리 센터는 조직의 비즈니스용 Skype 사용자에 대한 비즈니스용 Skype 관리하는 위치입니다. 사용자 세부 [](#manage-skype-for-business-settings-for-your-organization) 정보 페이지의 비즈니스용 Skype  탭에서 개별 사용자에 대한 비즈니스용 Skype  관리할 수 있습니다. [](#manage-skype-for-business-settings-for-individual-users)

조직의 공존 모드가 비즈니스용 Skype 으로만 설정되어 있지 않은 경우 Teams **표시됩니다.**  마찬가지로 사용자의 공존 **모드가** 에만 비즈니스용 Skype 없는 경우 사용자에 대한 Teams **탭이 표시됩니다.** 공존 모드에 대한 자세한 내용은 [](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 공존 및 Teams 비즈니스용 Skype 이해 및 공존 및 업그레이드 설정 을 [참조하세요.](setting-your-coexistence-and-upgrade-settings.md)

> [!NOTE]
> 비즈니스용 Skype 관리 센터의 **레거시** 포털에 Microsoft Teams 설정이 있습니다. 레거시 포털이 사용 중지되어 관리 관리 센터의 Teams 새 위치로 비즈니스용 Skype.

전역 관리자 또는 비즈니스용 Skype 관리자의 [Azure AD](/azure/active-directory/roles/permissions-reference) 관리자 역할이 비즈니스용 Skype 관리 센터에서 Microsoft Teams 지정해야 합니다.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>조직의 비즈니스용 Skype 설정 관리

관리 센터의 왼쪽 탐색에서 Microsoft Teams 에서 **org-wide**  >  **설정으로 비즈니스용 Skype.** 여기에서 조직의 모든 사용자에 대해 브로드캐스트, Skype 모임 상태 개인 정보 및 모바일 디바이스 알림을 구성하고 관리할 비즈니스용 Skype 수 있습니다.

### <a name="skype-meeting-broadcast"></a>Skype 모임 브로드캐스트

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

다음 설정을 사용하여 조직의 Skype 모임 [브로드캐스트를](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) 관리합니다.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="관리 Skype 모임 브로드캐스트 설정의 스크린샷.":::

- **Skype 모임 브로드캐스트:** 조직에 대해 브로드캐스트를 사용하도록 설정하려면 Skype 모임 켜기. 이 기능을 사용하도록 설정한 후 브로드캐스트 에 대한 네트워크를 [Skype 모임 합니다.](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)
- **미리 보기 기능:** 이 기능을 켜면 새 기능에 대한 초기 액세스를 얻을 수 있습니다.
- **이끌이는** 익명 모임을 예약할 수 있습니다. 조직 외부의 모든 사용자가 로그인하지 않고 참가할 수 있는 브로드캐스트 이벤트를 만들 수 있도록 하려는 경우 이 기능을 켜야 합니다. 
- **브로드캐스트 Skype 모임** 녹화 : 주최자 및 발표자가 모임을 녹화할 수 있도록 설정합니다.  
- **참석자에** 대한 Helpdesk 지원 URL: 모임 참석자에 도움이 필요한 경우 사용할 수 있는 조직의 지원 URL을 입력합니다.

### <a name="presence-and-mobile-notifications"></a>현재 상태 및 모바일 알림

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


다음 설정을 사용하여 조직의 비즈니스용 Skype 현재 상태 개인 정보 및 모바일 알림을 관리합니다.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="관리 센터의 현재 상태 설정 스크린샷.":::

#### <a name="presence"></a>현재 상태

기본적으로 조직의 비즈니스용 Skype 다른 사용자의 현재 상태(예: 사용 가능, 사용 중 또는 비우기)를 볼 비즈니스용 Skype 있습니다. 다음 중 하나를 선택하면 사용자의 현재 사용자를 볼 수 있는 사용자를 비즈니스용 Skype 있습니다.

- **현재 상태** 정보 자동으로 표시 : 비즈니스용 Skype 외부 목록에 추가하지 않은 조직의  모든  사용자 또는 차단된 사용자는 해당 사용자의 현재 상태는 볼 수 있습니다.
- **사용자의** 연락처에만 현재 상태 정보 표시 : 사용자의 비즈니스용 Skype 목록에 추가되지 않은 모든 사용자 또는 차단된  사용자 목록에서 해당 사용자의 현재 상태는 볼 수 있습니다.  사용자는 도구 옵션 으로 비즈니스용 Skype 이 설정을 설정  >    >  **수 있습니다.**

#### <a name="mobile-notifications"></a>모바일 알림

모바일 사용자가 푸시 알림 비즈니스용 Skype 통해 수신 및 누락된 인스턴트 메시지, 음성 메일 메시지 및 부재 중 호출에 대한 경고를 받을지 여부를 설정할 수 있습니다. 조직에서 사용되는 모바일 디바이스에 따라 **Microsoft 푸시** 알림 서비스, Apple **푸시** 알림 서비스 또는 둘 다를 사용할 수 있습니다.

다음을 염두에 두어야 합니다.

- 푸시 알림을 해제하면 사용자가 다음에 모바일 디바이스에서 알림을 시작할 때 모든 비즈니스용 Skype 표시됩니다.
- 기본적으로 푸시 알림이 켜져 있습니다. 개별 사용자는 모바일 장치에서 비즈니스용 Skype 해제할 수 있습니다.
- 푸시 알림을 해제하면 사용자가 푸시 알림을 다시 켜지 못합니다. 

> [!IMPORTANT]
> Microsoft는 다른 회사를 사용하여 사용자 비즈니스용 Skype 사용자에 대한 실시간 Windows Phone iPhone iPad 있습니다. 이 개인 [정보 취급 방침 을 참조합니다.](https://go.microsoft.com/fwlink/p/?linkid=247732)

## <a name="manage-skype-for-business-settings-for-individual-users"></a>개별 비즈니스용 Skype 설정 관리

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

개별 비즈니스용 Skype 설정을 관리하려면 Teams 관리 센터의 왼쪽 탐색에서 사용자로 이동하여 사용자 표시 이름을 클릭하여 사용자 **세부 정보 페이지를 열고** 비즈니스용 Skype 설정 탭을 선택합니다.  여기에서 사용자에 대한 외부 액세스 및 모임 설정을 구성할 수 있습니다.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="사용자 비즈니스용 Skype 탭의 스크린샷입니다.":::

### <a name="external-access-settings"></a>외부 액세스 설정

사용자가 조직 외부의 사용자와 통신할 수 있는지 여부를 선택적으로 허용하거나 차단할 수 있습니다.

- **외부 비즈니스용 Skype** 사용자: 페더리드된 도메인의 사용자와 통신할 수 있도록 허용하려면 비즈니스용 Skype 설정합니다.
- **외부 Skype** 사용자 : 사용자가 사용자와 통신할 수 있도록 허용하려는 경우 이 Skype 설정합니다. 

### <a name="meeting-settings"></a>모임 설정

사용자에 대한 다음 모임 설정을 구성할 수 있습니다.

- **오디오 & 비디오:** 다음 오디오 및 비디오 설정 중 하나를 선택합니다.

    - **없음:** 사용자는 오디오 또는 비디오를 사용할 수 없습니다.
    - **오디오만**: 사용자는 오디오를 사용할 수 있지만 비디오는 사용할 수 없습니다.
    - **오디오 및 비디오:** 사용자는 오디오 및 비디오를 사용할 수 있습니다.
    - **오디오 및 비디오(HD)**: 사용자는 오디오 및 고화질 비디오를 사용할 수 있습니다.
    
- **모임에 &** 대화 기록 : 사용자가 대화 및 모임을 기록할 수 있도록 이 기능을 켜야 합니다.
- **준수**: 전자적으로 저장된 정보를 법적으로 보존해야 하는 경우 이 기능을 켜야 합니다.