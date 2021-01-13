---
title: Intune을 사용하여 Teams 휴대폰 및 Teams 디스플레이 배포
ms.author: v-cichur
author: cichur
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
search.appverid: MET150
localization_priority: Normal
description: 이 문서에서는 Microsoft Teams 디스플레이에서 지원하는 기능에 대한 개요를 제공합니다.
ms.openlocfilehash: 4d955db2f260af0eff3d0c1f059461703cf23d79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825418"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Intune을 사용하여 Teams 휴대폰 및 Teams 디스플레이 배포

이 문서에서는 Intune을 사용하여 Teams 휴대폰 및 Teams 디스플레이를 배포하는 방법에 대한 개요를 제공합니다.

## <a name="conditional-access"></a>조건부 액세스

조건부 액세스는 Office 365 리소스에 액세스하는 디바이스가 제대로 관리되고 안전하도록 하는 데 도움이 되는 Azure AD(Azure Active Directory) 기능입니다.  Teams 서비스에 조건부 액세스 정책을 적용하는 경우 Teams에 액세스하는 Android 장치(Teams 휴대폰 및 Teams 디스플레이 포함)를 Intune에 등록해야 합니다. 해당 설정은 정책을 준수해야 합니다.  장치가 Intune에 등록되지 않은 경우 또는 등록되어 있지만 해당 설정이 정책을 준수하지 않는 경우 조건부 액세스는 사용자가 디바이스에서 Teams 앱에 로그인하거나 사용할 수 없습니다.

일반적으로 Intune 내에 정의된 규정 준수 정책은 사용자 그룹에 할당됩니다.  즉, Android 규정 준수 정책을 user@contoso.com 해당 정책은 Android 스마트폰 및 로그인하는 Android 기반 Teams user@contoso.com 동일하게 적용됩니다.

Intune 등록을 적용해야 하는 조건부 액세스를 사용하는 경우 조직에서 성공적인 Intune 등록을 허용하도록 설정해야 하는 몇 가지가 있습니다.

- **Intune 라이선스** Teams 장치에 로그인하는 사용자는 Intune에 대한 라이선스가 있어야 합니다.  Teams 디바이스가 유효한 Intune 라이선스가 있는 사용자 계정에 로그인하는 한 디바이스는 로그인 프로세스의 일부로 Microsoft Intune에 자동으로 등록됩니다.
- **Intune 구성** Android 디바이스 관리자 등록에 대해 올바르게 구성된 Intune 테넌트가 설정되어 있어야 합니다.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Teams Android 기반 디바이스를 등록하도록 Intune 구성

Teams Android 기반 디바이스는 Android DA(장치 관리자) 관리를 통해 Intune에서 관리됩니다. 디바이스를 Intune에 등록하기 전에 수행할 몇 가지 기본 단계가 있습니다.  현재 Intune을 통해 디바이스를 이미 관리하고 있는 경우 이러한 모든 것을 이미 수행한 것일 수 있습니다.  그렇지 않은 경우 다음 작업을 할 수 있습니다.

1. Intune MDM(모바일 디바이스 관리) 기관을 설정합니다.  Intune을 사용한 적이 없는 경우 디바이스를 등록하기 전에 MDM 기관을 설정해야 합니다. 자세한 내용은 모바일 디바이스 관리 [기관 설정 을 참조하세요.](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)  이 단계는 새 Intune 테넌트 만들기 시 수행해야 하는 일회성 단계입니다.
2. Android 디바이스 관리자 등록을 사용하도록 설정 Android 기반 Teams 디바이스는 Intune을 사용하여 디바이스 관리자 디바이스로 관리됩니다.  새로 만든 테넌트의 경우 디바이스 관리자 등록이 기본적으로 해제되어 있습니다.  자세한 내용은 Android 디바이스 관리자 [등록을 참조하세요.](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)
3. 사용자에게 라이선스를 할당합니다. Intune에 등록하는 Teams 디바이스 사용자에게 유효한 Intune 라이선스가 할당되어야 합니다. 자세한 내용은 Intune에서 디바이스를 등록할 수 있도록 사용자에게 라이선스 [할당을 참조하세요.](https://docs.microsoft.com/intune/fundamentals/licenses-assign)
4. 디바이스 관리자 규정 준수 정책을 할당합니다.  Android 디바이스 관리자 규정 준수 정책을 만들고 Teams 디바이스에 로그인할 사용자를 포함하는 Azure Active Directory 그룹에 할당합니다. 자세한 내용은 규정 준수 정책을 사용하여 [Intune을](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)사용하여 관리하는 디바이스에 대한 규칙을 설정하세요.

## <a name="see-also"></a>참고 항목

[Teams용 전화](phones-for-teams.md)

[Microsoft Teams에 대해 인증된 IP 전화기](teams-ip-phones.md)

[Teams 표시](teams-displays.md)

[Teams에서 디바이스 관리](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
