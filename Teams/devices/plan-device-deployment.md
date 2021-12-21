---
title: 휴대폰 디바이스 및 Teams 배포 계획
ms.author: czawideh
author: cazawideh
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
description: 이 문서에서는 조직에서 휴대폰 및 디스플레이를 배포하는 Teams 및 단계를 제공합니다.
ms.openlocfilehash: 2ad9840d6ebd1ac6973027dedf6be294704f5326
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2021
ms.locfileid: "61577802"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>휴대폰 디바이스 및 Teams 배포 계획

휴대폰 디바이스 및 Teams 성공적으로 배포하고 Teams 계획부터 시작합니다. 이 문서에서는 조직에서 이러한 디바이스를 배포하는 작업 및 단계를 설명합니다. 또한 디바이스 사용, 라이선스, 환경, 터치포인트 및 관리와 통합하는 방법에 대한 지침도 제공합니다.

> [!TIP]
> [Microsoft 365 채택](https://adoption.microsoft.com/) 허브는 사용자와 함께 입양 여정을 시작할 수 있는 Microsoft Teams.

## <a name="task-1-what-are-your-deployment-objectives"></a>작업 1: 배포 목표는 무엇입니까?

조직에서 휴대폰 및 Teams 롤아웃 계획은 배포 목표에서 시작합니다. Teams 디바이스는 회의실, 사무실 및 기타 기능 공간에서 하이브리드 작업을 지원합니다. 이러한 디바이스를 사용할 위치와 누구를 결정해야 합니다.

### <a name="objective-identify-your-device-personas"></a>목표: 디바이스 사용자 식별

Teams 및 디스플레이는 다음 두 가지 사용자 중 하나에 맞습니다. 

- 개인 디바이스
- 공유 공간 디바이스

개인 및 공유 디바이스에는 역할과 사용 현황이 다릅니다. 

**개인 디바이스:** 

- 일반적으로 한 사용자에게 할당되어 해당 사용자의 계정으로 로그인하고 서비스에 액세스하기 위해 Teams 기능 라이선스를 사용하도록 설정합니다.
- 개인 디바이스는 사용자 1명당 하나의 디바이스와 일대일 관계를 맺고 있는 것으로 생각하세요.
- 데스크톱 클라이언트와 페어링할 수 Teams Better Together와 같은 기능을 사용할 수 있습니다.
- 헤드셋, 유선 또는 무선에 연결할 수 있습니다.
- 개인 디바이스의 추가 기능으로는 핫 데스크링 및 홈 화면이 포함됩니다. 

**공유 공간 디바이스:**

- 공용 지역 전화 또는 회의실 장치와 같은 특정 기능을 수행하고 서비스에 액세스하려면 전용 계정 및 기능 라이선스가 필요합니다.
- 공유 디바이스는 일대다 관계인 여러 사용자가 공유하는 하나의 디바이스로 생각하세요.
- 회의실, 수신 공간 또는 제조 층과 같은 공유 공간에 배포됩니다. 
- 사용자 인터페이스(UI)는 공용 영역 및 UI와 같은 해당 함수에 전화 UI 또는 회의실 UI는 공유 디바이스의 기능 및 배치에 따라 달라 니다.
- 설정이 변경되지 않도록 보장하거나 계정이 로그인하지 못하도록 구성 및 선택적 경화가 필요합니다. 
- 공유 공간 디바이스의 추가 기능으로는 공용 지역 전화에 대한 검색 및 유휴 시간 제한이 있는 핫 데스크링이 포함됩니다.

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>목표: 필요한 개인 및 공유 공간 디바이스 수

이제 디바이스 사용자 식별을 확인한 후 사용할 인증된 디바이스와 필요한 디바이스 수를 결정해야 합니다. 이 결정을 내릴 수 있도록 다음 질문을 고려합니다. 

- 필요한 개인 디바이스 수와 개인 디바이스는 누구인가요?
- 공유 디바이스가 필요한 방 또는 공간은 몇 개인가요? 모든 공간에 동일한 유형의 디바이스가 있나요? 
- 디바이스가 특정 요구 사항을 충족해야 하나요?
    - 예를 들어 화면 크기, 폼 팩터 및 제조업체 또는 모델이 있나요? 인증된 휴대폰 및 디스플레이 목록은 인증된 Microsoft Teams [를 참조하세요.](teams-ip-phones.md)
-  휴대폰 또는 Teams 디스플레이가 Teams 있나요? 휴대폰에서 지원하는 기능 목록은 Teams 휴대폰을 [](phones-for-teams.md#features-supported-by-teams-phones) 참조하고 Microsoft Teams 디스플레이에서 지원하는 기능 목록을 Teams [표시를 Microsoft Teams 참조하세요.](teams-displays.md#features-supported-by-teams-displays)
- 새 사용자에게 충분한 디바이스가 있나요, 아니면 새 주문 및 배달 프로세스가 있나요?
- 유지 관리 또는 하드웨어 문제의 경우 예비 디바이스를 사용할 수 있나요? 디바이스를 빠르게 교환할 수 있게 하여 사용자 환경의 중단을 방지할 수 있습니다.

## <a name="task-2-what-are-your-licensing-requirements"></a>작업 2: 라이선스 요구 사항은 무엇입니까? 

이제 필요한 디바이스 수를 알 수 있습니다. 다음 단계는 필요한 라이선스 수를 결정하는 것입니다. Teams 및 디스플레이에 액세스하려면 라이선스가 Microsoft Teams Microsoft 365.

공유 및 개인 디바이스에는 다른 라이선스가 필요합니다. 개인 디바이스의 경우 사용자 계정에 할당된 라이선스를 사용할 수 있습니다. 공유 디바이스에는 해당 기능에 대한 라이선스가 필요합니다. 휴대폰 및 디스플레이의 경우 해당 라이선스는 전화 공용 영역 Microsoft Teams 라이선스 및 Microsoft Teams 룸 스탠더드 [라이선스입니다.](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices) [](../set-up-common-area-phones.md#step-1---buy-the-licenses)

자세한 내용은 라이선스 옵션을 비교하고 라이선스 [Microsoft 365 를 참조하세요.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 

## <a name="task-3-what-are-your-dependencies"></a>작업 3: 종속성이란? 

### <a name="objective-plan-your-device-identities"></a>목표: 디바이스 ID 계획

ID를 사용하면 디바이스가 Microsoft 365 액세스할 수 있으며, 디바이스를 조직 내에서 검색, 관리 및 연결하기가 더 쉬워야 합니다. 이 작업을 수행하려면 디바이스 ID를 계획할 때 다음을 고려합니다.

- 사용자 주체 이름 및 해당 형식 및 도메인
- 이름 표시
- 주소 책 검색 가능성
- 개인 및 공유 공간 디바이스 유형
- 그룹 및 사용자 할당 라이선스

### <a name="objective-review-conditional-access-policies"></a>목표: 조건부 액세스 정책 검토

Azure Active Directory 조건부 액세스 정책은 디바이스에 로그인하기 전에 충족해야 하는 추가 요구 사항입니다.

배포를 계획할 때

- 휴대폰 및 디스플레이에 영향을 줄 수 있는 Teams 조건부 액세스 정책을 검토합니다. What [If](/azure/active-directory/conditional-access/what-if-tool) 도구 및 로그인 로그를 사용하여 Azure AD 관리 센터에서 이 작업을 [할 수 있습니다.](/azure/active-directory/reports-monitoring/concept-sign-ins)

- 필요한 경우 새 규칙 계획

- 디바이스 필터와 같은 조건부 액세스 기능을 사용하여 휴대폰 및 디스플레이에 Teams 적용합니다.

>[!NOTE]
>Android 디바이스가 지원하지 않는 몇 가지 조건부 액세스 정책이 있습니다. 지침 및 모범 사례는 Android 디바이스에 대한 인증 모범 사례를 Teams [참조하세요.](authentication-best-practices-for-android-devices.md)

## <a name="task-4-prepare-your-environment"></a>작업 4: 환경 준비

### <a name="objective-plan-network-basics"></a>목표: 네트워크 기본 계획

Teams 전화 디바이스 및 디스플레이는 의도한 Teams 인터넷에 액세스해야 합니다. 네트워크를 배포할 준비가 됐을 때 다음을 고려합니다.

- 네트워크 인프라에 용량이 충분한가요? 스위치 포트, 무선 액세스 지점 및 기타 범위를 고려합니다.
- VLANS 및 DHCP를 사용하는 경우 범위가 그에 따라 크기는 어떻게 하나요?
- 디바이스가 배포된 위치의 네트워크 경로를 평가하고 테스트 Microsoft 365. 
- 지침에 따라 필요한 방화벽 포트 및 url을 Microsoft 365 를 하세요.
- 위치 정확도 및 규정 준수를 위해 E911 요구 사항 및 구성을 검토하고 테스트합니다. 
- 프록시 서버를 사용하지 않도록 방지하고 안정성 및 품질을 위해 미디어 경로를 최적화합니다.

### <a name="objective-physical-considerations"></a>목표: 물리적 고려 사항

휴대폰 및 디스플레이에 Teams 실제 공간을 고려합니다.

주요 측면은 다음과 같습니다.

- **Power:** 충분한 전기 콘센트가 있나요? 디바이스에 외부 전원이 필요한 경우 콘센트에 얼마나 가까이 배치할 수 있나요?
- **디바이스 배치:** 디바이스는 물리적으로 어디에 있나요? 원래 OEM(장비 제조업체)의 책상 스탠드, 벽 마운트 및 기타 액세서리를 검토합니다.
- **보안:** 디바이스가 특정 공간에 잠겨야 하나요?
- **접근성:** 디바이스가 기본 사용자의 접근성 요구 사항을 충족하나요? 배치 위치, 와이어 길이 및 핸드셋 또는 헤드셋 사용성을 고려합니다.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>작업 5: 배포된 디바이스를 어떻게 관리하나요?

Teams 및 디스플레이는 2~Microsoft 365 포털 및 해당 PowerShell 모듈에서 관리됩니다. 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory 관리 센터

Azure AD 관리 센터를 사용하여 관리

- 휴대폰 및 디스플레이에 Teams 모든 ID 관련 작업
- 조건부 액세스 정책 
- 암호 재설정

#### <a name="teams-admin-center"></a>Teams 관리 센터

관리 Teams 관리 센터 사용

- [디바이스 설정에 Teams](../business-voice/manage-devices.md)
- [구성 프로필](device-management.md#use-configuration-profiles-in-teams)
- [디바이스 태그 지정](manage-device-tags.md)
- [원격 로그인 및 로그인](remote-sign-in-and-sign-out.md)
- 통화 분석  
- 펌웨어
- 로그 문제 해결 및 다운로드

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Endpoint Manager 관리 센터(디바이스 관리에 Intune을 사용하는 경우)

관리 Endpoint Manager 관리 센터를 사용하여 다음을 관리합니다. 

- 디바이스 규정 준수 정책
- 등록 제한 사항
- 회사 디바이스 식별자
- 디바이스 필터
