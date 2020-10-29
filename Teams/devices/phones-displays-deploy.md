---
title: Intune을 사용 하 여 팀 전화 및 팀의 배포 표시
ms.author: v-lanac
author: lanachin
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
description: 이 문서에서는 Microsoft 팀이 표시 하는 기능에 대 한 개요를 제공 합니다.
ms.openlocfilehash: acebf619d76cd6df2f0da305deedec9dd3b79aa0
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787639"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Intune을 사용 하 여 팀 전화 및 팀의 배포 표시

이 문서에서는 Intune을 사용 하 여 팀 전화 및 팀 표시를 배포 하는 방법에 대 한 개요를 제공 합니다.

## <a name="conditional-access"></a>조건부 액세스

조건부 액세스는 Office 365 리소스에 액세스 하는 디바이스가 제대로 관리 되 고 안전한 지 확인 하는 데 도움이 되는 azure Active Directory (Azure AD) 기능입니다.  팀 서비스에 조건부 액세스 정책을 적용 하는 경우, Android 장치 (팀 전화, 팀 표시 포함)가 Intune에 등록 되어야 하 고 해당 설정이 정책을 준수 해야 합니다.  장치가 Intune에 등록 되지 않은 경우 또는 해당 설정이 정책에 맞지 않는 경우에는 조건부 액세스를 통해 사용자가 디바이스에서 팀 앱에 로그인 하거나 해당 앱을 사용할 수 없습니다.

일반적으로 Intune 내에서 정의 된 규정 준수 정책은 사용자 그룹에 게 할당 됩니다.  즉, Android 준수 정책을 user@contoso.com에 할당 하면 해당 정책은 Android smartphone 및 user@contoso.com 로그인 하는 모든 Android 기반 팀 장치에 동일 하 게 적용 됩니다.

사용자의 조직에 Intune 등록이 적용 되어야 하는 조건부 액세스를 사용 하는 경우에는 성공적으로 Intune을 등록할 수 있도록 설정 해야 하는 몇 가지 사항이 있습니다.

- **Intune 라이선스** 팀 장치에 로그인 하는 사용자에 게 Intune 라이선스가 있어야 합니다.  팀 장치가 유효한 Intune 라이선스가 있는 사용자 계정에 로그인 한 경우 로그인 프로세스의 일부로 장치가 Microsoft Intune에 자동으로 등록 됩니다.
- **Intune 구성** Android 장치 관리자 등록에 대해 올바르게 구성 된 Intune 테 넌 트가 설정 되어 있어야 합니다.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Intune에서 팀으로 등록 Android 기반 장치 구성

팀 Android 기반 장치는 DA (Android 장치 관리자) 관리를 통해 Intune에서 관리 합니다. Intune에 장치를 등록할 수 있으려면 먼저 몇 가지 기본 단계를 수행 해야 합니다.  현재 Intune을 사용 하 여 이미 장치를 관리 하 고 있는 경우 이러한 모든 작업을 이미 수행 했을 수 있습니다.  그렇지 않은 경우 수행할 작업은 다음과 같습니다.

1. Intune MDM (모바일 디바이스 관리) 인증 기관 설정.  아직 Intune을 사용 하지 않은 경우 디바이스를 등록 하기 전에 MDM 기관을 설정 해야 합니다. 자세한 내용은 [모바일 장치 관리 기관 설정을](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)참조 하세요.  이것은 새 Intune 테 넌 트를 만들 때 수행 해야 하는 일회성 단계입니다.
2. Android 장치 관리자 등록을 사용 하도록 설정 합니다. Android 기반 팀 디바이스는 Intune을 사용 하 여 디바이스 관리자 장치로 관리 됩니다.  새로 만든 테 넌 트에 대 한 장치 관리자 등록은 기본적으로 해제 되어 있습니다.  자세한 내용은 [Android 장치 관리자 등록](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)을 참조 하세요.
3. 사용자에 게 라이선스를 할당 합니다. Intune을 등록 하는 팀 디바이스의 사용자에 게 유효한 Intune 라이선스를 할당 해야 합니다. 자세한 내용은 [Intune에서 장치를 등록할 수 있도록 사용자에 게 라이선스 할당](https://docs.microsoft.com/intune/fundamentals/licenses-assign)을 참조 하세요.
4. 장치 관리자 준수 정책을 할당 합니다.  Android 장치 관리자 준수 정책을 만들고 팀 디바이스에 로그인 할 사용자가 포함 된 Azure Active Directory 그룹에 할당 합니다. 자세한 내용은 [준수 정책을 사용 하 여 Intune을 사용 하 여 관리 하는 장치에 대 한 규칙 설정](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)을 참조 하세요.

## <a name="see-also"></a>참고 항목

[Teams용 전화](phones-for-teams.md)

[Microsoft 팀에 대해 인증 된 IP 전화](teams-ip-phones.md)

[팀 표시](teams-displays.md)

[Teams에서 디바이스 관리](device-management.md)

[팀 마켓플레이스](https://office.com/teamsdevices)
