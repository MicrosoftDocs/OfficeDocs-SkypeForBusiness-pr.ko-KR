---
title: Microsoft 팀 관리 센터에서 비즈니스용 Skype 설정 관리
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀 관리 센터의 비즈니스용 Skype 기능에 대 한 설정을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0a74b2586fa706dc8fe9db73c58b7d938eae59ee
ms.sourcegitcommit: 54e685b07d1c23100951d46913480989f046d534
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "48827762"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터에서 비즈니스용 Skype 설정 관리

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Microsoft 팀 관리 센터에서 관리자는 조직의 비즈니스용 skype 사용자에 대 한 비즈니스용 Skype 기능을 관리할 수 있습니다. 비즈니스용 **skype** 페이지에서 [조직의](#manage-skype-for-business-settings-for-your-organization) 설정을 관리 하 고 사용자 세부 정보 페이지의 **비즈니스용 skype** 탭에서 [개별 사용자에](#manage-skype-for-business-settings-for-individual-users) 대 한 설정을 관리할 수 있습니다.

조직의 공존 모드가 **팀 으로만** 설정 되어 있지 않은 경우 **비즈니스용 Skype** 페이지만 볼 수 있습니다. 마찬가지로 사용자의 공존 모드가 **팀 전용** 인 경우 사용자에 대 한 **비즈니스용 Skype** 탭만 표시 됩니다. 공존 모드에 대 한 자세한 내용은 [비즈니스용 Skype 공존 및 상호 운용성에 대 한 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 를 참조 하 고 [공존 및 업그레이드 설정을 설정](setting-your-coexistence-and-upgrade-settings.md)하는 방법에 대해 알아보세요.

> [!NOTE]
> 이전에는 Microsoft 팀 관리 센터의 **레거시 포털** 에 비즈니스용 Skype 설정이 있습니다. 레거시 포털을 사용 하지 않는 경우에는 비즈니스용 Skype 관리 센터의 팀 관리 센터에서 이러한 새로운 위치로 설정을 마이그레이션 했습니다.

Microsoft 팀 관리 센터에서 비즈니스용 Skype 기능을 관리 하려면 전역 관리자 또는 비즈니스용 Skype 관리자의 [AZURE AD 관리자 역할이](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) 할당 되어야 합니다.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>조직의 비즈니스용 Skype 설정을 관리 합니다.

Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **조직 전체**  >  **비즈니스용 Skype** 설정으로 이동 합니다. 여기서는 조직의 모든 비즈니스용 Skype 사용자에 대 한 Skype 모임 브로드캐스트, 현재 상태 프라이버시 및 모바일 장치 알림을 구성 하 고 관리할 수 있습니다.

### <a name="skype-meeting-broadcast"></a>Skype 모임 브로드캐스트

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

다음 설정을 사용 하 여 조직에서 [Skype 모임 브로드캐스트](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) 를 관리할 수 있습니다.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="관리 센터의 Skype 모임 브로드캐스트 설정 스크린샷":::

- **Skype 모임 브로드캐스트** : 조직에 대해 Skype 모임 브로드캐스트를 사용 하도록 설정 합니다. 이 기능을 사용 하도록 설정한 후에 [는 Skype 모임 브로드캐스트에 대 한 네트워크를 설정](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)해야 합니다.
- **미리 보기 기능** : 새로운 기능에 빠르게 액세스 하려면이 옵션을 설정 하세요.
- **이끌이는 익명 모임을 예약할 수** 있습니다. 이끌이가 로그인 할 필요 없이 조직 외부의 모든 사용자에 게 참가할 수 있도록 하는 브로드캐스트 이벤트를 만들도록 하려면이 옵션을 설정 합니다. 
- **Skype 모임 브로드캐스트 모임 기록** : 이끌이 및 발표자가 모임을 녹음/녹화할 수 있도록 설정 합니다.  
- **참석자를 위한 헬프 데스크 지원 url** : 모임 참석자가 모임을 진행 하는 동안 도움이 필요한 경우 조직에서 사용할 수 있는 조직의 지원 url을 입력 합니다.

### <a name="presence-and-mobile-notifications"></a>현재 상태 및 모바일 알림

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


조직의 비즈니스용 Skype 현재 상태 개인 정보 및 모바일 알림을 관리 하려면 다음 설정을 사용 합니다.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="관리 센터의 현재 상태 설정 스크린샷":::

#### <a name="presence"></a>현재 상태

기본적으로 조직의 비즈니스용 Skype 사용자는 다른 비즈니스용 Skype 사용자의 현재 상태를 볼 수 있습니다 (예: 사용 중, 약속 있음 또는 자리 비움). 다음 중 하나를 선택 하 여 비즈니스용 Skype 사용자의 현재 상태를 볼 수 있는 사용자를 설정 합니다.

- **현재 상태 정보 표시** : 사용자의 **외부** 또는 **차단** 목록에 추가 되지 않은 조직의 모든 비즈니스용 Skype 사용자는 해당 사용자의 현재 상태를 볼 수 있습니다.
- **사용자의 대화 상대 에게만 현재 상태 정보 표시** : 사용자의 대화 **상대 목록에** 추가 되지 않은 모든 비즈니스용 Skype 사용자의 현재 상태 **External** 를 볼 수 있습니다. 사용자는 **설정**  >  **도구**  >  **옵션** 으로 이동해 서 비즈니스용 Skype에서이 설정을 무시할 수 있습니다.

#### <a name="mobile-notifications"></a>모바일 알림

비즈니스용 Skype mobile 사용자가 푸시 알림 서비스를 통해 들어오고 부재 중 메신저 대화, 보이스 메일 메시지, 부재 중 통화에 대 한 알림을 받을 지 여부를 설정할 수 있습니다. 조직에서 사용 하는 모바일 장치에 따라 **Microsoft 푸시 알림 서비스** , **Apple 푸시 알림 서비스** 또는 둘 다를 사용할 수 있습니다.

다음 사항에 유의 하세요.

- 푸시 알림을 끄면 사용자가 다음에 모바일 장치에서 비즈니스용 Skype를 시작할 때 모든 알림을 받게 됩니다.
- 기본적으로 푸시 알림은 켜져 있습니다. 개별 사용자는 모바일 장치에서 비즈니스용 Skype를 통해 기능을 해제할 수 있습니다.
- 푸시 알림을 해제 하면 사용자가 다시 설정할 수 없습니다. 

> [!IMPORTANT]
> Microsoft는 다른 회사를 사용 하 여 Windows Phone, iPhone 및 iPad 사용자에 게 비즈니스용 Skype 모바일 알림을 제공 합니다. 본 [개인 정보 취급 방침](https://go.microsoft.com/fwlink/p/?linkid=247732)을 참조 하세요.

## <a name="manage-skype-for-business-settings-for-individual-users"></a>개별 사용자에 대 한 비즈니스용 Skype 설정 관리

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

개별 사용자의 비즈니스용 Skype 설정을 관리 하려면 팀 관리 센터의 왼쪽 탐색 **에서 사용자의** 표시 이름을 클릭 하 여 사용자 세부 정보 페이지를 연 다음 비즈니스용 **Skype 설정** 탭을 선택 합니다. 여기에서 사용자에 대 한 외부 액세스 및 모임 설정을 구성할 수 있습니다.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="사용자 세부 정보 페이지의 비즈니스용 Skype 탭 스크린샷":::

### <a name="external-access-settings"></a>외부 액세스 설정

사용자가 조직 외부 사용자와 통신할 수 있는지 여부를 선택적으로 허용 하거나 차단할 수 있습니다.

- **외부 비즈니스용 skype 사용자** : 페더레이션 도메인에서 사용자가 비즈니스용 skype 사용자와 통신할 수 있도록 하려면이 옵션을 켭니다.
- **외부 skype 사용자** : 사용자가 Skype 사용자와 통신할 수 있도록 허용 하려면이 옵션을 켭니다. 

### <a name="meeting-settings"></a>모임 설정

사용자에 대해 다음 모임 설정을 구성할 수 있습니다.

- **오디오 & 비디오** : 다음 오디오 및 비디오 설정 중 하나를 선택 합니다.

    - **없음** : 사용자가 오디오 또는 비디오를 사용할 수 없습니다.
    - **오디오만** : 사용자가 오디오는 사용할 수 있지만 비디오는 아닙니다.
    - **오디오 및 비디오** : 사용자는 오디오 및 비디오를 사용할 수 있습니다.
    - **오디오 및 비디오 (HD)** : 사용자는 오디오 및 고화질 비디오를 사용할 수 있습니다.
    
- **모임 & 기록** : 사용자가 대화 및 모임을 녹화할 수 있도록이 기능을 켭니다.
- **준수** : 전자적으로 저장 된 정보를 유지 해야 하는 경우이 기능을 켭니다. 
