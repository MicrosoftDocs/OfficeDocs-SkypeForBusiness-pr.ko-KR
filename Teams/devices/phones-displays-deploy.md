---
title: 'Intune을 사용하여 Teams 휴대폰, Teams 디스플레이, Teams 패널 및 Microsoft Teams 룸 배포'
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
description: 이 문서에서는 Android 디바이스에서 지원하는 기능과 Microsoft Teams 제공합니다.
---

# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Intune을 사용하여 Teams 휴대폰, Teams 디스플레이, Teams 패널 및 Microsoft Teams 룸 배포

이 문서에서는 Intune을 사용하여 휴대폰, Teams 디스플레이, Teams 패널 및 Teams 배포하는 Microsoft Teams 룸 개요를 제공합니다.

## <a name="conditional-access"></a>조건부 액세스

조건부 액세스는 azure AD(Azure Active Directory) 기능으로, 리소스에 액세스하는 디바이스가 Office 365 안전하게 관리되도록 하는 데 도움이 됩니다.  Teams 서비스에 조건부 액세스 정책을 적용하는 경우 Teams 휴대폰, Teams 디스플레이, Teams 패널 및 Microsoft Teams 룸 Android 디바이스)에 Teams Intune에 등록해야 하며 해당 설정은 정책을 준수해야 합니다.  디바이스가 Intune에 등록되지 않은 경우 또는 등록되어 있지만 해당 설정이 정책을 준수하지 않는 경우 조건부 액세스는 사용자가 디바이스에서 앱에 로그인하거나 Teams 방지합니다.

일반적으로 Intune 내에 정의된 규정 준수 정책은 사용자 그룹에 할당됩니다.  즉, Android 규정 준수 정책을 할당하는 user@contoso.com 해당 정책은 로그인하는 Android 스마트폰 및 Android 기반 Teams 디바이스에 user@contoso.com 적용됩니다.

Intune 등록을 적용해야 하는 조건부 액세스를 사용하는 경우 조직에서 성공적인 Intune 등록을 허용하기 위해 설정해야 할 몇 가지가 있습니다.

- **Intune 라이선스** 디바이스에 로그인하는 Teams Intune에 대한 라이선스가 있어야 합니다.  디바이스가 Teams Intune 라이선스가 있는 사용자 계정에 로그인하는 한, 디바이스는 로그인 프로세스의 일부로 Microsoft Intune 자동으로 등록됩니다.
- **Intune 구성** Android 디바이스 관리자 등록을 위해 제대로 구성된 Intune 테넌트가 설정되어 있어야 합니다.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Android 기반 디바이스에 Teams Intune 구성

Teams Android 기반 디바이스는 Android 디바이스 관리자(DA) 관리를 통해 Intune에서 관리됩니다. 디바이스를 Intune에 등록하기 전에 수행할 몇 가지 기본 단계가 있습니다.  현재 Intune을 통해 디바이스를 관리하고 있는 경우 이러한 모든 일을 이미 수행한 것일 수 있습니다.  그렇지 않은 경우 다음과 같습니다.

> [!NOTE]
> - 테넌트 관리자가 공용 영역 휴대폰을 Intune에 등록하려면 계정에 Intune 라이선스를 추가하고 Intune 등록 단계를 따라야 합니다.
> - 디바이스에 로그인하는 데 Teams Intune에 대한 라이선스가 없는 경우 계정에 대해 Intune 준수 정책 및 등록 제한을 사용하지 않도록 설정해야 합니다.



1. Intune MDM(모바일 장치 관리) 기관을 설정합니다.  

   Intune을 사용한 적이 없는 경우 디바이스를 등록하기 전에 MDM 기관을 설정해야 합니다. 자세한 내용은 모바일 장치 관리 [권한 설정 을 참조하세요](/intune/fundamentals/mdm-authority-set).  이 단계는 새 Intune 테넌트 만들기 시 수행해야 하는 일회성 단계입니다.
1. Android 디바이스 관리자 등록을 사용하도록 설정합니다.
  
   Android 기반 Teams 디바이스는 Intune을 사용하여 디바이스 관리자 장치로 관리됩니다.  새로 만든 테넌트의 경우 디바이스 관리자 등록이 기본적으로 해제됩니다. Android [디바이스 관리자 등록을 참조하세요](/intune/enrollment/android-enroll-device-administrator).
1. 사용자에게 라이선스를 할당합니다. 
 
   Intune에 Teams 디바이스의 사용자에게 유효한 Intune 라이선스가 할당되어야 합니다. 자세한 내용은 Intune에 디바이스를 등록할 수 있도록 사용자에게 라이선스 할당 [을 참조하세요](/intune/fundamentals/licenses-assign).
1. 디바이스 관리자 규정 준수 정책을 할당합니다.  

   1. Android 디바이스 관리자 준수 정책을 생성합니다.

   1. 디바이스에 Azure Active Directory 사용자를 포함하는 Teams 그룹에 할당합니다. 준수 [정책 사용을 참조하여 Intune을 사용하여 관리하는 디바이스에 대한 규칙을 설정합니다](/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>참고 항목

[Teams용 전화](phones-for-teams.md)

[IP Phone이 인증된 Microsoft Teams](teams-ip-phones.md)

[Teams 표시](teams-displays.md)

[Teams에서 디바이스 관리](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
