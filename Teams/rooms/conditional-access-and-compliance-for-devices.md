---
title: Microsoft Teams 룸 대한 조건부 액세스 및 규정 준수 모범 사례
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 권장되는 조건부 액세스 및 Intune 디바이스 준수 정책 및 Microsoft Teams 룸 대한 모범 사례에 대해 알아봅니다.
ms.openlocfilehash: e16513a840dadf7a5cabe961a0fbbd9135da9b89
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606547"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Microsoft Teams 룸 대한 조건부 액세스 및 Intune 규정 준수

이 문서에서는 공유 공간에 사용되는 Microsoft Teams 룸 대한 조건부 액세스 및 Intune 디바이스 준수 정책에 대한 요구 사항 및 모범 사례를 제공합니다.

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

## <a name="requirements"></a>요구 사항

Teams 룸 조건부 액세스 정책을 할당하려는 디바이스에 이미 배포되어 있어야 합니다. 아직 Teams 룸 배포하지 않은 경우 [회의실 및 공유 Teams 디바이스에 대한 리소스 계정 만들기 및](with-office-365.md) [Android에서 Microsoft Teams 룸 배포](../devices/collab-bar-deploy.md)를 참조하세요.

조건부 액세스를 사용하려면 Azure Active Directory P1 서비스 계획이 필요합니다. Microsoft Teams 룸 라이선스에 포함되어 있습니다.

## <a name="teams-rooms-conditional-access-best-practices"></a>조건부 액세스 모범 사례 Teams 룸

조건부 액세스 정책은 공유 공간에 있고 여러 사람이 사용하는 디바이스에서 로그인 프로세스를 보호할 수 있습니다. Azure Active Directory의 조건부 액세스(Azure AD)에 대한 개요[는 Azure Active Directory의 조건부 액세스란?](/azure/active-directory/conditional-access/overview)을 참조하세요.

조건부 액세스를 사용하여 Teams 룸 보호하는 경우 다음 모범 사례를 고려합니다.

-   배포 및 관리를 간소화하려면 한 사용자 그룹에 Teams 룸 연결된 모든 Microsoft 365 회의실 리소스 계정을 포함합니다.

-   모든 Teams 룸 리소스 계정에 대한 명명 표준이 있습니다. 예를 들어 계정 이름 'mtr-room1@contoso.com' 및 'mtr-room2@contoso.com'은 모두 'mtr-' 접두사로 시작합니다.
    계정 이름이 표준화되면 Azure AD 동적 그룹을 사용하여 이러한 모든 계정에 조건부 액세스 정책을 한 번에 자동으로 적용할 수 있습니다. [동적 그룹에 대한 자세한 내용은 동적으로 채워진 그룹 멤버 자격](/azure/active-directory/enterprise-users/groups-dynamic-membership)에 대한 규칙을 참조하세요.

Teams 룸 대해 지원되는 조건부 액세스 할당 목록은 [지원되는 조건부 액세스 정책을](supported-ca-and-compliance-policies.md#supported-conditional-access-policies) 참조하세요.

## <a name="example-conditional-access-policy"></a>조건부 액세스 정책 예제

아래 예제에서 조건부 액세스 정책은 다음과 같이 작동합니다.

1.  계정 로그인은 특정 사용자 그룹의 구성원이어야 합니다(이 예제에서는 "공유 디바이스" 그룹).

2.  계정 로그인은 Exchange Online, Microsoft Teams 또는 SharePoint Online에만 액세스해야 합니다. 다른 클라이언트 앱에 로그인하려는 시도는 거부됩니다.

3.  리소스 계정은 Windows 디바이스 플랫폼에서 로그인해야 합니다.

4.  또한 리소스 계정은 신뢰할 수 있는 알려진 위치에서 로그인해야 합니다.

이러한 조건이 성공적으로 충족되고 사용자가 올바른 사용자 이름과 암호를 입력하면 리소스 계정이 Teams에 로그인됩니다.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Teams 룸 Microsoft Intune 규정 준수를 사용하여 조건부 액세스

규정 준수 요구 사항은 최소 운영 체제 버전과 같이 디바이스가 준수로 표시되도록 충족해야 하는 정의된 규칙입니다. 디바이스를 리소스 계정에 로그인하는 데 사용하려면 먼저 규정을 준수하는 것으로 간주해야 합니다.

Teams 룸 대해 지원되는 Intune 준수 정책 목록은 [지원되는 디바이스 준수 정책을](supported-ca-and-compliance-policies.md#supported-device-compliance-policies) 참조하세요.

Teams Android 디바이스를 사용하여 Intune 설정하는 방법에 대한 자세한 내용은 [Teams Android 기반 디바이스를 등록하도록 Intune 구성](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices)을 참조하세요.

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>예제(Windows에만 해당): Intune 디바이스 준수를 사용하는 조건부 액세스

이 예제에서는 Windows에서 Teams 룸

1. Windows의 Teams 룸 방화벽이 실행되고 있어야 합니다.

2. Microsoft Defender가 Teams 룸 실행 중인지를 요구합니다.

3. Teams 룸이 이러한 요구 사항 중 하나를 충족하지 않으면 규격으로 표시되지 않으며 디바이스가 로그인하지 않습니다.

이 규정 준수 정책은 Teams 리소스 계정뿐만 아니라 모든 사용자에게 적용됩니다.
