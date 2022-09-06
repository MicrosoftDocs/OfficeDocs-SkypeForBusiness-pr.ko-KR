---
title: Teams 전화 장치 및 디스플레이에 대한 배포 계획
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: tony.woodruff
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
search.appverid: MET150
description: 이 문서에서는 조직에 Teams 휴대폰 및 디스플레이를 배포하는 작업 및 단계에 대한 개요를 제공합니다.
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.openlocfilehash: fb9b560f56ece49ddae9f15899a118596a31c38f
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606847"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Teams 전화 장치 및 디스플레이에 대한 배포 계획

Teams 전화 장치 및 Teams 디스플레이의 성공적인 배포는 계획부터 시작합니다. 이 문서에서는 조직에서 이러한 디바이스를 배포하는 작업 및 단계를 안내합니다. 또한 디바이스 사용, 라이선스, 사용자 환경, 터치포인트 및 관리와의 통합에 대한 지침을 제공합니다.

> [!TIP]
> [Microsoft 365 채택 허브는 Microsoft](https://adoption.microsoft.com/) Teams를 사용하여 채택 과정을 시작하기에 좋은 장소입니다.

## <a name="task-1-what-are-your-deployment-objectives"></a>작업 1: 배포 목표는 무엇인가요?

조직에서 Teams 휴대폰 및 디스플레이 출시를 계획하는 것은 배포 목표부터 시작합니다. Teams 디바이스는 회의실, 사무실 및 기타 기능 공간에서 하이브리드 작업을 지원합니다. 이러한 디바이스를 사용할 위치와 대상을 결정해야 합니다.

### <a name="objective-identify-your-device-personas"></a>목표: 디바이스 가상 사용자 식별

Teams 휴대폰 및 디스플레이는 다음 두 개의 페르소나 중 하나에 적합합니다. 

- 개인 디바이스
- 공유 공간 디바이스

개인 및 공유 디바이스에는 서로 다른 역할과 용도가 있습니다. 

**개인 디바이스:** 

- 일반적으로 한 사용자에게 할당되고, 해당 사용자의 계정으로 로그인하고, Teams 기능 라이선스를 사용하여 서비스에 액세스할 수 있습니다.
- 개인 디바이스는 한 사용자당 하나의 디바이스와 일대일 관계를 갖는 것으로 간주합니다.
- Teams 데스크톱 클라이언트와 페어링할 수 있으며 Better Together와 같은 기능을 사용할 수 있습니다.
- 헤드셋, 유선 또는 무선에 연결할 수 있음
- 개인 장치의 추가 기능에는 핫 데스크 및 홈 화면이 포함됩니다. 

**공유 공간 디바이스:**

- 공용 영역 전화 또는 회의실 장치와 같은 특정 기능을 수행하고 서비스에 액세스하려면 전용 계정 및 기능 라이선스가 필요합니다.
- 공유 디바이스는 일대다 관계, 즉 많은 사용자가 공유하는 하나의 디바이스를 갖는 것으로 간주합니다.
- 회의실, 리셉션 공간 또는 제조 층과 같은 공유 공간에 배포됩니다. 
- 해당 UI(사용자 인터페이스)는 공용 영역 전화 UI 또는 회의실 UI와 같은 해당 함수에 따라 공유 디바이스의 기능 및 배치에 따라 달라집니다.
- 설정이 변경되지 않도록 하거나 계정이 로그아웃되지 않도록 하려면 구성 및 선택적 강화가 필요합니다. 
- 공유 공간 장치의 추가 기능에는 공용 영역 전화 검색 및 유휴 시간 제한이 있는 핫 데스크가 포함됩니다.

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>목표: 필요한 개인 및 공유 공간 디바이스의 개수는 얼마인가요?

이제 디바이스 페르소나를 식별했으므로 사용할 인증된 디바이스와 필요한 디바이스 수를 결정해야 합니다. 이 결정을 내리는 데 도움이 되도록 다음 질문을 고려하세요. 

- 필요한 개인 디바이스의 수와 개인 디바이스가 있는 사람은 누구인가요?
- 공유 디바이스가 필요한 객실 또는 공간은 몇 개입니까? 모든 공간에 동일한 유형의 디바이스가 있나요? 
- 디바이스가 특정 요구 사항을 충족해야 합니까?
    - 예를 들어 화면 크기, 폼 팩터, 제조업체 또는 모델이 있습니다. 인증된 휴대폰 및 디스플레이 목록은 [Microsoft Teams 인증 디바이스](teams-ip-phones.md)를 참조하세요.
-  Teams 휴대폰 또는 Teams 디스플레이가 필요한가요? Teams 휴대폰에서 지원하는 기능 목록은 [Microsoft Teams용 휴대폰을 참조하세요](phones-for-teams.md#features-supported-by-teams-phones). Teams 디스플레이에서 지원하는 기능 목록은 [Microsoft Teams 디스플레이를 참조하세요](teams-displays.md#features-supported-by-teams-displays).
- 새 사용자를 위한 충분한 디바이스 또는 새 주문 및 배달을 위한 프로세스가 있나요?
- 유지 관리에 사용할 수 있는 예비 디바이스가 있나요? 또는 디바이스에서 하드웨어 문제가 발생하는 경우 디바이스를 교체할 수 있으면 사용자 환경의 중단을 신속하게 방지할 수 있습니다.

## <a name="task-2-what-are-your-licensing-requirements"></a>작업 2: 라이선스 요구 사항은 무엇인가요? 

이제 필요한 디바이스 수를 알 수 있습니다. 다음 단계는 필요한 라이선스 수를 결정하는 것입니다. Teams 휴대폰 및 디스플레이에는 Microsoft Teams 및 Microsoft 365에 액세스하기 위한 라이선스가 필요합니다.

공유 및 개인 디바이스에는 다른 라이선스가 필요합니다. 개인 디바이스의 경우 사용자 계정에 할당된 라이선스를 사용할 수 있습니다. 공유 디바이스에는 해당 기능과 관련된 라이선스가 필요합니다. 휴대폰 및 디스플레이의 경우 해당 라이선스는 [Microsoft Teams용 공용 영역 전화 라이선스](../set-up-common-area-phones.md#step-1---buy-the-licenses) 및 [Microsoft Teams 룸 라이선스](../rooms/rooms-licensing.md)입니다.

자세한 내용과 라이선스 옵션을 비교하려면 [Microsoft 365 라이선스 계획을](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 참조하세요.

## <a name="task-3-what-are-your-dependencies"></a>작업 3: 종속성은 무엇인가요? 

### <a name="objective-plan-your-device-identities"></a>목표: 디바이스 ID 계획

ID를 사용하면 디바이스가 Microsoft 365 서비스에 액세스할 수 있으며, 디바이스를 조직 내에서 더 쉽게 검색, 관리 및 연결할 수 있습니다. 이렇게 하려면 디바이스 ID를 계획할 때 다음을 고려하세요.

- 사용자 계정 이름 및 해당 형식 및 도메인
- 표시 이름
- 주소록 검색 기능
- 개인 및 공유 공간 디바이스 유형
- 그룹 및 사용자 할당 라이선스

### <a name="objective-review-conditional-access-policies"></a>목표: 조건부 액세스 정책 검토

Azure Active Directory 조건부 액세스 정책은 디바이스를 로그인하기 전에 충족해야 하는 추가 요구 사항입니다.

배포를 계획할 때

- Teams 휴대폰 및 디스플레이에 영향을 줄 수 있는 기존 조건부 액세스 정책을 검토합니다. [What If 도구](/azure/active-directory/conditional-access/what-if-tool) 및 로그인 로그를 사용하여 Azure AD 관리 센터에서 이 작업을 수행할 수 [있습니다.](/azure/active-directory/reports-monitoring/concept-sign-ins)

- 필요한 경우 새 규칙 계획

- 디바이스 필터와 같은 조건부 액세스 기능을 사용하여 Teams 휴대폰 및 디스플레이에 규칙을 적용합니다.

>[!NOTE]
>Android 디바이스에서 지원하지 않는 몇 가지 조건부 액세스 정책이 있습니다. 지침 및 모범 사례는 Android 디바이스를 참조하세요. [Teams Android 디바이스에 대한 인증 모범 사례를 참조하세요](authentication-best-practices-for-android-devices.md).

## <a name="task-4-prepare-your-environment"></a>작업 4: 환경 준비

### <a name="objective-plan-network-basics"></a>목표: 네트워크 기본 사항 계획

Teams Phone 장치 및 디스플레이를 사용하려면 인터넷에 액세스하여 Teams에 연결하고 의도한 대로 작동해야 합니다. 네트워크를 배포할 준비를 하려면 다음을 고려하세요.

- 네트워크 인프라에 충분한 용량이 있나요? 스위치 포트, 무선 액세스 지점 및 기타 범위를 고려합니다.
- VLAN 및 DHCP를 사용하는 경우 범위 크기가 적절하게 조정하나요?
- 디바이스가 Microsoft 365에 배포되는 네트워크 경로를 평가하고 테스트합니다. 
- 지침에 따라 Microsoft 365에 필요한 방화벽 포트 및 URL을 엽니다.
- 위치 정확도 및 규정 준수에 대한 E911 요구 사항 및 구성을 검토하고 테스트합니다. 
- 프록시 서버를 사용하지 말고 안정성과 품질을 위해 미디어 경로를 최적화합니다.

### <a name="objective-physical-considerations"></a>목표: 물리적 고려 사항

Teams 휴대폰 및 디스플레이가 사용될 물리적 공간을 고려합니다.

주요 측면은 다음과 같습니다.

- **전원:** 전기 콘센트가 충분한가요? 디바이스에 외부 전원이 필요한 경우 콘센트에 얼마나 가까이 배치할 수 있나요?
- **디바이스 배치:** 디바이스는 물리적으로 어디에 있나요? OEM(원래 장비 제조업체)의 책상 스탠드, 벽걸이 및 기타 액세서리를 검토합니다.
- **보안:** 디바이스를 특정 공간에 잠가야 하나요?
- **접근성:** 디바이스가 기본 사용자의 접근성 요구 사항을 충족하나요? 배치 위치, 와이어 길이 및 핸드셋 또는 헤드셋 유용성을 고려합니다.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>작업 5: 배포된 디바이스를 어떻게 관리하나요?

Teams 휴대폰 및 디스플레이는 2~3개의 Microsoft 365 포털 및 해당 PowerShell 모듈에서 관리됩니다. 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory 관리 Center

Azure AD 관리 센터를 사용하여 관리

- Teams 휴대폰 및 디스플레이에 대한 모든 ID 관련 작업
- 조건부 액세스 정책 
- 암호 재설정

#### <a name="teams-admin-center"></a>Teams 관리 Center

Teams 관리 센터를 사용하여 관리

- [Teams에 대한 디바이스 설정](../business-voice/manage-devices.md)
- [구성 프로필](device-management.md#use-configuration-profiles-in-teams)
- [디바이스 태그 지정](manage-device-tags.md)
- [원격 로그인 및 로그아웃](remote-sign-in-and-sign-out.md)
- 통화 분석  
- 펌웨어
- 로그 문제 해결 및 다운로드

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Endpoint Manager 관리 Center(디바이스 관리에 Intune 사용하는 경우)

Endpoint Manager 관리 센터를 사용하여 다음을 관리합니다. 

- 디바이스 준수 정책
- 등록 제한 사항
- 회사 디바이스 식별자
- 디바이스 필터
