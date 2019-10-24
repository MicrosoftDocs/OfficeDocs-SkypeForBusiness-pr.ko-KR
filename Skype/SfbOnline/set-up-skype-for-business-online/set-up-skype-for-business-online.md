---
title: 비즈니스용 Skype Online 설정
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.custom:
- Setup
- Alchemy
- LIL_Placement
description: '비즈니스용 Skype를 설치 하도록 조직의 도메인, 사용자, IM, 현재 상태를 설정 하는 방법을 알아봅니다. 오디오 회의, 전화 시스템 및 통화 요금제 및 Skype 모임 브로드캐스트를 설정 하는 방법도 알아봅니다. '
ms.openlocfilehash: 239e1c39563594ffe1ff106284bbbf912367fb88
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "37642149"
---
# <a name="set-up-skype-for-business-online"></a>비즈니스용 Skype Online 설정

비즈니스용 Skype를 설정 하려면 Office 365 전역 관리자 권한이 있어야 합니다. 웹의 일부분에 대 한 액세스를 제한 하는 방화벽 또는 프록시 서버가 있는 경우 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089) 를 고용 하 여 비즈니스용 Skype를 설정 하는 것이 좋습니다.

## <a name="setting-up-skype"></a>Skype 설정

Office 365 구독으로 Skype를 설정 하는 데 도움이 필요한 것 같습니다. 이 문서에 나와 있는 단계를 따라 설치를 완료할 수 있습니다.

## <a name="1-plan-for-skype-for-business"></a>1. 비즈니스용 Skype 계획

**[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** 또는 **Business Essentials**가 있는 경우 비즈니스용 Skype를 사용 하 여 구독 중인 비즈니스의 다른 사용자에 게 온라인으로 전화를 걸 수 있습니다. 예를 들어 비즈니스에 10 명의 사용자가 있는 경우 [IM 및 온라인 모임에 비즈니스용 skype를 사용 하](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) 고, 아래에서 2-6 단계를 수행한 후 비즈니스용 skype를 사용 하 여 비즈니스용 Skype [로 모임을](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) 시작할 수 있습니다. Outlook에서 온라인 모임으로도 [비즈니스용 Skype 모임을 설정할](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) 수 있습니다.

비즈니스용 Skype를 사용 하 여 회사 *외부* 의 사용자에 게 **전화를 걸고** 수신 하려면 다음을 수행 합니다.

- **옵션 1. 무료 [Skype 앱](https://www.skype.com/)을 사용**하세요. 소규모 기업 (예: 1-2 사람)이 있는 경우 Skype 앱을 사용 하는 것이 더 나은 방법입니다. 국내 및 국제 전화에 사용 하는 것은 저렴 합니다. 계속 해 서 컨퍼런스 통화를 개최 하 고 영상 통화를 하 고 데스크톱을 공유할 수 있습니다. [요금 및 결제 옵션을 확인](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)하세요.

- **옵션 2. 요금제를 업그레이드 하 고 Office 365에 대 한 전화 시스템 및 통화 요금제를 구입**합니다. 이 비용을 확인 하 고 전환 하는 가장 쉬운 방법은 [비즈니스 제품에 대 한 지원 팀에 문의](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 하 여 관리자의 도움을 요청 하 고 모든 작업을 수행 하는 것입니다.

자세히 알아보려면 [비즈니스용 Office 365의 설정 계획](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)을 참조 하세요.

## <a name="2-sign-in-to-office-365"></a>2. Office 365에 로그인 합니다.
<a name="bkmk_signin"> </a>

비즈니스용 Skype Online은 Office 365 서비스 제품군의 일부입니다. 비즈니스용 Skype Online을 설정 하려면 Office 365에 로그인 해야 합니다. 이 작업을 수행 하는 방법은 다음과 같습니다.

1. Office 365 사용자 ID (예: <em>rob@fourthcoffee.com</em> )를 찾습니다. 비즈니스용 Skype Online을 구매할 때 만든 Office 365 사용자 ID가 포함 된 Microsoft Online Services 팀에서 전자 메일을 받았습니다. 메일의 모양은 다음과 같습니다.

    ![비즈니스용 Skype Online에 등록 한 후 받은 환영 전자 메일의 예입니다. 여기에는 Office 365 사용자 id가 포함 되어 있습니다.](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. 관리 센터에 로그인 하 고 Office 365 사용자 ID 및 암호를 입력 합니다. 로그인 하면 Microsoft 365 관리 센터가 표시 됩니다.

    ![비즈니스용 Skype Online 요금제를 사용 하는 경우 관리 센터의 모양을 보여 주는 예입니다.](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)

## <a name="3-set-up-your-domain-and-users"></a>3. 도메인 및 사용자 설정
<a name="bkmk_users"> </a>

Office 365에 로그인 한 후에는 비즈니스용 Skype Online을 사용 하도록 도메인 및 조직 구성원을 설정할 수 있습니다.

1. Office [365에 도메인 및 사용자 추가](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): office 365 설정 마법사를 사용 하 여 office 365을 사용 하 여 사용자 지정 도메인 (예: *fourthcoffee.com*)을 설정 합니다. **기본적으로 Office 365 설치 마법사에는 비즈니스용 Skype Online 설정 및 비즈니스용 Skype 사용자 Id 만들기가 포함 되어 있습니다.** 이미 마법사를 사용 하 여 Office 365에 대 한 도메인을 설정한 경우에는이 단계를 완료 합니다.

2. 도메인 및 dns [연결](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): 도구-도메인 문제 해결사를 사용 하 여 도메인 및 dns 설정이 올바른지 확인 합니다. 이 작업을 수행 하면 나중에 DNS 설정을 향후 문제의 원본으로 제거할 수 있기 때문에 모든 설치 문제를 파악 하는 데 도움이 됩니다.

3. [Office 365 url 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): 대부분의 small 기업은이 단계를 수행할 필요가 없습니다. **그러나 웹의 일부에 대 한 액세스를 제한 하는 방화벽 또는 프록시 서버가 있는 경우**비즈니스용 Skype Online 끝점에 대 한 액세스를 허용 하는 규칙을 만들어야 합니다. 이는 방화벽과 프록시 서버를 구성 하는 데 경험이 많은 사용자가 수행 하는 고급 단계입니다. 이전에이 작업을 수행 하지 않은 경우에는 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089) 를 고용 하 여 비즈니스용 Skype를 설정 하는 것이 좋습니다.

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. 조직에서 메신저 대화 및 현재 상태 설정
<a name="bkmk_IM"> </a>

인스턴트 메시지 (IM) 및 현재 상태 (비즈니스용[skype의 현재 상태 정보에 대 한 액세스 제어](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c))는 비즈니스용 skype에 포함 된 기본 기능입니다. 기본적으로 비즈니스 사용자는 서로 Skype와 인스턴트 메시지를 공유할 수 있습니다.

1. **비즈니스용 Skype 사용자가 통신할 수 있는 사람을 선택 합니다.**

   - [사용자가 외부 비즈니스용 Skype 사용자에 게 연락할 수 있도록 허용](allow-users-to-contact-external-skype-for-business-users.md) 귀하 *와* 다른 기업 모두에서 시스템을 구성 해야 합니다.

     **중요**: 비즈니스에 rob@contosowest.com 및 ina@contosoeast.com와 같은 두 개의 도메인이 있는 경우이 단계를 수행 해야 모든 사용자가 서로 통신할 수 있습니다.

   - [비즈니스용 skype 사용자가 회사 외부의 skype 연락처를 추가 하도록 허용](let-skype-for-business-users-add-skype-contacts.md)

2. **동료가 온라인 상태 인지를 볼 수 있는 사람을 선택 합니다.** 현재 상태 기능에는 온라인 상태와 사용 가능한 시간 (예: 약속 있음/없음, 자리 비움, 프레젠테이션)이 표시 됩니다.

    ![개인 메시지를 사용 하 여 사용자의 온라인 상태에 대 한 예입니다.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    비즈니스의 모든 사용자에 대 한 기본 설정을 선택할 수 있습니다.

   - 사용자의 온라인 상태를 조직의 모든 사용자에 게 자동으로 표시

   - 사용자의 온라인 상태를 자신의 연락처에만 표시

지침은 [비즈니스용 Skype Online에서 현재 상태 구성을](configure-presence-in-skype-for-business-online.md)참조 하세요.

## <a name="5-download-and-install-skype-for-business"></a>5. 비즈니스용 Skype 다운로드 및 설치
<a name="bkmk_download"> </a>

PC, Mac 또는 모바일 장치에서 비즈니스용 Skype를 사용 하려면 사용자와 비즈니스의 다른 사람들이 먼저 장치에 비즈니스용 Skype 다운로드를 설치 해야 합니다.

- [비즈니스용 Skype 설치](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Office 365 포털에서 앱을 다운로드 하 고 PC 또는 Mac에 설치 하는 방법에 대 한 지침입니다.

- [Office 365에서 비즈니스용 Skype 클라이언트 배포](deploy-the-skype-for-business-client-in-office-365.md)대규모 엔터프라이즈에서 앱을 배포 하는 방법에 대 한 지침입니다.

- 비즈니스용 [Skype 설치](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Android 장치, iOS 장치, Windows phone에서 비즈니스용 skype를 다운로드 하 고 설치 하 고 로그인 합니다.

- [휴대폰 전화 알림 설정 또는 해제](turn-on-or-off-mobile-phone-notifications.md): 모바일 장치에 비즈니스용 Skype가 설치 되어 있는 경우 사용자와 회사의 다른 사용자가 수신 및 부재 중 메신저 대화에 대 한 알림을 받을 수 있습니다.

## <a name="6-test-to-make-sure-everything-is-working"></a>6. 모든 작업이 제대로 수행 되는지 테스트
<a name="bkmk_test"> </a>

먼저 사용자와 비즈니스의 다른 사용자가 비디오를 사용할 수 있는지 여부를 테스트 하세요. [비즈니스용 Skype에 로그인 및 로그 아웃](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451) 서로 메신저 대화를 보내고 상대방의 현재 상태를 보고 빠른 모임에 참가할 수 있는지 확인 하세요.

문제? 이렇게 하려면 다음을 수행합니다.

- [비즈니스용 Skype에 로그인 하는 데 도움이 필요 하세요?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) 일반적인 로그인 문제

- [비즈니스 제품에 대 한 고객 지원 문의-관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 저희에 게 도움을 주세요!

## <a name="do-you-want-to-set-up-other-available-features"></a>다른 사용 가능한 기능을 설정 하 시겠습니까?
<a name="bkmk_more"> </a>

추가 기능을 설정 하기 전에 라이선스가 있는지 확인 합니다. [비즈니스용 Skype 및 Microsoft 팀 추가 기능 라이선스](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a>오디오 회의 설정

조직의 사용자가 모임에 전화를 걸 때 휴대폰을 사용 해야 하는 경우가 있습니다. 비즈니스용 Skype에는 이러한 상황에 대 한 오디오 회의 기능이 포함 되어 있습니다. 모바일 장치 또는 PC에서 비즈니스용 Skype 앱을 사용 하는 대신 휴대폰을 사용 하 여 비즈니스용 Skype 모임에 전화를 걸 수 있습니다.

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>Office 365에서 전화 시스템 및 통화 계획 설정

Office 365의 전화 시스템 기능은 비즈니스에 대 한 전화 시스템을 제공 합니다. 조직의 다른 비즈니스용 Skype 사용자에 게 전화를 거는 무료 이며, 직원 들은 서로 또는 외부 발신자 로부터 보이스 메일을 받을 수 있습니다. 전화 시스템을 사용 하 여 얻을 수 있는 기능입니다.

통화 요금제 서비스를 추가 하면 직원 들이 비즈니스용 Skype에서 기본 전화 번호를 받습니다. 회사 외부에서 전화를 걸고 받을 수 있습니다. VoIP 전화, Pc 및 모바일 장치에서 음성 통화를 할 수 있습니다. 비상시의 경우에는 911를 호출 하 여 도움을 받으세요.

단계별 설정 지침은 통화 계획 설정을 참조 하세요.

### <a name="set-up-skype-meeting-broadcast"></a>Skype 모임 브로드캐스트 설정

Skype 모임 브로드캐스트는 최대 1만 참석자와의 모임을 생성, 호스팅 및 브로드캐스트할 수 있는 기능입니다. **작동 방식에 대해 자세히 알아보려면 [Skype 모임 브로드캐스트 란?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) 를 참조 하세요.**

Skype 모임 브로드캐스트를 설정 하는 단계에 대 한 개요는 다음과 같습니다.

1. 비즈니스용 [Office 365에 대 한 라이선스 할당 또는 제거](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): 브로드캐스트 모임을 **호스트할** 모든 사용자에 게 비즈니스용 **Skype Online** 또는 **Enterprise 계획** 라이선스를 할당 합니다.

2. [Skype 모임 브로드캐스트 사용](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md):이 기능은 기본적으로 활성화 되어 있지 않습니다. 이 기능을 설정 하 고 나면 사용자는 조직의 다른 사용자와 브로드캐스트 모임을 호스트할 수 있습니다.

3. [Skype 모임 브로드캐스트를 위한 네트워크 설정](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): 조직 외부의 참석자와 웹 세미나 진행 및 기타 브로드캐스트를 호스팅하려면 네트워크를 구성 해야 합니다.

4. [Skype 모임 브로드캐스트 예약](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) 및 [Skype 모임 브로드캐스트 참가](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): 다른 사용자가 모임에 참가 하 려 할 때 *https://portal.broadcast.skype.com* skype 모임 브로드캐스트 일정을 예약 하 여 모임 브로드캐스트를 확인 합니다.

## <a name="learn-about-network-connectivity-requirements"></a>네트워크 연결 요구 사항에 대 한 자세한 정보
<a name="bkmk_more"> </a>

비즈니스용 Skype에서 오디오, 비디오, 응용 프로그램 공유 품질은 종단간 네트워크 연결의 품질에 따라 크게 영향을 받습니다. 최상의 환경을 위해서는 회사 네트워크와 비즈니스용 Skype Online 간에 고품질의 연결을 설정 하는 것이 중요 합니다. 네트워크 및 조정 정보는 [비즈니스용 Skype Online 성능을 조정](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)을 참조 하세요.

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>설정이 모두 완료 되었습니까? 비즈니스용 Skype 사용 시작 하기
<a name="bkmk_more"> </a>

[비즈니스용 Skype 교육](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): 빠르게 시작 하는 데 도움이 되는 교육 항목 목록을 확인 하세요.

[비즈니스용 Skype 전화 회의 시작](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[비즈니스용 Skype에서 비디오 장치 옵션 설정](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[비즈니스용 Skype를 사용 하 여 영상 통화 만들기 및 받기](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>관련 항목
<a name="bkmk_more"> </a>

[비즈니스용 Skype 서버와 비즈니스용 Skype Online 간 하이브리드 연결 계획](https://go.microsoft.com/fwlink/p/?linkid=400791)



