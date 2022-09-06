---
title: Microsoft Teams 룸 대해 지원되는 조건부 액세스 및 Intune 디바이스 준수 정책
ms.author: dstrome
author: dstrome
ms.reviewer: kspiess
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Microsoft Teams 룸 대해 지원되고 권장되는 조건부 액세스 및 Intune 디바이스 준수 정책에 대해 알아봅니다.
ms.openlocfilehash: 1c9b3d2a40ce34076f917026300b8b7d0921d9c8
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606437"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms-and-teams-android-devices"></a>Microsoft Teams 룸 및 Teams Android 디바이스에 대해 지원되는 조건부 액세스 및 Intune 디바이스 준수 정책

이 문서에서는 Microsoft Teams 룸 대해 지원되는 조건부 액세스 및 Intune 디바이스 준수 정책을 제공합니다. 모범 사례 및 예제 정책은 Microsoft Teams 룸 [대한 조건부 액세스 및 Intune 규정 준수 모범 사례를 참조하세요](conditional-access-and-compliance-for-devices.md).

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

> [!NOTE]
> Teams 룸 조건부 액세스 정책을 할당하려는 디바이스에 이미 배포되어 있어야 합니다. 아직 Teams 룸 배포하지 않은 경우 [회의실 및 공유 Teams 디바이스에 대한 리소스 계정 만들기 및](with-office-365.md) [Android에서 Microsoft Teams 룸 배포](../devices/collab-bar-deploy.md)를 참조하세요.

## <a name="supported-conditional-access-policies"></a>지원되는 조건부 액세스 정책  

다음 목록에는 Windows 및 Android의 Teams 룸 및 Teams 패널, 휴대폰 및 디스플레이에 대한 정책에 대해 지원되는 조건부 액세스 정책이 포함되어 있습니다.

| 할당                               | Windows에서 Teams 룸                                                                                                                                                                              | Android 및 패널에서 Teams 룸                                                                                                                                                                              | Teams 휴대폰 및 디스플레이                                                                                                                                                    |
|------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 사용자 또는 워크로드 ID              | 지원                                                                                                                                                                            | 지원                                                                                                                                                                            | 지원                                                                                                                                                            |
| 클라우드 앱 또는 작업                    | 지원 <br><br> Teams 룸 Teams 전용 모드인 경우 Office 365 Exchange Online, Office 365 SharePoint Online 및 Microsoft Teams의 세 가지 클라우드 앱에 액세스해야 합니다. | 지원 <br><br> Teams 룸 Teams 전용 모드인 경우 Office 365 Exchange Online, Office 365 SharePoint Online 및 Microsoft Teams의 세 가지 클라우드 앱에 액세스해야 합니다. | 지원<br><br>Teams Android 디바이스는 Office 365 Exchange Online, Office 365 SharePoint Online 및 Microsoft Teams의 세 가지 클라우드 앱에 액세스해야 합니다.  |
| **조건**                           | ---                                                                                                                                                                                  | ---                                                                                                                                                                                  | ---                                                                                                                                                                  |
| 사용자 위험                                | 지원                                                                                                                                                                            | 지원                                                                                                                                                                            | 지원                                                                                                                                                            |
| 로그인 위험                             | 지원                                                                                                                                                                            | 지원                                                                                                                                                                            | 지원                                                                                                                                                            |
| 디바이스 플랫폼                         | 지원                                                                                                                                                                            | 지원                                                                                                                                                                            | 지원                                                                                                                                                            |
| 위치                                | 지원                                                                                                                                                                            | 지원                                                                                                                                                                            | 지원                                                                                                                                                            |
| 클라이언트 앱                              | 지원되지 않음                                                                                                                                                                        | 지원되지 않음                                                                                                                                                                        | 지원되지 않음                                                                                                                                                        |
| 디바이스에 대한 필터                       | 지원                                                                                                                                                                            | 지원                                                                                                                                                                            | 지원                                                                                                                                                            |
| **부여**                                | ---                                                                                                                                                                                  | ---                                                                                                                                                                                  | ---                                                                                                                                                                  |
| 액세스 차단                             | 지원                                                                                                                                                                            | 지원                                                                                                                                                                            | 지원                                                                                                                                                            |
| 액세스 권한 부여                             | 지원                                                                                                                                                                            | 지원                                                                                                                                                                            |                                                                                                                                                                      |
| 다단계 인증 필요      | 지원되지 않음                                                                                                                                                                        | 지원되지 않음                                                                                                                                                                        | 지원                                                                                                                                                            |
| 디바이스를 규격으로 표시해야 합니다. | 지원                                                                                                                                                                            | 지원                                                                                                                                                                            | 지원                                                                                                                                                            |
| 하이브리드 Azure AD 조인 디바이스 필요    | 지원되지 않음                                                                                                                                                                        | 지원되지 않음                                                                                                                                                                        | 지원되지 않음                                                                                                                                                        |
| 승인된 클라이언트 앱 필요              | 지원되지 않음                                                                                                                                                                        | 지원되지 않음                                                                                                                                                                        | 지원되지 않음                                                                                                                                                        |
| 앱 보호 정책 필요            | 지원되지 않음                                                                                                                                                                        | 지원되지 않음                                                                                                                                                                        | 지원되지 않음                                                                                                                                                        |
| 암호 변경 필요                  | 지원되지 않음                                                                                                                                                                        | 지원되지 않음                                                                                                                                                                        | 지원되지 않음                                                                                                                                                        |

> [!NOTE]
> 비즈니스용 Skype Online은 사용 중지되며 지원되지 않습니다. 비즈니스용 Skype Online 클라우드 앱은 디바이스 준수 기반 조건부 액세스 정책에 대해 지원되지 않습니다.

> [!NOTE]
> Windows의 Microsoft Teams 룸 디바이스 규정 준수 권한 부여 컨트롤을 지원하려면 다음 요구 사항을 충족해야 합니다.
>
> - Microsoft Teams 룸 애플리케이션 4.8.19.0 이상
> - Windows 10 버전 20H2 이상(10.0.19042)

## <a name="supported-device-compliance-policies"></a>지원되는 디바이스 준수 정책 

Windows의 Microsoft Teams 룸 Android의 Teams 룸 다양한 디바이스 준수 정책을 지원합니다.

#### <a name="teams-rooms-on-windows"></a>[Windows에서 Teams 룸](#tab/mtr-w)

다음은 Teams 룸 사용하기 위한 디바이스 준수 설정 및 권장 사항의 표입니다.  

| 정책                                                                                                                      | 가용성   | 참고                                                                                                                                       |
|-----------------------------------------------------------------------------------------------------------------------------|----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| [**디바이스 상태**](/mem/intune/protect/compliance-policy-create-windows#device-health)                                     | --             | --                                                                                                                                          |
| BitLocker 필요                                                                                                           | 지원      | Teams 룸 BitLocker를 처음 사용하도록 설정한 경우에만 사용합니다.                                                                                |
| 디바이스에서 보안 부팅을 사용하도록 설정해야 함                                                                             | 지원      | 보안 부팅은 Teams 룸 요구 사항입니다.                                                                                              |
| 코드 무결성 필요                                                                                                      | 지원      | 코드 무결성은 이미 Teams 룸 요구 사항입니다.                                                                                    |
| [**디바이스 속성**](/mem/intune/protect/compliance-policy-create-windows#device-properties)                             | --             | --                                                                                                                                          |
| 운영 체제 버전(최소, 최대)                                                                                 | 지원되지 않음  | Teams 룸 자동으로 최신 버전의 Windows로 업데이트되고 여기에 값을 설정하면 OS 업데이트 후 로그인에 성공하지 못할 수 있습니다. |
| 모바일 디바이스용 OS 버전(최소, 최대)                                                                            | 지원되지 않습니다. |                                                                                                                                             |
| 유효한 운영 체제 빌드                                                                                               | 지원되지 않음  |                                                                                                                                             |
| [**Configuration Manager 규정 준수**](/mem/intune/protect/compliance-policy-create-windows#device-properties)              | --             | --                                                                                                                                          |
| Configuration Manager 디바이스 준수 필요                                                                        | 지원      |                                                                                                                                             |
| [**시스템 보안**](/mem/intune/protect/compliance-policy-create-windows#system-security)                                 | --             | --                                                                                                                                          |
| 모든 암호 정책                                                                                                       | 지원되지 않음  | 암호 정책은 로컬 Skype 계정이 자동으로 로그인하는 것을 방지할 수 있습니다.                                                        |
| 디바이스에서 데이터 스토리지의 암호화가 필요합니다.                                                                               | 지원      | Teams 룸 데이터 스토리지 암호화를 처음 사용하도록 설정한 경우에만 사용합니다.                                                               |
| 방화벽                                                                                                                    | 지원      | 방화벽은 이미 Teams 룸 요구 사항입니다.                                                                                           |
| TPM(신뢰할 수 있는 플랫폼 모듈)                                                                                               | 지원      | TPM(신뢰할 수 있는 플랫폼 모듈)은 이미 Teams 룸 요구 사항입니다.                                                                     |
| 바이러스 백신                                                                                                                   | 지원      | 바이러스 백신(Windows Defender)은 이미 Teams 룸 요구 사항입니다.                                                                      |
| 스파이웨어 방지                                                                                                                 | 지원      | Windows Defender(Antispyware)는 이미 Teams 룸 요구 사항입니다.                                                                    |
| Microsoft Defender 맬웨어 방지                                                                                              | 지원      | Microsoft Defender 맬웨어 방지는 이미 Teams 룸 요구 사항입니다.                                                                    |
| Microsoft Defender 맬웨어 방지 최소 버전                                                                              | 지원되지 않습니다. | Teams 룸 이 구성 요소를 자동으로 업데이트하므로 규정 준수 정책을 설정할 필요가 없습니다.                                             |
| Microsoft Defender 맬웨어 방지 보안 인텔리전스 최신                                                             | 지원      | Microsoft Defender 맬웨어 방지가 이미 Teams 룸 요구 사항인지 확인합니다.                                                      |
| 실시간 보호                                                                                                        | 지원      | 실시간 보호는 이미 Teams 룸 요구 사항입니다.                                                                            |
| [**엔드포인트용 Microsoft Defender**](/mem/intune/protect/compliance-policy-create-windows#microsoft-defender-for-endpoint) | --             | --                                                                                                                                          |
| 디바이스가 머신 위험 점수에 있거나 아래에 있어야 합니다.                                                                | 지원      |                                                                                                                                             |

#### <a name="teams-rooms-on-android"></a>[Android에서 Teams 룸](#tab/mtr-a)

다음은 Teams 룸 사용하기 위한 디바이스 준수 설정 및 권장 사항의 표입니다.  

| 정책                                                                                                                                  | 가용성  | 참고                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------|---------------|-------------------------------------------------------------------------------|
| [**엔드포인트용 Microsoft Defender**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint)             | --            | --                                                                            |
| 디바이스가 머신 위험 점수에 있거나 아래에 있어야 합니다.                                                                             | 지원되지 않음 |                                                                               |
| [**디바이스 상태**](/mem/intune/protect/compliance-policy-create-android#device-health)                                                 | --            | --                                                                            |
| 디바이스 관리자를 사용하여 관리되는 디바이스                                                                                                | 필수      | Teams Android 디바이스 관리를 사용하려면 디바이스 관리자를 사용하도록 설정해야 합니다. |
| 루팅된 디바이스                                                                                                                          | 지원     |                                                                               |
| 디바이스가 디바이스 위협 수준 또는 그 아래에 있어야 합니다.                                                                            | 지원되지 않음 |                                                                               |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health)                                           | --            | --                                                                            |
| Google Play 서비스가 구성됨                                                                                                      | 지원되지 않음 | Google 플레이는 Teams Android 디바이스에 설치되어 있지 않습니다.                         |
| 최신 보안 공급자                                                                                                            | 지원되지 않음 | Google 플레이는 Teams Android 디바이스에 설치되어 있지 않습니다.                         |
| 앱에 대한 위협 검사                                                                                                                     | 지원되지 않음 | Google 플레이는 Teams Android 디바이스에 설치되어 있지 않습니다.                         |
| SafetyNet 디바이스 증명                                                                                                            | 지원되지 않음 | Google 플레이는 Teams Android 디바이스에 설치되어 있지 않습니다.                         |
| [**디바이스 속성**](/mem/intune/protect/compliance-policy-create-android#device-properties)                                         | --            | --                                                                            |
| 운영 체제 버전(최소, 최대)                                                                                             | 지원     |                                                                               |
| [**시스템 보안**](/mem/intune/protect/compliance-policy-create-android#system-security)                                             | --            | --                                                                            |
| 디바이스에서 데이터 스토리지의 암호화가 필요합니다.                                                                                           | 지원     |                                                                               |
| [**디바이스 보안**](/mem/intune/protect/compliance-policy-create-android#device-security)                                             | --            | --                                                                            |
| 알 수 없는 원본에서 앱 차단                                                                                                         | 지원되지 않음 | Teams 관리자만 앱 또는 OEM 도구를 설치합니다.                                   |
| 앱 런타임 무결성 회사 포털                                                                                                    | 지원     |                                                                               |
| 제한된 앱                                                                                                                         | 지원되지 않음 |                                                                               |
| 디바이스에서 USB 디버깅 차단                                                                                                           | 지원     |                                                                               |
| [**모든 Android 디바이스*](/mem/intune/protect/compliance-policy-create-android#all-android-devices)                                      | --            | --                                                                            |
| 암호가 필요하기 전까지 최대 비활성 시간(분)                                                                              | 지원되지 않음 |                                                                               |
| 모바일 디바이스의 잠금을 해제하려면 암호 필요                                                                                             | 지원되지 않음 |                                                                               |
| [**Android 10 이상**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later)                                   | --            | --                                                                            |
| [**Android 9 이하 또는 Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | --            | --                                                                            |
| 필수 암호 유형                                                                                                                  | 지원되지 않음 |                                                                               |

#### <a name="teams-phones-and-displays"></a>[Teams 휴대폰 및 디스플레이](#tab/phones)

다음은 Teams 휴대폰 및 디스플레이와 함께 사용하기 위한 디바이스 준수 설정 및 권장 사항의 표입니다.  

| 정책                                                                                                                                  | 가용성  | 참고                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------|---------------|-------------------------------------------------------------------------------|
| [**엔드포인트용 Microsoft Defender**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint)             | --            | --                                                                            |
| 디바이스가 머신 위험 점수에 있거나 아래에 있어야 합니다.                                                                             | 지원되지 않음 |                                                                               |
| [**디바이스 상태**](/mem/intune/protect/compliance-policy-create-android#device-health)                                                 | --            | --                                                                            |
| 디바이스 관리자를 사용하여 관리되는 디바이스                                                                                                | 필수      | Teams Android 디바이스 관리를 사용하려면 디바이스 관리자를 사용하도록 설정해야 합니다. |
| 루팅된 디바이스                                                                                                                          | 지원     |                                                                               |
| 디바이스가 디바이스 위협 수준 또는 그 아래에 있어야 합니다.                                                                            | 지원되지 않음 |                                                                               |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health)                                           | --            | --                                                                            |
| Google Play 서비스가 구성됨                                                                                                      | 지원되지 않음 | Google 플레이는 Teams Android 디바이스에 설치되어 있지 않습니다.                         |
| 최신 보안 공급자                                                                                                            | 지원되지 않음 | Google 플레이는 Teams Android 디바이스에 설치되어 있지 않습니다.                         |
| 앱에 대한 위협 검사                                                                                                                     | 지원되지 않음 | Google 플레이는 Teams Android 디바이스에 설치되어 있지 않습니다.                         |
| SafetyNet 디바이스 증명                                                                                                            | 지원되지 않음 | Google 플레이는 Teams Android 디바이스에 설치되어 있지 않습니다.                         |
| [**디바이스 속성**](/mem/intune/protect/compliance-policy-create-android#device-properties)                                         | --            | --                                                                            |
| 운영 체제 버전(최소, 최대)                                                                                             | 지원     |                                                                               |
| [**시스템 보안**](/mem/intune/protect/compliance-policy-create-android#system-security)                                             | --            | --                                                                            |
| 디바이스에서 데이터 스토리지의 암호화가 필요합니다.                                                                                           | 지원     | 제조업체는 Intune 인식하지 못하는 방식으로 디바이스에서 암호화 특성을 구성할 수 있습니다. 이 경우 Intune 디바이스를 비준수로 표시합니다.<br><br>제조업체에서 이러한 암호화 특성을 구성하는 방법은 디바이스 모델에 따라 달라질 수 있습니다. 특정 모델에 대한 자세한 내용은 디바이스 제조업체에 문의하세요. |
| [**디바이스 보안**](/mem/intune/protect/compliance-policy-create-android#device-security)                                             | --            | --                                                                            |
| 알 수 없는 원본에서 앱 차단                                                                                                         | 지원되지 않음 | Teams 관리자만 앱 또는 OEM 도구를 설치합니다.                                   |
| 앱 런타임 무결성 회사 포털                                                                                                    | 지원     |                                                                               |
| 제한된 앱                                                                                                                         | 지원되지 않음 |                                                                               |
| 디바이스에서 USB 디버깅 차단                                                                                                           | 지원     |                                                                               |
| [**모든 Android 디바이스*](/mem/intune/protect/compliance-policy-create-android#all-android-devices)                                      | --            | --                                                                            |
| 암호가 필요하기 전까지 최대 비활성 시간(분)                                                                              | 지원되지 않음 |                                                                               |
| 모바일 디바이스의 잠금을 해제하려면 암호 필요                                                                                             | 지원되지 않음 |                                                                               |
| [**Android 10 이상**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later)                                   | --            | --                                                                            |
| [**Android 9 이하 또는 Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | --            | --                                                                            |
| 필수 암호 유형                                                                                                                  | 지원되지 않음 |                                                                               |



#### <a name="teams-panels"></a>[Teams 패널](#tab/panels)

다음은 Teams 패널에서 사용하기 위한 디바이스 준수 설정 및 권장 사항의 표입니다.  

| 정책                                                                                                                                  | 가용성  | 참고                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------|---------------|-------------------------------------------------------------------------------|
| [**엔드포인트용 Microsoft Defender**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint)             | --            | --                                                                            |
| 디바이스가 머신 위험 점수에 있거나 아래에 있어야 합니다.                                                                             | 지원되지 않음 |                                                                               |
| [**디바이스 상태**](/mem/intune/protect/compliance-policy-create-android#device-health)                                                 | --            | --                                                                            |
| 디바이스 관리자를 사용하여 관리되는 디바이스                                                                                                | 필수      | Teams Android 디바이스 관리를 사용하려면 디바이스 관리자를 사용하도록 설정해야 합니다. |
| 루팅된 디바이스                                                                                                                          | 지원     |                                                                               |
| 디바이스가 디바이스 위협 수준 또는 그 아래에 있어야 합니다.                                                                            | 지원되지 않음 |                                                                               |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health)                                           | --            | --                                                                            |
| Google Play 서비스가 구성됨                                                                                                      | 지원되지 않음 | Google 플레이는 Teams Android 디바이스에 설치되어 있지 않습니다.                         |
| 최신 보안 공급자                                                                                                            | 지원되지 않음 | Google 플레이는 Teams Android 디바이스에 설치되어 있지 않습니다.                         |
| 앱에 대한 위협 검사                                                                                                                     | 지원되지 않음 | Google 플레이는 Teams Android 디바이스에 설치되어 있지 않습니다.                         |
| SafetyNet 디바이스 증명                                                                                                            | 지원되지 않음 | Google 플레이는 Teams Android 디바이스에 설치되어 있지 않습니다.                         |
| [**디바이스 속성**](/mem/intune/protect/compliance-policy-create-android#device-properties)                                         | --            | --                                                                            |
| 운영 체제 버전(최소, 최대)                                                                                             | 지원     |                                                                               |
| [**시스템 보안**](/mem/intune/protect/compliance-policy-create-android#system-security)                                             | --            | --                                                                            |
| 디바이스에서 데이터 스토리지의 암호화가 필요합니다.                                                                                           | 지원     |                                                                               |
| [**디바이스 보안**](/mem/intune/protect/compliance-policy-create-android#device-security)                                             | --            | --                                                                            |
| 알 수 없는 원본에서 앱 차단                                                                                                         | 지원되지 않음 | Teams 관리자만 앱 또는 OEM 도구를 설치합니다.                                   |
| 앱 런타임 무결성 회사 포털                                                                                                    | 지원     |                                                                               |
| 제한된 앱                                                                                                                         | 지원되지 않음 |                                                                               |
| 디바이스에서 USB 디버깅 차단                                                                                                           | 지원     |                                                                               |
| [**모든 Android 디바이스*](/mem/intune/protect/compliance-policy-create-android#all-android-devices)                                      | --            | --                                                                            |
| 암호가 필요하기 전까지 최대 비활성 시간(분)                                                                              | 지원되지 않음 |                                                                               |
| 모바일 디바이스의 잠금을 해제하려면 암호 필요                                                                                             | 지원되지 않음 |                                                                               |
| [**Android 10 이상**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later)                                   | --            | --                                                                            |
| [**Android 9 이하 또는 Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | --            | --                                                                            |
| 필수 암호 유형                                                                                                                  | 지원되지 않음 |                                                                               |

---
