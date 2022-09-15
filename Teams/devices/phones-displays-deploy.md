---
title: Intune 사용하여 Android에서 Teams 휴대폰, Teams 디스플레이, Teams 패널 및 Microsoft Teams 룸 배포
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: 이 문서에서는 Microsoft Teams Android 디바이스에서 지원하는 기능에 대한 개요와 기능을 제공합니다.
ms.openlocfilehash: 388848019806740074401400d0fad6847751489e
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705997"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Intune 사용하여 Android에서 Teams 휴대폰, Teams 디스플레이, Teams 패널 및 Microsoft Teams 룸 배포

이 문서에서는 Intune 사용하여 Android에서 Teams 휴대폰, Teams 디스플레이, Teams 패널 및 Microsoft Teams 룸 배포하는 방법에 대한 개요를 제공합니다.

## <a name="conditional-access"></a>조건부 액세스

조건부 액세스는 Office 365 리소스에 액세스하는 디바이스가 제대로 관리되고 안전한지 확인하는 데 도움이 되는 Azure Azure AD(Active Directory) 기능입니다. Teams 서비스에 조건부 액세스 정책을 적용하는 경우 Teams에 액세스하는 Android 디바이스(Teams 휴대폰, Teams 디스플레이, Teams 패널 및 android의 Microsoft Teams 룸 포함)는 Intune 등록해야 하며 해당 설정은 정책을 준수해야 합니다.  디바이스가 Intune 등록되지 않았거나 등록되었지만 해당 설정이 정책을 준수하지 않는 경우 조건부 액세스는 사용자가 디바이스에서 Teams 앱에 로그인하거나 사용하지 못하게 합니다.

일반적으로 Intune 내에 정의된 규정 준수 정책은 사용자 그룹에 할당됩니다.  즉, user@contoso.com Android 규정 준수 정책을 할당하는 경우 해당 정책은 Android 스마트폰 및 로그인할 user@contoso.com 있는 Android 기반 Teams 디바이스에 동일하게 적용됩니다.

Intune 등록을 적용해야 하는 조건부 액세스를 사용하는 경우 조직에서 성공적인 Intune 등록을 허용하도록 설정해야 하는 몇 가지 사항이 있습니다.

- **Intune 라이선스** Teams 디바이스에 로그인하는 사용자에게 Intune 대한 라이선스가 있어야 합니다.  Teams 디바이스가 유효한 Intune 라이선스가 있는 사용자 계정에 로그인하는 한 디바이스는 로그인 프로세스의 일부로 Microsoft Intune 자동으로 등록됩니다.
- **구성 Intune** Android 디바이스 관리자 등록을 위해 올바르게 구성된 Intune 테넌트가 설정되어 있어야 합니다.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Teams Android 기반 디바이스를 등록하도록 Intune 구성

Teams Android 기반 디바이스는 ANDROID DA(디바이스 관리자) 관리를 통해 Intune 관리됩니다. 디바이스를 Intune 등록하려면 몇 가지 기본 단계를 수행해야 합니다.  현재 Intune 사용하여 디바이스를 이미 관리하고 있는 경우 이러한 모든 작업을 이미 수행했을 것입니다.  그렇지 않은 경우 수행할 일은 다음과 같습니다.

> [!NOTE]
> - 테넌트 관리자가 공용 영역 전화기를 Intune 등록하려는 경우 계정에 Intune 라이선스를 추가하고 Intune 등록 단계를 따라야 합니다.
> - Teams 디바이스에 로그인하는 데 사용되는 사용자 계정이 Intune 대한 라이선스가 없는 경우 계정에 Intune 준수 정책 및 등록 제한을 사용하지 않도록 설정해야 합니다.
> - Teams 디바이스에 로그인하는 데 사용되는 사용자 계정이 Intune 라이선스가 부여되면 Teams 디바이스가 Intune 자동으로 등록됩니다.



1. INTUNE MDM(모바일 디바이스 관리) 기관을 설정합니다.  

   이전에 Intune 사용한 적이 없는 경우 디바이스를 등록하기 전에 MDM 기관을 설정해야 합니다. 자세한 내용은 [모바일 디바이스 관리 기관 설정을 참조하세요](/intune/fundamentals/mdm-authority-set).  새 Intune 테넌트 만들기 시 수행해야 하는 일회성 단계입니다.
1. Android 디바이스 관리자 등록을 사용하도록 설정합니다.
  
   Android 기반 Teams 디바이스는 Intune 사용하여 디바이스 관리자 디바이스로 관리됩니다.  새로 만든 테넌트에 대한 디바이스 관리자 등록은 기본적으로 해제되어 있습니다. [Android 디바이스 관리자 등록을 참조하세요](/intune/enrollment/android-enroll-device-administrator).
1. 사용자에게 라이선스를 할당합니다. 
 
   Intune 등록하는 Teams 디바이스 사용자에게 유효한 Intune 라이선스가 할당되어야 합니다. 자세한 내용은 [Intune 디바이스를 등록할 수 있도록 사용자에게 라이선스 할당](/intune/fundamentals/licenses-assign)을 참조하세요.
1. 디바이스 관리자 준수 정책을 할당합니다.  

   1. Android 디바이스 관리자 준수 정책을 만듭니다.

   1. Teams 디바이스에 로그인할 사용자가 포함된 Azure Active Directory 그룹에 할당합니다. [Intune 사용하여 관리하는 디바이스에 대한 규칙을 설정하려면 준수 정책 사용을](/mem/intune/protect/device-compliance-get-started) 참조하세요.

## <a name="see-also"></a>참고 항목

[Teams용 전화](phones-for-teams.md)

[Microsoft Teams용으로 인증된 IP 전화](teams-ip-phones.md)

[Teams 디스플레이](teams-displays.md)

[Teams에서 디바이스 관리](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
