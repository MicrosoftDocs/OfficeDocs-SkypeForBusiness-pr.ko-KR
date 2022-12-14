---
title: Microsoft Teams용 공용 영역 전화 설정
ms.author: danismith
author: DaniEASmith
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
- admindeeplinkMAC
- admindeeplinkTEAMS
description: 로비, 리셉션 공간 및 회의실에 대한 공용 영역 전화를 설정하는 방법을 알아봅니다.
ms.openlocfilehash: 06005f853ac125478ae1fd99dba2d022c5eb0100
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392158"
---
# <a name="set-up-common-area-phones-for-microsoft-teams"></a>Microsoft Teams용 공용 영역 전화 설정

공용 영역 전화는 일반적으로 로비 또는 많은 사람들이 전화를 걸 수 있는 다른 영역(리셉션 공간, 로비 또는 회의 전화)에 배치됩니다. 공용 영역 전화는 **Microsoft Teams 공유 디바이스** 라이선스에 연결된 계정으로 로그인됩니다.

이 문서에서는 공유 공간에 대한 공용 영역 휴대폰으로 Teams 전화 디바이스를 배포하고 구성하는 방법에 대한 개요를 제공합니다. 오디오 회의를 포함하여 보다 완벽한 회의실 환경을 위해 Teams 룸 디바이스를 사용하여 전용 **Teams 룸** 라이선스를 구매하는 것이 좋습니다. Teams 룸 대한 자세한 내용은 [Microsoft Teams 룸 참조하세요](rooms/index.md).

> [!NOTE]
> 비즈니스용 Skype 서버 만든 공용 영역 전화 개체에 대한 계정은 Microsoft Teams로 마이그레이션할 수 없습니다. 이 문서의 단계에 따라 Teams에 대한 해당 계정을 다시 만들고 필요한 경우 PSTN(공용 전환 전화 네트워크) 연결을 마이그레이션합니다.

## <a name="step-1---buy-the-licenses"></a>1단계 - 라이선스 구입

먼저 **Teams 공유 디바이스** 라이선스를 구매하고 인증된 휴대폰이 있는지 확인해야 합니다. 인증된 휴대폰을 검색하고 자세히 알아보려면 [Microsoft Teams 디바이스](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)로 이동하세요.

1. [Microsoft 365 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339) **청구** > **구매 서비스** 로 이동합니다.

2. **범주별 보기** 섹션이 아직 표시되지 않으면 **Microsoft 구매** 로 이동하여 **제품 보기를** 선택합니다. 그런 다음 **공동 작업 및 통신을** 선택합니다.  

3. 제품 목록에서 **Microsoft Teams 공유 디바이스** 를 찾고 **세부 정보를** 선택합니다.

4. 필요한 라이선스 수를 입력하고 **구매** 를 선택합니다.

> [!NOTE]
> 사용자 환경에서 Intune 사용하고 디바이스 준수가 필요한 조건부 액세스 규칙이 있는 경우 **Azure Active Directory Premium 플랜 1** 을 할당하고 공용 영역 전화의 디바이스 계정에 라이선스 **를 Intune** 합니다.
>
> 공용 영역 전화는 조건부 액세스 규칙 및 Multi-Factor Authentication과 같은 기타 ID 구성의 영향을 받을 수 있습니다. 자세한 내용은 [Teams Android 디바이스에 대한 인증 모범 사례를](devices/authentication-best-practices-for-android-devices.md) 참조하세요.

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>2단계 - 새 사용자 계정 만들기 및 라이선스 할당

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터 사용

둘 이상의 공통 영역 휴대폰을 한 번에 배포하는 경우 [PowerShell을 사용하여](#using-powershell) 계정을 만들고 라이선스를 할당하는 방법을 알아봅니다.

하나의 디바이스를 배포하는 경우:

1. [Microsoft 365 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339) **사용자** > **활성 사용자 사용자** > **추가로** 이동합니다.

2. 이름 및 두 번째 이름에 과 같은 `Main` 사용자 이름을 `Reception` 입력합니다.

3. 와 같이 `Main Reception`자동으로 생성되지 않는 경우 표시 이름을 입력합니다.

4. 또는 `Mainlobby`와 같은 `MainReception` 사용자 이름을 입력합니다.

5. 공용 영역 전화의 암호를 수동으로 설정합니다. 암호를 설정하려면 **자동으로 암호 만들기** 를 선택 취소하고 **이 사용자가 처음 로그인할 때 암호를 변경하도록 요구** 합니다.  

    > [!IMPORTANT]
    > 최종 사용자의 로그인 문제를 방지하려면 공용 영역 휴대폰에 대한 암호를 수동으로 설정하는 것이 좋습니다.

6. 디바이스의 사용 위치를 선택하고 **Teams 공유 디바이스** 라이선스를 계정에 할당합니다. 통화 플랜과 같은 다른 라이선스가 필요한 경우 할당합니다.

> [!NOTE]
> 전화 시스템 기능을 사용하여 라이선스를 추가할 필요가 없습니다. **Teams 공유 디바이스** 라이선스에 포함되어 있습니다.
>
> 직접 라우팅 또는 운영자 연결에서 Microsoft 전화 시스템을 사용하지 않는 경우 **통화 플랜** 라이선스를 추가할 수 있습니다. 라이선스에 대한 자세한 내용은 [Microsoft Teams 추가 기능 라이선스를 참조하세요](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>PowerShell 사용

둘 이상의 사용자 계정에 대한 라이선스를 한 번에 만들고 할당하려는 경우 PowerShell을 사용합니다. 자세한 내용은 [PowerShell을 사용하여 Microsoft 365 사용자 계정 만들기 및 PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)을 사용하여 [사용자 계정에 Microsoft 365 라이선스 할당을 참조하세요](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

## <a name="step-3---set-policies-for-common-area-phones"></a>3단계 - 공용 영역 휴대폰에 대한 정책 설정

정책을 사용하여 공용 영역 휴대폰에서 사용자가 사용할 수 있는 기능을 제어합니다.

### <a name="ip-phone-policies"></a>IP 전화 정책

Teams IP Phone 정책은 휴대폰에 로그인하는 계정이 **Teams 공유 디바이스** 라이선스 이외의 라이선스가 있는 경우에만 수정할 수 있습니다.  Microsoft 365 E3 또는 E5 구독 또는 Office 365 Enterprise E1, E3 또는 E5 구독으로 라이선스가 부여된 경우 IP 전화 정책을 수정할 수 있습니다.  공용 영역 전화 계정에서 **Teams 룸** 라이선스를 사용하는 경우 모드만 사용할 `MeetingRoomSignIn` 수 있습니다. `MeetingRoomSignIn` 모드는 가장 일반적인 지역 휴대폰에서 사용할 수 없습니다. 전화 인터페이스에 대해 지원되는 재정의에 대한 자세한 내용은 [Microsoft Teams Android 디바이스 사용자 인터페이스 설정을 참조하세요](/microsoftteams/devices/teams-android-devices-user-interface#override-automatic-user-interface-detection).

Teams IP 전화 정책을 사용하여 [SignInMode 매개 변수](/powershell/module/skype/new-csteamsipphonepolicy#parameters) 를 로 `CommonAreaPhoneSignIn` 설정하여 Teams 전화 장치에서 공통 영역 전화 환경을 사용하도록 설정합니다.

다른 매개 변수를 구성하려면 [IP 전화 정책을](/powershell/module/skype/new-csteamsipphonepolicy) 만드는 것이 좋습니다. 예를 들어 공용 영역에서 공용 영역 전화를 사용하는 경우 IP 전화 정책을 설정하여 조직의 전역 주소록 검색을 제한하고 핫 데스크를 차단합니다. 자세한 내용은 [Teams Android 디바이스 사용자 인터페이스 설정을 참조하세요](/microsoftteams/devices/Teams-Android-devices-user-interface).

### <a name="calling-policies"></a>통화 정책

통화 정책을 사용하여 일반 지역 전화에서 전화 전달 또는 동시 링을 사용하여 개인 통화를 사용하도록 설정합니다. 자세한 내용은 [Teams에서 통화 및 착신 전환 을 참조하세요](teams-calling-policy.md).

기본적으로 통화 대기는 공용 영역 전화에서 사용하도록 설정되지 않습니다. 사용하도록 설정하려면 정책을 만들어야 합니다. 자세한 내용은 [Microsoft Teams에서 통화 대기 및 검색을 참조하세요](call-park-and-retrieve.md).

> [!NOTE]
> 정책을 할당한 후 휴대폰에서 로그아웃하고 다시 로그인합니다. 정책 할당이 적용되는 데 최대 1시간이 걸릴 수 있습니다.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>4단계 - 전화 번호 획득 및 할당

PSTN 연결 옵션 [에 따라 전화 번호를](manage-phone-numbers-landing-page.md) 획득하고 할당하는 방법을 알아보려면 조직의 전화 번호 관리를 참조하세요.

## <a name="step-5---sign-in"></a>5단계 - 로그인

사용자 계정을 만들고 구성하면 휴대폰에 로그인할 수 있습니다. 배포하는 휴대폰 수에 따라 다음 세 가지 로그인 옵션이 있습니다.

- [로컬 로그인](#local-sign-in).
- [다른 디바이스에서 로그인합니다](#sign-in-from-another-device).
- [Teams 관리 센터를 사용하여 로그인합니다](#sign-in-using-the-teams-admin-center).

### <a name="local-sign-in"></a>로컬 로그인

사용자 이름 및 암호를 사용하여 로컬로 로그인하려면 다음을 수행합니다.

1. 공용 영역 전화를 켭니다.
2. **이 디바이스에서 로그인을** 선택합니다.
3. 디바이스의 로그인 지침을 따릅니다. 로그인하면 휴대폰에 공통 영역 전화 사용자 환경이 표시됩니다.

> [!NOTE]
> 통화 앱을 고정 해제하는 사용자 지정 설정 정책을 사용하는 경우 다이얼 패드가 공용 영역 휴대폰에 표시되지 않습니다. Teams 설정 정책에 대한 자세한 내용은 [Microsoft Teams에서 앱 설정 정책 관리를 참조하세요](teams-app-setup-policies.md).

### <a name="sign-in-from-another-device"></a>다른 디바이스에서 로그인

코드를 사용하여 다른 장치에서 공용 영역 휴대폰에 로그인할 수도 있습니다. 이러한 방식으로 로그인하면 휴대폰 자체가 아닌 다른 디바이스에서 사용자 이름과 암호를 입력합니다.

1. 공용 영역 휴대폰에서 로그인 화면에 표시되는 코드를 찾습니다.
2. 다른 디바이스에서 로 [https://www.microsoft.com/devicelogin](https://www.microsoft.com/devicelogin)이동합니다.
3. 코드를 입력하고 지침에 따라 로그인을 완료합니다.

### <a name="sign-in-using-the-teams-admin-center"></a>Teams 관리 센터를 사용하여 로그인

관리자는 [Teams 관리 센터에서](https://go.microsoft.com/fwlink/p/?linkid=2066851) 공용 영역 휴대폰을 원격으로 프로비전하고 로그인할 수 있습니다. 이 방법은 많은 수의 휴대폰을 한 번에 배포할 때 가장 효율적인 로그인 방법입니다. 자세한 내용은 [Teams Android 디바이스에 대한 원격 프로비저닝 및 로그인](devices/remote-provision-remote-login.md) 을 참조하세요.

## <a name="step-6---set-up-advanced-calling-on-common-area-phones-optional"></a>6단계 - 공용 영역 전화에서 고급 통화 설정(선택 사항)

기본적으로 기본 통화 환경은 공용 영역 전화의 홈 화면에 있지만 고급 통화 환경을 켤 수 있습니다.

Teams **공유 디바이스** 라이선스 및 최신 Teams 업데이트(최소 버전: 1449/1.0.94.2022061702)를 사용하는 지원되는 Teams 전화 장치 모델에 다음과 같은 고급 통화 기능을 사용할 수 있습니다.

- [대기를 호출하고 검색합니다](call-park-and-retrieve.md).
- [Exchange Online 플랜 2를 통한 클라우드 기반 음성 메일](set-up-phone-system-voicemail.md).
  - 클라우드 기반 음성 메일을 사용하지 않도록 설정하려면 [PowerShell을 사용하여 음성 메일 사용자 설정을](/powershell/module/skype/set-csonlinevoicemailusersettings) 참조하세요.
- [큐를 호출합니다](create-a-phone-system-call-queue.md).
- [자동 전화 교환](create-a-phone-system-auto-attendant.md).
- [그룹 통화 픽업](call-sharing-and-group-call-pickup.md).
- [전달 규칙](teams-calling-policy.md).

지원되는 Teams 전화 장치 모델에서 이러한 고급 통화 기능을 사용하려면 [Teams 관리 센터 또는 Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851) 공유 디바이스 계정에 로그인한 Teams 전화 장치에서 **고급 통화** 토글을 켤 수 있습니다.

고급 호출 기능을 켜려면 필요한 모든 기능을 지원할 수 있는 하드웨어 모델을 구매해야 합니다.

### <a name="turn-on-advanced-calling-in-teams-admin-center"></a>Teams 관리 센터에서 고급 통화 켜기

1. Microsoft 365 관리자 계정으로 [Teams 관리 센터에](https://admin.teams.microsoft.com/dashboard) 로그인합니다.
1. 왼쪽 메뉴에서 **Teams 디바이스** > **전화** > 이동하여 **구성 프로필 탭을** 선택합니다.
1. 목록에서 공통 영역 휴대폰에 할당된 구성 프로필을 선택합니다.
1. **통화 설정** 섹션에서 **고급 통화** 토글을 찾습니다.
1. 토글을 켭니다.
1. 페이지 아래쪽에서 **저장** 단추를 선택합니다.

### <a name="turn-on-advanced-calling-from-a-teams-phone-device"></a>Teams 전화 장치에서 고급 통화 켜기

1. Teams 전화 장치에 로그인한 후 **설정** > **디바이스 설정** > 관리 **통화****로만** >  이동합니다.
1. **고급 호출** 토글을 찾아서 켭니다.

## <a name="next-steps"></a>다음 단계

이제 조직의 공용 영역 전화를 설정하고 로그인했으므로 Teams 관리 센터에서 관리할 수 있습니다. [자세한 내용은 Microsoft Teams: 디바이스 관리를 참조하세요](devices/device-management.md).

## <a name="related-articles"></a>관련 기사

- [Microsoft Teams 디바이스를 원격으로 업데이트합니다](devices/remote-update.md).
- [Microsoft Teams 디바이스 태그를 관리합니다](devices/manage-device-tags.md).
- [teams 디바이스 상태 모니터링을 Microsoft](alerts/device-health-status.md).
