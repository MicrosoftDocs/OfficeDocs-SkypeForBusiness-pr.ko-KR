---
title: 공용 영역 전화 라이선스 설정
ms.author: czawideh
author: cazawideh
manager: serdars
ms.date: 1/28/2022
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: '로비, 리셉션 공간 및 회의실용 공용 영역 전화 설정 방법 알아보기 '
ms.openlocfilehash: a4a0f5a0a0436a1ea8e81cac8c288de483c24896
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705867"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>Microsoft Teams용 공용 영역 전화 배포

공용 영역 전화는 일반적으로 많은 사람들이 전화를 걸 수 있는 로비 또는 다른 영역과 같은 영역에 배치됩니다. 예: 리셉션 공간, 로비 또는 전화 회의 전화. 공용 영역 전화는 공용 영역 전화 라이선스에 연결된 계정으로 로그인됩니다.

이 문서에서는 Teams 휴대폰을 공유 공간에 대한 공용 영역 전화로 배포하고 구성하는 방법에 대한 개요를 제공합니다. 오디오 회의를 비롯한 보다 완벽한 회의실 환경을 위해 회의실 장치로 전용 회의실 라이선스를 구매하는 것이 좋습니다.

## <a name="overview"></a>개요

공용 영역 전화 라이선스는 다음을 지원합니다.

|                                           | 공용 영역 전화                                 |
|-------------------------------------------|---------------------------------------------------|
| **Microsoft Teams**                       | &#x2714;                                          |
| **Teams Phone**  &sup1;                   | &#x2714;                                          |
| **오디오 회의**                    | &#x2718; &sup2;                                   |
| **Microsoft Intune**                      | &#x2714;                                          |
| **Azure Active Directory Premium 플랜 1** | &#x2714;                                          |
| **Exchange Online 플랜 2**                | &#x2714;  &sup3;                                  |
| **전 세계 가용성**                | &#x2714;                                          |
| **채널 가용성**                  | EA, EAS, EES, CSP, 웹 다이렉트, GCC, GCC-High, DoD |

&sup1; 이전에는 전화 시스템으로 알려져 있습니다.

&sup2; 공용 영역 전화는 모임 이끌이가 제공하는 전화 접속 번호를 통해 오디오 회의에 참가할 수 있습니다.  

&sup3; 클라우드 기반 음성 메일 기능만 지원됩니다.

>[!NOTE]
> 비즈니스용 Skype 서버 만든 공용 영역 전화 개체에 대한 계정은 Microsoft Teams로 마이그레이션할 수 없습니다. 이 문서의 단계에 따라 Teams에 대한 해당 계정을 다시 만들고 필요한 경우 PTSN 연결을 마이그레이션합니다.

## <a name="step-1---buy-the-licenses"></a>1단계 - 라이선스 구입

먼저 CAP(공용 영역 전화) 라이선스를 구입하고 인증된 휴대폰이 있는지 확인해야 합니다. 인증된 휴대폰을 검색하고 자세히 알아보려면 [Microsoft Teams 디바이스](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)로 이동하세요.

1. Microsoft 365 관리 센터 **청구** > **구매 서비스** 로 이동합니다. 

2. **범주별 보기** 섹션이 아직 표시되지 않으면 **Microsoft에서 구매** 로 이동하여 **제품 보기를** 선택합니다. 그런 다음 **, 공동 작업 및 통신을** 선택합니다.  

3. 제품 목록에서 **공용 영역 전화를** 찾아 **세부 정보를** 선택합니다.

4. 필요한 라이선스 수를 입력하고 **구입** 을 선택합니다.

>[!NOTE]
>사용자 환경에서 Intune 사용하고 디바이스 준수가 필요한 조건부 액세스 규칙이 있는 경우 Azure Active Directory Premium 플랜 1을 할당하고 공용 영역 전화의 디바이스 계정에 라이선스를 Intune 합니다.
>
>공용 영역 전화는 조건부 액세스 규칙 및 Multi-Factor Authentication과 같은 기타 ID 구성의 영향을 받을 수 있습니다. 자세한 내용은 [Teams Android 디바이스에 대한 인증 모범 사례를](devices/authentication-best-practices-for-android-devices.md) 참조하세요.

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>2단계 - 새 사용자 계정 만들기 및 라이선스 할당

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터 사용

한 번에 둘 이상의 공통 영역 휴대폰을 배포하는 경우 [PowerShell을 사용하여](#using-powershell) 계정을 만들고 라이선스를 할당하는 방법을 알아봅니다.

하나의 디바이스를 배포하는 경우:

1. Microsoft 365 관리 센터 **사용자****활성 사용자** >  > **추가 사용자로** 이동합니다.

2. 이름에 "Main"과 같은 사용자 이름을 입력하고 두 번째 이름의 "수신"을 입력합니다.

3. "기본 수신"처럼 표시 이름을 자동으로 생성하지 않는 경우 표시 이름을 입력합니다.

4. "MainReception" 또는 "Mainlobby"와 같은 사용자 이름을 입력합니다.

5. 공용 영역 전화의 암호를 수동으로 설정합니다. 이렇게 하려면 **자동으로 암호 만들기** 를 선택 취소하고 **이 사용자가 처음 로그인할 때 암호를 변경하도록 요구** 합니다.  

    >[!Important]
    > 일반 영역 전화의 암호를 수동으로 설정하는 것이 최종 사용자의 로그인 문제를 방지하는 것이 좋습니다.

6. 디바이스의 사용 위치를 선택하고 계정에 Common Area Phone 라이선스를 할당합니다. 통화 플랜과 같은 다른 라이선스가 필요한 경우 할당합니다.

>[!NOTE]
> 전화 시스템 라이선스를 추가할 필요가 없습니다. 공용 영역 전화 라이선스에 포함되어 있습니다.
>
>Microsoft Phone 시스템 직접 라우팅 또는 운영자 연결을 사용하지 않는 경우 통화 플랜 라이선스를 추가할 수 있습니다. 라이선스에 대한 자세한 내용은 [Microsoft Teams 추가 기능 라이선스를](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 참조하세요.

### <a name="using-powershell"></a>PowerShell 사용

둘 이상의 사용자 계정에 대한 라이선스를 한 번에 만들고 할당하려는 경우 PowerShell을 사용합니다. 자세한 내용은 [PowerShell을 사용하여 Microsoft 365 사용자 계정 만들기](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) 및 [PowerShell을 사용하여 사용자 계정에 Microsoft 365 라이선스 할당](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) 을 참조하세요.

## <a name="step-3---set-policies-for-common-area-phones"></a>3단계 - 공용 영역 전화 정책 설정

정책을 사용하여 일반 지역 전화에서 사용자가 사용할 수 있는 기능을 제어합니다.

>[!NOTE]
>정책을 할당한 후 휴대폰에서 로그아웃하고 다시 로그인합니다. 정책 할당이 적용되는 데 최대 1시간이 걸릴 수 있습니다.

### <a name="ip-phone-policies"></a>IP 전화 정책

공용 영역 전화 라이선스가 할당된 계정으로 로그인한 전화는 공통 영역 사용자 환경을 표시합니다.

휴대폰의 기본 인터페이스를 재정의하려면 [IP 전화 정책을](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps&preserve-view=true) 만드는 것이 좋습니다. 예를 들어 공용 영역에서 공용 영역 전화기를 사용하는 경우 IP 전화 정책을 설정하여 조직의 전체 주소록 검색을 제한하고 핫 데스크를 차단합니다. 자세한 내용은 [Teams Android 디바이스 사용자 인터페이스 설정을](devices/Teams-Android-devices-user-interface.md) 참조하세요.

### <a name="calling-policies"></a>통화 정책

통화 정책을 사용하여 일반 지역 전화에서 통화 전달 또는 동시 링을 사용하여 개인 통화를 사용하도록 설정합니다. 자세한 내용은 [Teams에서 통화 및 착신 전환(call-forwarding](teams-calling-policy.md) )을 참조하세요.

기본적으로 통화 대기는 일반 지역 전화에서 사용하도록 설정되지 않습니다. 사용하도록 설정하려면 정책을 만들어야 합니다. 자세한 내용은 [통화 대기 및 Microsoft Teams에서 검색](call-park-and-retrieve.md) 을 참조하세요.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>4단계 - 전화 번호 획득 및 할당

PSTN 연결 옵션 [에 따라 전화 번호를](manage-phone-numbers-landing-page.md) 획득하고 할당하는 방법을 알아보려면 조직의 전화 번호 관리를 참조하세요.

## <a name="step-5---sign-in"></a>5단계 - 로그인

사용자 계정을 만들고 구성한 후에는 휴대폰에 로그인할 수 있습니다. 배포하는 휴대폰 수에 따라 다음 세 가지 로그인 옵션이 있습니다.

- [로컬 로그인](#local-sign-in)
- [다른 디바이스에서 로그인](#sign-in-from-another-device)
- [Teams 관리 센터를 사용하여 로그인](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>로컬 로그인

사용자 이름 및 암호를 사용하여 로컬로 로그인하려면 다음을 수행합니다. 

1. 공용 영역 전화 켜기

2. **이 디바이스에서 로그인** 선택

3. 디바이스의 로그인 지침을 따릅니다. 로그인하면 휴대폰에 공통 영역 전화 사용자 환경이 표시됩니다.

> [!NOTE]
> 통화 앱을 고정 해제하는 사용자 지정 설정 정책을 사용하는 경우 다이얼 패드가 공용 영역 전화에 표시되지 않습니다. Teams 설정 정책에 대한 자세한 내용은 [Microsoft Teams에서 앱 설정 정책 관리를 참조하세요](/microsoftteams/teams-app-setup-policies).

### <a name="sign-in-from-another-device"></a>다른 디바이스에서 로그인

코드를 사용하여 다른 장치에서 공용 영역 전화기에 로그인할 수도 있습니다. 이러한 방식으로 로그인하면 휴대폰 자체가 아닌 다른 디바이스에서 사용자 이름과 암호를 입력합니다.

1. 먼저 공용 영역 전화에서 로그인 화면에 표시되는 코드를 찾습니다.

2. 다른 디바이스에서 .로 https://www.microsoft.com/devicelogin이동합니다.

3. 코드를 입력하고 지침에 따라 로그인을 완료합니다.

### <a name="sign-in-using-the-teams-admin-center"></a>Teams 관리 센터를 사용하여 로그인

관리자는 Teams 관리 센터에서 공용 영역 전화기를 원격으로 프로비전하고 로그인할 수 있습니다. 많은 수의 휴대폰을 한 번에 배포할 때 가장 효율적인 로그인 방법입니다. 자세한 내용은 [Teams Android 디바이스에 대한 원격 프로비저닝 및 로그인](devices/remote-provision-remote-login.md) 을 참조하세요.

## <a name="next-steps"></a>다음 단계

이제 조직의 공용 영역 전화를 설정하고 로그인했으므로 Teams 관리 센터에서 관리할 수 있습니다. [자세한 내용은 Microsoft Teams: 디바이스 관리를 참조하세요](devices/device-management.md).

## <a name="related-topics"></a>관련 주제

- [원격으로 Microsoft Teams 디바이스 업데이트](devices/remote-update.md)
- [Microsoft Teams 디바이스 태그 관리](devices/manage-device-tags.md)
- [Microsoft Teams 디바이스 상태 모니터링](alerts/device-health-status.md)
