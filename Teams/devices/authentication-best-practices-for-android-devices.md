---
title: Android 디바이스의 공유 디바이스 관리를 Microsoft Teams 위한 인증 모범 사례입니다.
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Teams 공유 Android 디바이스 관리에 대한 모범 사례입니다. 여기에는 조건부 액세스, 암호 정책, 다단계 인증 조언 등이 있습니다.
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
ms.openlocfilehash: 6eef76052f662b26f946bf80839a62186c287b68
ms.sourcegitcommit: d425748a50964ebc78e5d38fce564a444a449f43
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65635466"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Android 디바이스에서 공유 디바이스 관리를 Teams 위한 인증 모범 사례

Teams 사용하는 디바이스의 목표는 다양한 디바이스 관리 전략을 필요한 것으로 만듭니다. 예를 들어 단일 영업 담당자가 사용하는 개인 비즈니스 태블릿에는 많은 고객 서비스 사용자가 공유하는 전화 통화와 다른 요구 사항 집합이 있습니다.

보안 관리자 및 운영 팀은 조직에서 사용할 수 있는 디바이스를 계획해야 합니다. 각 용도에 가장 적합한 *보안* 조치를 구현해야 합니다. 이 문서의 권장 사항은 이러한 결정 중 일부를 더 쉽게 만듭니다.

>[!NOTE]
>조건부 액세스에는 Azure Active Directory(Azure AD) Premium 구독이 필요합니다.

>[!NOTE]
>Android 모바일 디바이스에 대한 정책은 Teams Android 디바이스에 적용되지 않을 수 있습니다.

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>인증 권장 사항은 개인 디바이스와 공유 Android 디바이스에 대해 다릅니다.

공유 Teams 디바이스는 개인 디바이스에서 사용되는 등록 및 규정 준수에 대해 동일한 요구 사항을 사용할 수 없습니다. 공유 디바이스에 개인 디바이스 인증 요구 사항을 적용하면 로그인 문제가 발생합니다.

1.  **암호 정책으로 인해 디바이스가 로그아웃됩니다.**

Teams 디바이스에서 사용되는 계정에는 암호 만료 정책이 있습니다. 공유 디바이스와 함께 사용되는 계정에는 암호가 만료되면 업데이트하고 작업 상태로 복원할 특정 사용자가 없습니다. 조직에서 암호를 만료하고 가끔 다시 설정해야 하는 경우 Teams 관리자가 암호를 재설정하고 다시 로그인할 때까지 이러한 계정은 Teams 디바이스에서 작업을 중지합니다.

**과제**: 액세스에 관해서. 디바이스에서 Teams 사용자의 계정에 암호 만료 정책이 있습니다. 암호가 만료되면 변경하기만 하면 됩니다. 그러나 *공유 디바이스*(리소스 계정)에서 사용되는 계정은 필요에 따라 암호를 변경할 수 있는 단일 사용자에게 연결되지 않을 수 있습니다. 즉, 암호가 만료되고 작업을 다시 시작하는 방법을 모르고 작업자를 그 자리에 남겨 둘 수 있습니다.

조직에서 암호 재설정을 요구하거나 암호 만료를 적용하는 경우 이러한 공유 계정이 다시 로그인할 수 있도록 Teams 관리자가 암호를 재설정할 준비가 되어 있는지 확인합니다.

2.  **조건부 액세스 정책으로 인해 디바이스가 로그인하지 못합니다.**

**과제**: 공유 디바이스는 사용자 계정 또는 개인 디바이스에 대한 Azure AD 조건부 액세스 정책을 준수할 수 없습니다. 공유 디바이스가 조건부 액세스 정책에 대한 사용자 계정 또는 개인 디바이스와 그룹화되면 로그인이 *실패합니다*.

예를 들어 Teams 액세스하는 데 다단계 인증이 필요한 경우 해당 인증을 완료하려면 코드의 사용자 항목이 필요합니다. 공유 디바이스에는 일반적으로 다단계 인증을 구성하고 완료할 수 있는 단일 사용자가 없습니다. 또한 계정이 X일마다 다시 인증해야 하는 경우 공유 디바이스는 사용자의 개입 없이는 문제를 해결할 수 없습니다.

다단계 인증은 공유 디바이스에서 지원되지 않습니다. 대신 사용할 메서드는 아래에 설명되어 있습니다.

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>Teams 사용하여 공유 Android 디바이스를 배포하기 위한 모범 사례

조직에서 Teams 디바이스를 배포할 때 다음 설정을 권장합니다.

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**리소스 계정 사용 및 암호 만료 축소**

Teams 공유 디바이스는 [Exchange 리소스 사서함](/exchange/recipients-in-exchange-online/manage-resource-mailboxes)을 사용해야 합니다. 이러한 사서함을 만들면 계정이 자동으로 생성됩니다. 이러한 계정은 Active Directory에서 Azure AD 동기화하거나 Azure AD 직접 만들 수 있습니다. 사용자에 대한 모든 암호 만료 정책은 Teams 공유 디바이스에서 사용되는 계정에도 적용되므로 암호 만료 정책으로 인한 중단을 방지하기 위해 공유 디바이스에 대한 암호 만료 정책을 만료되지 않도록 설정합니다.

Teams 디바이스 CY21 [업데이트 #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones)(Teams 휴대폰용 Teams 버전 1449/1.0.94.2021022403) 및 [CY20부터 21 업데이트 #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android)(Android Microsoft Teams 룸 Teams 버전 1449/1.0.96.2021051904) 테넌트 관리자는 Teams 로그인할 수 있습니다. 디바이스를 원격으로 사용합니다. 테넌트 관리자는 기술자와 암호를 공유하여 디바이스를 설정하는 대신 원격 로그인을 사용하여 확인 코드를 발급해야 합니다. Teams 관리 센터에서 이러한 디바이스에 로그인할 수 있습니다.

자세한 내용은 [원격 프로비저닝을 참조하고 Teams Android 디바이스에 로그인합니다](/MicrosoftTeams/devices/remote-provision-remote-login). 

### <a name="review-these-conditional-access-policies"></a>**이러한 조건부 액세스 정책 검토**

Azure AD 조건부 액세스는 로그인하기 위해 디바이스가 충족해야 하는 추가 요구 사항을 설정합니다. Teams 디바이스의 경우 다음 지침을 검토하여 공유 디바이스 사용자가 작업을 수행할 수 있도록 하는 정책을 작성했는지 확인합니다.

> [!TIP]
> 조건부 액세스에 대한 개요는 [조건부 액세스란?](/azure/active-directory/conditional-access/overview)을 참조하세요.

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>공유 디바이스에 다단계 인증 사용 안 함

공유 디바이스에 대한 계정은 최종 사용자 계정이 아닌 회의실 또는 물리적 공간에 연결됩니다. 공유 디바이스는 다단계 인증을 지원하지 않으므로 모든 다단계 인증 정책에서 공유 디바이스를 제외합니다.

>[!TIP]
>[명명된 위치를](/azure/active-directory/conditional-access/location-condition) 사용하거나 [규격 디바이스를 사용하여](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) 공유 디바이스를 보호해야 합니다.

### <a name="you-can-use-location-based-access-with-named-locations"></a>명명된 위치에서 위치 기반 액세스를 사용할 수 있습니다.

공유 디바이스가 다양한 IP 주소로 식별할 수 있는 잘 정의된 위치에 프로비전된 경우 이러한 디바이스에 [대해 명명된 위치를](/azure/active-directory/conditional-access/location-condition) 사용하여 조건부 액세스를 구성할 수 있습니다. 이 조건부를 통해 이러한 디바이스는 네트워크 내에 있는 경우에만 회사 리소스에 액세스할 수 있습니다.

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>규격 공유 디바이스를 필요로 하지 않는 시기 및 시기

>[!NOTE]
>디바이스를 준수하려면 Intune 라이선스가 필요합니다.

공유 디바이스를 Intune 등록하는 경우 규격 디바이스만 회사 리소스에 액세스할 수 있도록 디바이스 준수를 조건부 액세스의 컨트롤로 구성할 수 있습니다. Teams 디바이스는 디바이스 준수에 따라 조건부 액세스 정책에 대해 구성할 수 있습니다. 자세한 내용은 [조건부 액세스: 규격 또는 하이브리드 Azure AD 조인 디바이스 필요](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)를 참조하세요.

Intune 사용하여 디바이스에 대한 준수 설정을 설정하려면 [준수 정책을 사용하여 Intune 사용하여 관리하는 디바이스에 대한 규칙을 설정하는 방법을](/intune/protect/device-compliance-get-started) 참조하세요.

>[!NOTE]
> *핫 데스크* 에 사용되는 공유 디바이스는 규정 준수 정책에서 제외해야 합니다. 규정 준수 정책을 사용하면 디바이스가 핫 데스크 사용자 계정에 등록되지 않습니다. **대신 명명된 위치를 사용하여 이러한 디바이스를 보호합니다**.
> 보안을 강화하려면 명명된 위치 정책 외에도 *핫 데스크 사용자/사용자 계정에* 대한 [다단계 인증을 요구할](/azure/active-directory/authentication/tutorial-enable-azure-mfa) 수도 있습니다.

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>로그인 빈도 조건에서 공유 디바이스 제외

조건부 액세스에서 사용자가 지정된 기간 후에 리소스에 액세스하기 위해 다시 로그인하도록 로그인 [빈도를 구성할](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) 수 있습니다. 회의실 계정에 로그인 빈도가 적용되는 경우 공유 디바이스는 관리자가 다시 로그인할 때까지 로그아웃합니다. Microsoft는 모든 로그인 빈도 정책에서 공유 디바이스를 제외하는 것이 좋습니다.

### <a name="using-filters-for-devices"></a>디바이스에 필터 사용

[디바이스 필터](/azure/active-directory/conditional-access/concept-condition-filters-for-devices)는 조건부 액세스의 기능으로, Azure AD 사용할 수 있는 디바이스 속성을 기반으로 디바이스에 대해 보다 세부적인 정책을 구성할 수 있습니다. 또한 디바이스 개체에서 확장 특성을 1-15로 설정한 다음 이를 사용하여 사용자 지정 값을 사용할 수도 있습니다.

디바이스에 대한 필터를 사용하여 공통 영역 디바이스를 식별하고 다음 두 가지 주요 시나리오에서 정책을 사용하도록 설정합니다.

1.  개인 디바이스에 적용된 정책에서 공유 디바이스 제외 예를 들어 핫 데스크에 사용되는 공유 디바이스에는 디바이스 규정 준수가 *적용되지* 않지만 모델 번호에 따라 다른 모든 디바이스에 *적용됩니다* .

2.  개인 디바이스에 적용 *해서는 안* 되는 공유 디바이스에 특별 정책 적용 예를 들어 이러한 디바이스에 대해 설정한 확장 특성(예: "CommonAreaPhone")에 따라 공통 영역 디바이스에 대해서만 명명된 위치를 정책으로 요구합니다.

>[!NOTE] 
> **모델**, **제조업체** 및 **operatingSystemVersion** 과 같은 일부 특성은 Intune 디바이스를 관리하는 경우에만 설정할 수 있습니다. 디바이스가 Intune 관리되지 않는 경우 확장 특성을 사용합니다.
