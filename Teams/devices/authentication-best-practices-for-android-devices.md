---
title: Android 디바이스에 대한 인증 모범 사례
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Android 디바이스 인증에 Teams 모범 사례 가이드입니다.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0ff320688d7afc583e1e806803349fb3d07ceb0c
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767211"
---
# <a name="authentication-best-practices-for-teams-android-devices"></a>Android 디바이스에 대한 Teams 모범 사례

이 문서에서는 휴대폰 및 호출 디바이스에 대한 인증 정책을 배포하는 Teams 일반적인 지침 및 모범 사례를 제공합니다.

>[!NOTE]
>조건부 액세스에는 Azure AD(Azure Active Directory) Premium 필요합니다.

>[!NOTE]
>Android 모바일 디바이스에 대한 정책은 Android 디바이스에 Teams 수 있습니다.


## <a name="personal-and-shared-devices"></a>개인 및 공유 디바이스

회의실 Teams 공용 지역 전화와 같은 공유 디바이스는 일반적으로 개인 디바이스에 적용되는 등록 및 규정 준수에 대해 동일한 요구 사항을 사용할 수 없습니다. 공유 디바이스에 개인 디바이스 인증 요구 사항을 적용하면 다음과 같은 로그인 문제가 발생할 수 있습니다.

1.  **암호 정책으로 인해 디바이스가 서명됩니다.**

디바이스에 Teams 암호 만료 정책이 있습니다. 사용자와 달리 공유 디바이스와 함께 사용하는 계정에는 암호가 만료될 때 업데이트하고 유효한 상태로 복원할 지정된 사용자가 없습니다. 조직에서 암호가 만료되고 정기적으로 다시 설정해야 하는 경우 이러한 계정은 Teams 관리자가 암호를 다시 설정하고 다시 로그인할 때까지 Teams 디바이스에서 작동을 중지합니다.

2.  **조건부 액세스 정책으로 인해 디바이스에 로그인하지 못했습니다.**

공유 디바이스는 사용자 계정 또는 개인 디바이스에 대한 Azure AD 조건부 액세스 정책을 준수할 수 없습니다. 공유 디바이스가 조건부 액세스 정책에 대한 사용자 계정 또는 개인 디바이스와 그룹화되는 경우 로그인이 실패합니다.

예를 들어 액세스하는 데 다단계 인증이 필요한 Teams 인증을 완료하려면 사용자 개입이 필요합니다. 공유 디바이스는 다단계 인증을 지원하지 않습니다. 마찬가지로, 계정이 X 일마다 다시 확인하도록 구성된 경우 공유 디바이스는 사용자 개입 없이 문제를 해결할 수 없습니다.

## <a name="best-practices-for-teams-shared-device-deployments"></a>공유 디바이스 배포에 Teams 모범 사례

조직에서 디바이스를 배포할 때 Teams 권장됩니다.

### <a name="password-policy"></a>**암호 정책**

Teams 공유 디바이스는 Exchange [계정을 사용해야 합니다.](/exchange/recipients-in-exchange-online/manage-resource-mailboxes) 이러한 계정은 Active Directory에서 동기화되거나 Azure AD에서 직접 만들 수 있습니다. 사용자에 대한 모든 암호 만료 정책은 공유 디바이스에서 사용되는 계정에도 Teams 적용됩니다.

암호 만료 정책으로 인한 중단을 방지하기 위해 공유 디바이스의 암호 만료 정책을 만료하지 않도록 설정하세요.

Teams 디바이스 CY21 업데이트 [#1(Teams](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) 버전 1449/1.0.94.202102403)Teams 및 [CY202로 시작 1 업데이트 #2(android에서](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) Teams 버전 1449/1.0.96.2021051904 Microsoft Teams 룸) 테넌트 관리자는 원격으로 Teams 수 있습니다. 디바이스를 설정하기 위해 기술자에게 암호를 공유하지 않습니다. 관리자는 원격 로그인을 사용하여 확인 코드를 발급한 다음 관리 센터에서 Teams 로그인합니다.

자세한 내용은 [원격 프로비전](/MicrosoftTeams/devices/remote-provision-remote-login)및 Android 디바이스에 Teams 참조하세요. 

### <a name="conditional-access-policies"></a>**조건부 액세스 정책**

Azure AD 조건부 액세스는 로그인하기 위해 디바이스가 충족해야 하는 추가 요구 사항을 설정합니다. Teams 디바이스의 경우 다음 지침을 검토하여 적절한 정책을 작성한지 여부를 판단합니다. 조건부 액세스에 대한 개요는 조건부 액세스 [를 참조하세요.](/azure/active-directory/conditional-access/overview)

### <a name="multi-factor-authentication"></a>다단계 인증

공유 디바이스에 대한 계정은 사용자 계정이 아닌 공간 또는 물리적 공간에 연결됩니다. 공유 디바이스는 다단계 인증을 지원하지 않습니다. 모든 다단계 인증 정책에서 공유 디바이스를 제외합니다.

>[!TIP]
>명명된 [위치를 사용하거나](/azure/active-directory/conditional-access/location-condition) [규정](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) 준수 디바이스를 사용하여 공유 디바이스를 보호합니다.

### <a name="location-based-access-with-named-locations"></a>명명된 위치가 있는 위치 기반 액세스

공유 디바이스가 다양한 IP 주소로 식별할 수 있는 잘 정의된 위치에 프로비전되는 [](/azure/active-directory/conditional-access/location-condition) 경우 이러한 디바이스에 대해 명명된 위치를 사용하여 조건부 액세스를 구성할 수 있습니다. 이 조건부를 사용하면 이러한 디바이스가 네트워크 내에 있는 경우만 회사 리소스에 액세스할 수 있습니다.

### <a name="require-compliant-device"></a>규정 준수 디바이스 필요

>[!NOTE]
>디바이스 규정 준수에는 Intune 라이선스가 필요합니다.

공유 디바이스를 Intune에 등록하는 경우 규정 준수 디바이스만 회사 리소스에 액세스할 수 있도록 조건부 액세스의 제어로 디바이스 준수를 구성할 수 있습니다. Teams 규정 준수에 따라 조건부 액세스 정책에 대해 디바이스를 구성할 수 있습니다. 자세한 내용은 조건부 액세스: 규정 준수 또는 [하이브리드 Azure AD 조인 디바이스 필요 를 참조하세요.](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)

Intune을 사용하여 디바이스에 대한 규정 준수 설정을 설정하는 경우 규정 준수 정책 사용을 참조하여 [Intune을](/intune/protect/device-compliance-get-started)사용하여 관리하는 디바이스에 대한 규칙을 설정합니다.

>[!NOTE]
> hotdesking에 사용되는 공유 디바이스는 규정 준수 정책에서 제외해야 합니다. 규정 준수 정책은 디바이스가 핫 데스크 사용자 계정에 등록하지 못하도록 방지합니다. 대신 명명된 위치를 사용하여 이러한 디바이스를 보호합니다.
> 보안을 강화하려면 명명된 위치 정책 외에도 핫데스킹 사용자에게 다단계 인증을 요구할 수도 있습니다. [](/azure/active-directory/authentication/tutorial-enable-azure-mfa)

### <a name="sign-in-frequency"></a>로그인 빈도

조건부 액세스에서 사용자가 [](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) 지정된 기간 후에 리소스에 액세스하도록 다시 로그인하도록 로그인 빈도를 구성할 수 있습니다. 룸 계정에 대해 로그인 빈도가 적용된 경우 공유 디바이스는 관리자가 다시 로그인할 때까지 로그인합니다. Microsoft는 모든 로그인 빈도 정책에서 공유 디바이스를 제외하는 것이 좋습니다.

### <a name="filters-for-devices"></a>디바이스에 대한 필터

[디바이스에 대한](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) 필터는 Azure AD에서 사용할 수 있는 디바이스 속성을 기반으로 디바이스에 대해 더 세분화된 정책을 구성할 수 있는 조건부 액세스의 기능입니다. 디바이스 개체에서 확장 특성 1-15를 설정한 다음, 사용자 지정 값을 사용하여 사용자 지정 값을 사용할 수도 있습니다.

디바이스에 대한 필터를 사용하여 공통 영역 디바이스를 식별하고 두 가지 주요 시나리오에서 정책을 사용하도록 설정합니다.

1.  개인 장치에 적용되는 정책에서 공유 디바이스를 제외합니다. 예를 들어 핫데스크에 사용되는 공유 디바이스에는 디바이스 준수 요구가 적용되지 않지만 모델 번호를 기반으로 하는 다른 모든 디바이스에 대해 적용됩니다.

2.  개인 디바이스에 적용되지 않는 공유 디바이스에 대한 특수 정책을 적용합니다. 예를 들어 이러한 디바이스에 대해 설정한 확장 특성(예: "CommonAreaPhone")에 따라 공용 영역 디바이스에만 명명된 위치를 정책으로 요구합니다.

>[!NOTE] 
> 모델, 제조업체 **및**  **operatingSystemVersion과** 같은 일부 특성은 디바이스가 Intune에서 관리하는 경우에만 설정할 수 있습니다. 디바이스가 Intune에서 관리되지 않는 경우 확장 특성을 사용합니다.
