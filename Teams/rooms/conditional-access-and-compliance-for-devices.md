---
title: 조건부 액세스 및 규정 준수 모범 사례를 Microsoft Teams 룸
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 권장 조건부 액세스 및 Intune 디바이스 준수 정책 및 모범 사례에 대해 Microsoft Teams 룸.
ms.openlocfilehash: 1f4bec9d47b73be1638b1740afeb879b4dfb4026
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689192"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>조건부 액세스 및 Intune 규정 준수를 Microsoft Teams 룸

이 문서에서는 공유 공간에 사용되는 사용자에 대한 조건부 액세스 및 Intune 디바이스 준수 정책에 Microsoft Teams 룸 요구 사항 및 모범 사례를 제공합니다.

## <a name="requirements"></a>요구 사항

Teams 룸 조건부 액세스 정책을 할당하려는 디바이스에 이미 배포되어야 합니다. 아직 배포하지 않은 Teams 룸 자세한 내용은 회의실 및 공유 디바이스에 Teams 리소스 계정 [](with-office-365.md) 만들기 및 Android에서 Microsoft Teams 룸 배포를 참조하세요.[](../devices/collab-bar-deploy.md)

조건부 Azure Active Directory 사용하려면 P1 서비스 계획이 필요합니다. 이 라이선스는 라이선스에 Microsoft Teams 룸 있습니다.

## <a name="teams-rooms-conditional-access-best-practices"></a>Teams 룸 액세스 모범 사례

조건부 액세스 정책은 공유 공간에 있으며 여러 사용자가 사용하는 디바이스에서 로그인 프로세스를 보호할 수 있습니다. Azure AD(Azure AD)의 조건부 액세스에 대한 개요는 Azure Active Directory 조건부 액세스[란?을 Azure Active Directory.](/azure/active-directory/conditional-access/overview)

조건부 액세스를 사용하여 보안 Teams 룸 경우 다음 모범 사례를 고려합니다.

-   배포 및 관리를 간소화하기 위해 Microsoft 365 그룹과 연결된 모든 Teams 룸 계정이 포함됩니다.

-   모든 리소스 계정에 대한 이름 Teams 룸 있습니다. 예를 들어 계정 이름 'mtr-room1@contoso.com' 및 'mtr-room2@contoso.com'은 모두 'mtr-'으로 시작됩니다.
    계정 이름이 표준화된 경우 Azure AD의 동적 그룹을 사용하여 이러한 모든 계정에 조건부 액세스 정책을 자동으로 적용할 수 있습니다. 동적 [그룹에 대한](/azure/active-directory/enterprise-users/groups-dynamic-membership) 자세한 내용은 동적으로 채워진 그룹 멤버 자격에 대한 규칙을 참조하세요.

지원되는 조건부 액세스 할당 목록은 Teams 룸 조건부 [액세스 정책을 참조하세요](supported-ca-and-compliance-policies.md#supported-conditional-access-policies).

## <a name="example-conditional-access-policy"></a>예제 조건부 액세스 정책

아래 예제에서 조건부 액세스 정책은 다음과 같이 작동합니다.

1.  로그인하는 계정은 특정 사용자 그룹의 구성원이 되어야 합니다. 이 예제에서는 "공유 디바이스" 그룹입니다.

2.  로그인한 계정은 온라인에서 Exchange Online, Microsoft Teams 또는 SharePoint 시도해야 합니다. 다른 클라이언트 앱에 로그인하려는 시도는 거부됩니다.

3.  리소스 계정은 디바이스 플랫폼에서 Windows 있어야 합니다.

4.  리소스 계정도 알려진 신뢰할 수 있는 위치에서 로그인해야 합니다.

이러한 조건이 성공적으로 충족되는 경우 사용자가 올바른 사용자 이름과 암호를 입력하면 리소스 계정이 Teams.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Microsoft Intune 준수하는 조건부 액세스 Teams 룸

규정 준수 요구 사항은 디바이스가 최소 운영 체제 버전과 같이 준수로 표시되어야 하는 정의 규칙입니다. 디바이스는 리소스 계정에 로그인하는 데 사용되기 전에 규정을 준수하는 것으로 간주해야 합니다.

지원되는 Intune 준수 정책 목록은 지원되는 디바이스 Teams 룸 [준수 정책을 참조하세요](supported-ca-and-compliance-policies.md#supported-device-compliance-policies).

Android 디바이스를 사용하여 Intune을 설정하는 Teams 자세한 내용은 Android 기반 디바이스를 등록하도록 [Intune](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices) 구성을 Teams 참조하세요.

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>예제(Windows 전용): Intune 디바이스 규정 준수를 사용하여 조건부 액세스

이 예제에서는 Teams 룸 Windows

1. 방화벽이 Teams 룸 실행되고 Windows.

2. Microsoft Defender가 실행 중인 Teams 룸.

3. 이 Teams 룸이 이러한 요구 사항 중 하나를 충족하지 않는 경우 규정 준수로 표시되지 않습니다. 디바이스는 로그인하지 않습니다.

이 규정 준수 정책은 리소스 계정만이 아니라 모든 사용자에게 Teams 적용됩니다.
