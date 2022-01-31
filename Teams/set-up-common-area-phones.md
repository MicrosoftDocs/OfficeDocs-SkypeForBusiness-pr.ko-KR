---
title: 공용 영역 라이선스 전화 설정
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
description: '로비, 수신 공간 및 회의실에 대한 공용 영역 휴대폰을 설정하는 방법에 대해 자세히 알아보기 '
ms.openlocfilehash: a4e4720fe7baf58d0da6f00800c61b706ec48516
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279266"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>공용 영역 휴대폰을 배포합니다Microsoft Teams

일반적인 영역 전화는 일반적으로 로비 또는 전화를 걸 수 있는 다른 영역에 배치됩니다. 예를 들어 수신 영역, 로비 또는 전화 회의 전화가 있습니다. 공용 영역 휴대폰은 공용 영역 라이선스에 묶인 계정으로 전화 있습니다.

이 문서에서는 공유 공간에 대한 공용 Teams 휴대폰으로 휴대폰을 배포하고 구성하는 방법에 대한 개요를 제공합니다. 오디오 회의를 비롯한 보다 완전한 회의실 환경을 위해 회의실 디바이스로 전용 미팅룸 라이선스를 구입하는 것이 고려됩니다.

## <a name="overview"></a>개요

공용 영역 전화 라이선스는 다음을 지원합니다. 


| &nbsp;  |  공용 영역 전화  |
|---------|---------|
|비즈니스용 Skype |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|전화 시스템 |    &#x2714; |
|오디오 회의 |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|전 세계 가용성 |       &#x2718; &sup2;  |
|채널 가용성 |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&sup1; 공통 영역 전화는 모임 이끌이가 제공하는 전화 접속 번호를 통해 오디오 회의에 참가할 수 있습니다.

&sup2; sovereign 클라우드에서 사용할 수 없습니다.  

>[!NOTE]
> 휴대폰의 공용 영역 비즈니스용 Skype 서버 계정은 Microsoft Teams. 이 문서의 단계를 따라 해당 계정을 다시 Teams 필요한 경우 PTSN 연결을 마이그레이션합니다.

## <a name="step-1---buy-the-licenses"></a>1단계 - 라이선스 구매

먼저 CAP(Common Area 전화) 라이선스를 구입하고 인증된 휴대폰이 있는지 확인해야 합니다. 인증된 휴대폰을 검색하고 자세히 알아보시고자 하여 디바이스를 Microsoft Teams[.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)

1. Microsoft 365 관리 센터 **BillingPurchase** >  서비스로 이동합니다. 

2. 범주별 **보기** 섹션이 아직 표시되지 않은 경우 **Microsoft** 에서 구입으로 이동하고 제품 보기 **를 선택합니다**. 그런 다음 **공동 작업 및 통신을 선택합니다**.  

3. 제품 목록에서 공통 **영역 전화 찾아** **세부 정보를 선택합니다**.

4. 필요한 라이선스 수를 입력하고 구매를 **선택합니다**.

>[!NOTE]
>환경에서 Intune을 사용하고 있으며 디바이스 준수가 필요한 조건부 액세스 규칙이 있는 경우 공용 영역 전화의 디바이스 계정에 Azure Active Directory Premium 계획 1 및 Intune 라이선스를 할당해야 합니다.
>
>공용 영역 휴대폰은 조건부 액세스 규칙 및 Multi-Factor Authentication과 같은 기타 ID 구성에 영향을 줄 수 있습니다. 자세한 [내용은 Android Teams 인증](devices/authentication-best-practices-for-android-devices.md) 모범 사례를 참조합니다.

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>2단계 - 새 사용자 계정 만들기 및 라이선스 할당

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터

두 개 이상의 공통 영역 휴대폰을 한 번 배포하는 경우 PowerShell을 사용하여 계정을 만들고 라이선스를 할당하는 [방법에 대해 알아보아야 합니다](#using-powershell).

하나의 디바이스를 배포하는 경우:

1. 이 Microsoft 365 관리 센터 **UserActive** >  **UsersAdd** >  **사용자로 이동합니다**.

2. 이름의 "Main"과 같은 사용자 이름과 두 번째 이름의 "수신"을 입력합니다.

3. "Main Reception"처럼 자동으로 자생하지 않는 경우 표시 이름을 입력합니다.

4. "MainReception" 또는 "Mainlobby" 같은 사용자 이름을 입력합니다.

5. 방지하려면 공용 영역 전화의 암호를 수동으로 설정합니다. 이렇게하려면 자동으로 암호를 만들고 이 사용자에게  처음 로그인할 때 암호를 변경하도록 **요구합니다**.  

    >[!Important]
    > 일반 지역 휴대폰에 대한 암호를 수동으로 설정하는 것이 최종 사용자의 로그인 문제를 방지하는 것이 좋습니다.

6. 디바이스의 사용 위치를 선택하고 공용 영역 전화 라이선스를 계정에 할당합니다. 통화 요금제와 같은 다른 라이선스가 필요한 경우 할당합니다.

>[!NOTE]
> 라이선스를 추가할 필요가 전화 시스템 없습니다. 공용 영역 라이선스에 전화 포함되어 있습니다.
>
>시스템 직접 라우팅 또는 운영자 Microsoft 전화 사용하지 않는 커넥트 계획 라이선스를 추가할 수 있습니다. 라이선스에 대한 자세한 내용은 추가 Microsoft Teams [라이선스를 참조하세요](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>PowerShell 사용

하나 이상의 사용자 계정에 대해 라이선스를 만들고 할당하려는 경우 PowerShell을 사용하세요. 자세한 [Microsoft 365 PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide)을 사용하여 사용자 계정 만들기 및 Microsoft 365 라이선스 [](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide) 할당을 참조하세요.

## <a name="step-3---set-policies-for-common-area-phones"></a>3단계 - 공용 영역 휴대폰에 대한 정책 설정

정책을 사용하여 공용 영역 휴대폰에서 사용자가 사용할 수 있는 기능을 제어할 수 있습니다.

>[!NOTE]
>정책을 할당한 후 휴대폰에서 로그인하고 다시 로그인합니다. 정책 할당이 적용되는 데 최대 1시간이 걸릴 수 있습니다.

### <a name="ip-phone-policies"></a>IP 전화 정책

공용 영역 라이선스가 할당된 계정으로 로그인한 휴대폰은 전화 사용자 환경을 표시합니다.

휴대폰의 기본 인터페이스를 다시 지정하려는 경우 IP 전화 정책을 [만드는 것이 고려됩니다](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps). 예를 들어 공용 영역 전화가 공용 영역에 사용되는 경우 IP 전화 정책을 설정하여 조직의 글로벌 주소록 검색을 제한하고 핫데스크링을 차단합니다. 자세한 [Teams Android](devices/Teams-Android-devices-user-interface.md) 디바이스 사용자 인터페이스 설정 을 참조합니다.

### <a name="calling-policies"></a>통화 정책

통화 정책을 사용하여 일반 지역 전화에서 통화 전달 또는 동시 링을 사용하여 개인 통화를 사용하도록 설정합니다. 자세한 [내용은](teams-calling-policy.md) 전화 통화 및 Teams 참조합니다.

기본적으로 공용 지역 전화에는 통화 공원이 활성화되지 않습니다. 정책을 사용하도록 설정하려면 정책을 만들어야 합니다. 자세한 [내용은 통화 공원을 참조](call-park-and-retrieve.md)하고 Microsoft Teams 검색합니다.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>4단계 - 전화 번호 획득 및 할당

[PSTN](manage-phone-numbers-landing-page.md) 연결 옵션에 따라 전화 번호를 획득하고 할당하는 방법에 대한 자세한 내용은 조직의 전화 번호 관리를 참조하세요.

## <a name="step-5---sign-in"></a>5단계 - 로그인

사용자 계정을 만들고 구성한 후 휴대폰에 로그인할 수 있습니다. 배포하는 휴대폰의 수에 따라 세 가지 로그인 옵션이 있습니다.

- [로컬 로그인](#local-sign-in)
- [다른 장치에서 로그인](#sign-in-from-another-device)
- [관리 센터를 사용하여 Teams 로그인](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>로컬 로그인

사용자 이름 및 암호로 로컬로 로그인하는 경우: 

1. 공용 영역 전화 켜기

2. 이 **디바이스에서 로그인 선택**

3. 디바이스의 로그인 지침을 따르고 있습니다. 로그인하면 휴대폰에 공통 영역 전화 사용자 환경이 표시됩니다.

### <a name="sign-in-from-another-device"></a>다른 장치에서 로그인

코드를 사용하여 다른 장치에서 공용 영역 전화에 로그인할 수도 있습니다. 이 방법으로 로그인하면 휴대폰 자체가 아닌 다른 디바이스에 사용자 이름과 암호를 입력합니다.

1. 먼저 공용 영역 전화에서 로그인 화면에 표시된 코드를 찾아 봐야 합니다.

2. 다른 장치에서 으로 이동합니다 https://www.microsoft.com/devicelogin.

3. 코드를 입력하고 지침에 따라 로그인을 완료합니다.

### <a name="sign-in-using-the-teams-admin-center"></a>관리 센터를 사용하여 Teams 로그인

관리자는 관리자 센터에서 원격으로 프로비전하고 공용 지역 전화에 Teams 수 있습니다. 이 방법은 많은 수의 휴대폰을 한 번 배포할 때 가장 효율적인 로그인 방법입니다. 자세한 [내용은 원격 프로비전](devices/remote-provision-remote-login.md) 및 Teams Android 디바이스에 로그인을 참조합니다.

## <a name="next-steps"></a>다음 단계

이제 조직에 대한 공용 영역 휴대폰을 설정하고 로그인한 후 관리 센터에서 Teams 있습니다. 자세한 [Microsoft Teams 장치 관리를](devices/device-management.md) 참조합니다.

## <a name="related-topics"></a>관련 항목

- [원격 Microsoft Teams 디바이스 업데이트](devices/remote-update.md)
- [디바이스 Microsoft Teams 관리](devices/manage-device-tags.md)
- [Microsoft Teams 상태 모니터링](alerts/device-health-status.md)
