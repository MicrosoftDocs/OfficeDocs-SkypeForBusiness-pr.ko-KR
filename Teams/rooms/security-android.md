---
title: Android용 Microsoft Teams 보안
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Android용 Microsoft Teams 디바이스를 보호하는 방법을 알아봅니다.
ms.openlocfilehash: 6d17cc68af8ef4a879d5de3b17d27f20b281ddf8
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532438"
---
# <a name="microsoft-teams-for-android-security"></a>Android용 Microsoft Teams 보안

이 문서에서는 Microsoft Endpoint Manager 전용 디바이스 모드로 구성된 Android 디바이스에 대해서는 다루지 않습니다. Teams Android 디바이스는 키오스크 모드에서 의도적으로 실행됩니다. Android 키오스크에 대한 자세한 내용은 [Android Enterprise 전용 디바이스 등록](/mem/intune/enrollment/android-kiosk-enroll)을 참조하세요.

Microsoft는 OEM 파트너와 협력하여 설계에 따라 안전하고 고객의 요구에 맞게 사용자 지정할 수 있는 솔루션을 제공합니다. 이 문서에서는 Teams Android 디바이스에 있는 많은 보안 기능과 접근 방식에 대해 설명합니다. 탐색의 용이성을 위해 네 개의 주요 섹션으로 분할됩니다.

> [!NOTE]
> Microsoft Teams Android 디바이스는 일반적인 Android 디바이스로 취급해서는 안 됩니다. Teams Android 디바이스는 Teams 및 해당 사용 사례와 함께 사용하도록 설계된 용도로 작성된 어플라이언스입니다. 이 문서는 Android 운영 체제를 실행하는 인증된 전용 Microsoft Teams 디바이스에만 적용됩니다. Teams 인증 디바이스는 인증된 OEM 공급업체에서만 구매할 수 있습니다. Microsoft Teams 인증 Android 디바이스에 대한 자세한 내용은 [Microsoft Teams 인증 Android 디바이스를 참조하세요](/microsoftteams/devices/teams-ip-phones).

Windows 디바이스의 Teams 룸 보안에 대한 자세한 내용은 [Windows 보안에 대한 Microsoft Teams 룸](security-windows.md) 참조하세요.

## <a name="software-security"></a>소프트웨어 보안

### <a name="android-kiosk-mode"></a>Android 키오스크 모드

Teams Android 디바이스는 Android 키오스크 모드에서 디바이스를 실행하여 승인된 애플리케이션만 실행하도록 잠겨 있습니다. 키오스크 모드는 모든 시작 관리자 기능에 대한 액세스를 사용하지 않도록 설정하고 디바이스에서 권한 있는 애플리케이션이 시작되도록 디바이스를 보호하는 데 도움이 됩니다.  

| 애플리케이션 이름            | 애플리케이션 설명                   |
|-----------------------------|-------------------------------------------|
| Microsoft Teams Android 앱 | Microsoft Teams 디바이스 애플리케이션        |
| Microsoft Teams 관리 에이전트 | Teams 관리 센터 원격 관리      |
| Intune 회사 포털       | 디바이스 등록, 등록 & 로그인 |
| OEM 파트너 에이전트           | OEM 파트너 에이전트 & 디바이스 설정 앱   |

기본적으로 Microsoft Teams Android 앱은 Android 키오스크 모드에서 시작되며 지정된 Teams 사용자 환경 이외의 구성 요소에 대한 액세스 또는 운영 체제에 대한 액세스 권한을 사용자에게 제공하지 않습니다.

### <a name="application-code-signing"></a>애플리케이션 코드 서명

모든 Microsoft 및 OEM 애플리케이션은 코드 서명입니다. 코드 서명은 디바이스에서 실행되는 소프트웨어가 Microsoft 및 하드웨어 파트너의 정품인지 확인하는 데 도움이 됩니다. 또한 코드 서명은 디바이스에서 실행되는 소프트웨어의 무결성을 확인하여 정품 소프트웨어만 시작하고 실행할 수 있도록 합니다.  

### <a name="third-party-applications"></a>타사 애플리케이션

Teams 인증 장치에는 Google Play 스토어, Amazon App Store 또는 Google Play 서비스가 설계에 따라 설치되어 있지 않습니다. 이렇게 하면 스토어에서 디바이스로 타사 애플리케이션을 설치할 수 없습니다.  

### <a name="android-debug-bridge"></a>Android 디버그 브리지

릴리스 소프트웨어를 실행하는 모든 Teams Android 디바이스에서 의도적으로 ADB(Android 디버그 브리지)를 사용할 수 없습니다. ADB는 관리자가 Android 기반 디바이스에서 함수를 수행하고 앱 설치, 디바이스 셸에 대한 액세스 및 기타 관리 함수를 사용하도록 설정하는 명령줄 도구입니다.  

### <a name="file-system-encryption"></a>파일 시스템 암호화

Teams Android 디바이스는 Android 기반 암호화를 지원해야 하며 Microsoft Endpoint Manager 규정 준수 정책을 사용하여 적용할 수 있습니다. Endpoint Manager 준수 정책에 대한 자세한 내용은 [Endpoint Manager 준수 정책을 사용하여 Intune 사용하여 관리하는 디바이스에 대한 규칙을 설정합니다](/mem/intune/protect/device-compliance-get-started).

### <a name="android-os-version"></a>Android OS 버전

Teams Android 디바이스는 지원되는 버전의 Android를 실행합니다. Android 운영 체제는 OEM 파트너에 의해 관리되고 Teams 인증 펌웨어에 병합된 다음 Teams 관리 센터에서 디바이스로 푸시됩니다. Teams Android 디바이스에서 실행 중인 Android 버전에 대한 자세한 내용은 [Microsoft Teams 인증 Android 디바이스를 참조하세요](/microsoftteams/devices/teams-ip-phones).

### <a name="android-security-updates"></a>Android 보안 업데이트

OEM 공급업체는 펌웨어 업데이트 프로세스의 일부로 적절한 Android 보안 업데이트 기준을 통합하여 기본 운영 체제가 안전하게 유지되도록 합니다. 디바이스를 정기적으로 업데이트하는 것은 디바이스에서 적절한 Android 보안 업데이트가 실행되도록 하는 데 중요합니다. 자세한 내용은 디바이스 제조업체를 참조하세요.

### <a name="account-security"></a>계정 보안

Teams Android 디바이스는 디바이스의 성공적인 작동을 가능하게 하는 두 가지 유형의 계정을 중심으로 빌드됩니다.

- 로컬 디바이스 관리자 계정

- 사용자 또는 리소스 계정  

Teams Android 디바이스는 디바이스 로그인을 위한 추가 보안 계층으로 사용할 수 있는 일부 조건부 액세스 정책과도 호환됩니다. 모범 사례 및 지원되는 조건부 액세스 정책은 [지원되는 조건부 액세스 준수 정책을 참조하세요](/microsoftteams/rooms/supported-ca-and-compliance-policies).

### <a name="local-device-administrator-account"></a>로컬 디바이스 관리자 계정

Teams Android 디바이스에는 디바이스 설정에 액세스하기 위한 관리 계정, 로컬 웹 서버(설치된 경우) 및 OEM 특정 설정이 포함됩니다.

이 계정의 기본 사용자 이름 및 암호와 같은 초기 디바이스 설정 및 구성 항목은 디바이스 제조업체에서 가져올 수 있습니다.

> [!CAUTION]
> 가능한 한 빨리 로컬 디바이스 관리자 암호를 변경해야 합니다.  

> [!TIP]
> Teams 관리 센터를 사용하여 구성 프로필을 적용하여 로그인한 Teams Android 디바이스의 로컬 디바이스 관리자 암호를 변경할 수 있습니다. Android 디바이스의 상승된 기능을 보호하려면 초기 디바이스 로그인 후 이 방법을 사용하는 것이 좋습니다. 관리자 권한 기능은 지원되는 경우 디바이스 설정 및 웹 관리 포털을 포함할 수 있습니다.

### <a name="user-or-resource-account"></a>사용자 또는 리소스 계정

Teams Android 디바이스를 사용하려면 사용자 또는 전용 리소스 계정을 사용하여 Microsoft 365에 로그인해야 합니다. 개인 디바이스의 일반 사용자 계정인지 또는 공유 디바이스의 리소스 계정인지에 따라 특정 방식으로 이러한 계정을 보호하려고 합니다. 자세한 내용은 [회의실 및 공유 디바이스에 대한 리소스 계정 만들기 및 구성을 참조하세요](/microsoftteams/rooms/with-office-365).

### <a name="device-updates"></a>디바이스 업데이트

Teams Android 디바이스는 사용할 수 있게 되면 Teams 관리 센터에서 Microsoft 인증 업데이트를 다운로드하도록 구성됩니다. 관리자가 자동으로 또는 수동으로 호출할 수 있습니다. 필요한 경우 OEM 파트너의 타사 도구를 사용하여 이 함수를 수행할 수도 있습니다. Teams Android 디바이스는 사용자에게 영향을 주지 않도록 몇 시간 후에 업데이트를 설치할 수 있습니다. 시간 후 일정을 Teams 관리 센터에서 구성하거나 OEM 파트너의 타사 도구를 사용할 수 있습니다.

> [!IMPORTANT]
> Microsoft는 Teams 관리 센터를 통해 모든 Teams Android 디바이스에 대한 펌웨어 관리를 수행하는 것이 좋습니다.

## <a name="network-security"></a>네트워크 보안

Teams Android 디바이스에는 방화벽 및 기타 보안 디바이스를 통한 액세스를 포함하여 Microsoft Teams 클라이언트와 동일한 네트워크 요구 사항이 있습니다. 특히 Teams에 **필요한** 범주는 아래 나열된 다른 지원 서비스와 함께 방화벽에서 열려 있어야 합니다. Teams Android 디바이스에 필요한 IP 및 URL의 전체 목록은 다음을 참조하세요.

- Microsoft Teams, Exchange Online, SharePoint Online, Microsoft 365 Common 및 Office Online [Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- Microsoft Intune [대한 네트워크 엔드포인트 Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Teams Android 디바이스는 대부분의 802.1X 및 기타 네트워크 기반 보안 프로토콜에서 작동합니다. 그러나 모든 네트워크 보안 구성에 대해 Teams Android 디바이스를 테스트할 수는 없습니다. 따라서 네트워크 성능 문제로 추적할 수 있는 성능 문제가 발생하는 경우 조직에서 구성된 경우 이러한 프로토콜을 사용하지 않도록 설정하거나 OEM 파트너에게 도움을 요청해야 할 수 있습니다.

실시간 미디어의 최적의 성능을 위해 프록시 서버 및 기타 네트워크 보안 디바이스를 우회하도록 Teams 미디어 트래픽을 구성하는 것이 좋습니다. 실시간 미디어는 프록시 서버 및 기타 네트워크 보안 디바이스로 인해 발생할 수 있는 네트워크 대기 시간에 민감합니다. 네트워크 대기 시간은 사용자의 비디오 및 오디오 품질을 크게 저하시킬 수 있습니다. 자세한 내용은 Microsoft Teams를 사용하여 미디어 성능을 개선하기 위한 네트워크 권장 사항을 설명하는 [한 설계자의 관점인 클라우드에 대한 네트워킹](/microsoft-365/solutions/networking-design-principles) 을 참조하세요.

Teams Android 디바이스는 인터넷에서 암호화된 통신 및 엔드포인트 인증을 사용합니다. Teams Android 디바이스는 TLS 1.2 이상을 사용합니다.  

> [!IMPORTANT]
> Teams Android 디바이스는 인증된 프록시 서버 또는 테넌트 제한을 지원하지 않습니다. 프록시 지원 정보는 OEM 파트너에게 문의하세요.

Teams Android 디바이스는 내부 LAN에 연결할 필요가 없습니다. 직접 인터넷에 액세스할 수 있는 보안 네트워크 세그먼트에 Teams Android 디바이스를 배치하는 것이 좋습니다. 예를 들어 Teams 휴대폰을 음성 VLAN에 배포할 수 있습니다. 내부 LAN이 손상되면 이 네트워크 분리를 구현하여 Teams Android 디바이스에 대한 공격 벡터 기회가 줄어듭니다.

Teams Android 디바이스를 유선 네트워크에 연결하는 것이 좋습니다. 무선 네트워크를 사용하려면 최상의 환경을 위해 신중한 계획과 평가가 필요합니다.

근접 조인, Better Together, Teams 캐스트 및 Teams 패널 페어링은 Bluetooth에 의존합니다. Android 디바이스용 Teams 룸 Bluetooth 기술 사용은 현재 광고 비콘 및 프롬프트 프록시 연결로 제한됩니다. `ADV_NONCONN_INT` PDU(프로토콜 데이터 단위) 형식은 광고 비콘에 사용됩니다. 이 PDU 유형은 수신 대기 디바이스에 정보를 보급하는 연결할 수 없는 디바이스용입니다. 이러한 기능의 일부로 Bluetooth 디바이스 페어링이 없습니다. Bluetooth 프로토콜에 대한 자세한 내용은 Bluetooth SIG 웹 사이트에서 확인할 수 있습니다.

Teams 휴대폰 및 디스플레이는 Bluetooth Hands-Free 프로필을 사용하여 헤드셋과 페어링하는 Bluetooth 페어링 기능을 제공합니다.

Microsoft Teams의 보안에 대한 자세한 내용은 [보안 및 Microsoft Teams](/microsoftteams/teams-security-guide)를 참조하세요.  
