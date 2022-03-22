---
title: 지원되는 조건부 액세스 및 Intune 디바이스 규정 준수 정책에 Microsoft Teams 룸
ms.author: czawideh
author: cazawideh
ms.reviewer: kspiess
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 지원되는 조건부 액세스 및 Intune 디바이스 규정 준수 정책에 대해 Microsoft Teams 룸.
ms.openlocfilehash: f3b115430779324a260232ce45ba125859abdde8
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689186"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>지원되는 조건부 액세스 및 Intune 디바이스 규정 준수 정책에 Microsoft Teams 룸

이 문서에서는 지원되는 조건부 액세스 및 Intune 디바이스 준수 정책을 Microsoft Teams 룸. 모범 사례 및 예제 정책은 조건부 액세스 및 [Intune 규정 준수 모범 사례를 Microsoft Teams 룸](conditional-access-and-compliance-for-devices.md).

> [!NOTE]
> Teams 룸 조건부 액세스 정책을 할당하려는 디바이스에 이미 배포되어야 합니다. 아직 배포하지 않은 Teams 룸 자세한 내용은 회의실 및 공유 디바이스에 Teams 리소스 계정 [](with-office-365.md) 만들기 및 Android에서 Microsoft Teams 룸 배포를 참조하세요.[](../devices/collab-bar-deploy.md)

## <a name="supported-conditional-access-policies"></a>지원되는 조건부 액세스 정책  

다음 목록에는 Android 및 Android에서 지원되는 Teams 룸 Windows 조건부 액세스 정책이 포함됩니다.

| 할당 | Windows | Android |
|------------|---------|---------|
| 사용자 또는 워크로드 ID |지원되는 | 지원되는 |
|클라우드 앱 또는 작업 | 지원되는 <br><br> Teams 룸 전용 모드인 Teams 경우 다음 세 가지 Cloud 앱에 액세스해야 합니다. Office 365 Exchange Online Office 365 SharePoint 온라인 및 Microsoft Teams | 지원되는 <br><br> Teams 룸 전용 모드인 Teams 경우 다음 세 가지 Cloud 앱에 액세스해야 합니다. Office 365 Exchange Online Office 365 SharePoint 온라인 및 Microsoft Teams |
|**조건**| --- | --- |
| 사용자 위험 | 지원되는 | 지원되는 |
| 로그인 위험 | 지원되는 | 지원되는 |
| 디바이스 플랫폼 | 지원되는 | 지원되는 |
| 위치 | 지원되는 | 지원되는 |
|클라이언트 앱 |지원되지 않음| 지원되지 않음 |
|디바이스에 대한 필터 | 지원되는 | 지원되는 |
|**부여**| --- | --- |
| 액세스 차단 | 지원되는 | 지원되는 |
| 액세스 권한 부여 | 지원되는 | 지원되는 | 
| 다단계 인증 필요 | 지원되지 않음 | 지원되지 않음 |
| 디바이스를 규정 준수로 표시해야 합니다. | 지원되는 | 지원되는 |
|하이브리드 Azure AD 조인 디바이스 필요 | 지원되지 않음 | 지원되지 않음 |
|승인된 클라이언트 앱 필요 | 지원되지 않음 | 지원되지 않음 |
| 앱 보호 정책 필요 | 지원되지 않음 |지원되지 않음 |
| 암호 변경 필요 | 지원되지 않음 | 지원되지 않음 |

> [!NOTE]
> 비즈니스용 Skype 온라인이 사용 중지되어 지원되지 않습니다. 비즈니스용 Skype 온라인 클라우드 앱은 디바이스 규정 준수 기반 조건부 액세스 정책에 지원되지 않습니다.

> [!NOTE]
> Microsoft Teams 룸 Windows 규정 준수 권한 부여 제어를 지원하기 위해 다음 요구 사항을 충족해야 합니다.
>
> - Microsoft Teams 룸 4.8.19.0 이상
> - Windows 10 버전 20H2 이상(10.0.19042)

## <a name="supported-device-compliance-policies"></a>지원되는 디바이스 규정 준수 정책 

Microsoft Teams 룸 Windows Teams 룸 디바이스 규정 준수 정책을 지원합니다.

#### <a name="teams-rooms-on-windows"></a>[Teams 룸 Windows](#tab/mtr-w)

다음은 디바이스 규정 준수 설정 및 사용에 대한 권장 사항의 표 Teams 룸.  

|정책 | 가용성 | 참고|
|---------|-------------|-------|
| [**디바이스 상태**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|BitLocker 필요| 지원되는 | 처음에 BitLocker를 사용하도록 설정한 경우만 Teams 룸. |
|디바이스에서 보안 부팅을 사용하도록 설정해야 합니다. |지원되는 |보안 부팅은 보안 Teams 룸. |
|코드 무결성 필요 |지원되는  | 코드 무결성은 이미 Teams 룸. |
| [**디바이스 속성**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|운영 체제 버전(최소, 최대) |지원되지 않음 | Teams 룸 최신 버전으로 자동으로 업데이트하고 Windows 값을 설정하면 OS 업데이트 후 성공적으로 로그인하지 못하게 될 수 있습니다.|
|모바일 디바이스용 OS 버전(최소, 최대) | 지원되지 않습니다. | 해당 없음 |
| 유효한 운영 체제 빌드 | 지원되지 않음 | 해당 없음 |
| [**구성 관리자 규정 준수**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Configuration Manager에서 디바이스 준수 필요 | 지원되는 |  해당 없음 |
| [**시스템 보안**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| 모든 암호 정책 | 지원되지 않음 | 암호 정책은 로컬 Skype 자동으로 로그인하지 못하게 할 수 있습니다. |
| 디바이스에서 데이터 저장소 암호화가 필요합니다. | 지원되는  | 데이터 저장소의 암호화를 처음 사용하도록 설정한 경우만 Teams 룸. |
| 방화벽 | 지원되는 | 방화벽은 이미 방화벽에 대한 요구 사항입니다Teams 룸 |
| TPM(신뢰할 수 있는 플랫폼 모듈) | 지원되는 | TPM(신뢰할 수 있는 플랫폼 모듈)은 이미 신뢰할 수 있는 플랫폼 Teams 룸. |
| 바이러스 백신 | 지원되는 | 바이러스 백신(Windows Defender)은 이미 Teams 룸. |
| 안티스피웨어 | 지원되는 | 안티스피웨어(Windows Defender)는 이미 Teams 룸. |
| Microsoft Defender 맬웨어 방지 | 지원되는 | Microsoft Defender 맬웨어 방지는 이미 보안에 Teams 룸. |
| Microsoft Defender 맬웨어 방지 최소 버전 | 지원되지 않습니다. | Teams 룸 규정 준수 정책을 설정할 필요가 없습니다.|
| Microsoft Defender 맬웨어 방지 보안 인텔리전스
최신 | 지원되는 | Microsoft Defender 맬웨어 방지가 이미 사용자에 대한 요구 사항인지 Teams 룸. |
| 실시간 보호 | 지원되는 | 실시간 보호는 이미 실시간 보호를 위한 Teams 룸. |
| [**엔드포인트용 Microsoft Defender**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| 디바이스가 컴퓨터 위험 점수에 또는 아래에 있을 수 있습니다. | 지원되는 |  해당 없음 |

#### <a name="teams-rooms-on-android"></a>[Teams 룸 Android에서 사용](#tab/mtr-a)

다음은 디바이스 규정 준수 설정 및 사용에 대한 권장 사항의 표 Teams 룸.  

| 정책 | 가용성 | 참고 |
|---------|-------------|-------|
| [**엔드포인트용 Microsoft Defender**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| 디바이스가 컴퓨터 위험 점수에 또는 미만이 되거나 | 지원되지 않음 |  해당 없음 |
| [**디바이스 상태**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| 디바이스 관리자를 사용하여 디바이스 관리 | 지원되지 않습니다. | Teams Android 디바이스가 디바이스로 관리됩니다.
관리자. |
| 루트 디바이스 | 지원되는 |  해당 없음 |
| 디바이스가 디바이스 위협 수준 또는 아래에 있을 수 있습니다. | 지원되지 않음 |  해당 없음 |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play Services가 구성됩니다. | 지원되지 않음 | Google Play는 Android 디바이스에 Teams 없습니다. |
| 최신 보안 공급자 | 지원되지 않음 | Google Play는 Android 디바이스에 Teams 없습니다. |
| 앱에서 위협 검색 | 지원되지 않음 | Google Play는 Android 디바이스에 Teams 없습니다. |
| SafetyNet 디바이스인testation | 지원되지 않음 | Google Play는 Android 디바이스에 Teams 없습니다.|
| [**디바이스 속성**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| 운영 체제 버전(최소, 최대) | 지원되는 |  해당 없음 |
[**시스템 보안**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| 디바이스에서 데이터 저장소 암호화가 필요합니다. |지원되는 |  해당 없음 |
[**디바이스 보안**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| 알 수 없는 원본에서 앱 차단 | 지원되지 않음 | 관리자만 Teams 또는 OEM 도구를 설치합니다. |
| 회사 포털 런타임 무결성을 보장합니다. | 지원되는 |  해당 없음|
| 제한된 앱 | 지원되지 않음 |  해당 없음 |
| 디바이스에서 USB 디버깅 차단 | 지원되는 |  해당 없음|
[**모든 Android 디바이스*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|암호가 필요하기 전에 최대 비활성 시간 | 지원되지 않음 |  해당 없음 |
| 모바일 디바이스 잠금을 해제하려면 암호 필요 | 지원되지 않음 | 해당 없음 |
| [**Android 10 이상**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 이상 또는 삼성 Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|필수 암호 유형 |지원되지 않음 | 해당 없음|

---
