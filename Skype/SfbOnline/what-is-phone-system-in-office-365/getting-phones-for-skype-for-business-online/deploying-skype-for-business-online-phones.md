---
title: 비즈니스용 Skype Online 휴대폰 배포
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 올바른 펌웨어를 얻고, 필요한 경우 업데이트 하 고, 라이선스를 할당 하 고, 비즈니스용 Skype online 휴대폰용 설정을 구성 하는 배포 단계를 알아보세요.
ms.openlocfilehash: 5eda8c9e21ed93b09b9033c5b70bb359894330f7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705813"
---
# <a name="deploying-skype-for-business-online-phones"></a>비즈니스용 Skype Online 휴대폰 배포

이 배포 가이드는 비즈니스용 Skype Online IP 전화를 배포 하는 데 도움이 됩니다.
  
전화 번호를 사용 하는 모든 유형의 기업은 사용자가 음성 전화를 걸고 받을 수 있으며, 비즈니스를 위해 중요 한 요구 사항입니다. 전화 번호가 있는 사용자는 IP 전화, Pc, 모바일 장치를 비롯 한 모든 비즈니스용 Skype 장치에서 음성 통화를 할 수 있습니다. 비즈니스용 [Skype Online에 대 한 전화를](getting-phones-for-skype-for-business-online.md)읽어 Skype FOR business IP 전화에 대해 자세히 알아볼 수 있습니다.
  
## <a name="deployment-steps-for-ip-phones"></a>IP 휴대폰용 배포 단계

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>1 단계-제조업체의 관리자 가이드 및 전화 설명서 다운로드

시작 하기 전에 전화 제조업체의 관리 가이드 및 전화 사용자 설명서를 다운로드 하는 것이 좋습니다.
  
- Polycom 휴대폰용 [Polycom 배포 가이드](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html)를 참조 하세요.
    
- 옛 Alink 휴대폰의 경우에는 [옛 Alink 비즈니스용 SKYPE HD SIP 전화 솔루션](http://www.yealink.com/products_top_2.html)을 참조 하세요.
    
- 오디오 통화 전화의 경우 [오디오 코드 프로비저닝 관리 가이드](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)를 참조 하세요.
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>2 단계-비즈니스용 Skype 지원 IP 전화 및 펌웨어를 구매 또는 마이그레이션 하 고 있는지 확인 합니다.

비즈니스용 Skype Online 지원 되는 휴대폰 및 펌웨어가 비즈니스용 Skype 서버와도 호환 되지만, 반대의 경우는 그렇지 않습니다. 지원 되는 휴대폰 및 펌웨어를 구입 하거나 프로 비전 하는 경우 비즈니스용 [Skype Online 전화](getting-phones-for-skype-for-business-online.md)를 참조 하세요.
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>3 단계-올바른 펌웨어가 설치 되어 있는지 확인 하 고, 필요한 경우 펌웨어를 업데이트 합니다.

휴대폰의 펌웨어 버전을 확인 하세요. 용
  
- **Polycom vvx 휴대폰**의 경우 **설정** > **상태** > **플랫폼** > **응용 프로그램** > **메인**으로 이동 하세요.
    
- **옛 alink 휴대폰**의 경우 메인 전화 화면에서 **상태로** 이동 합니다.
    
- **오디오 코드 전화**, 시작 화면에서 **메뉴** > **디바이스 상태** > **펌웨어 버전** 으로 이동 합니다.
    
    > [!NOTE]
    > 전화 정보에 대 한 원격 액세스는 제조업체 관리 가이드를 참조 하세요. 위의 링크에서 사용자 안내서 및 전화 매뉴얼을 참조 하세요. 
  
- **Lpe (Lync Phone Edition) 휴대폰용**시작 화면에서 **메뉴** > **시스템 정보** 로 이동 합니다.
    
### <a name="step-4---device-update-considerations"></a>4 단계-장치 업데이트 고려 사항

> [!NOTE]
> 5.5.1 이전의 Polycom 펌웨어에는 비즈니스용 Skype 구현 "전화 잠금"으로 대체 되는 제조업체 관련 장치 잠금 메커니즘이 있습니다. 5.5.1에서 "Device Lock"으로 보안이 설정 된 전화를 업그레이드 하면 "전화-잠금"을 사용 하 여 "장치 잠금"에서 PIN 코드를 상속 받지 않으므로 안전 하지 않은 전화기를 남길 수 있습니다. "장치 잠금"을 활성화 한 사용자는 다음 Polycom 디바이스 프로필 매개 변수를 사용 하 여 사용자에 게 업그레이드 시간 (popUpSK, enabled = 1)을 제어 해야 합니다. 
  
펌웨어 업데이트는 비즈니스용 Skype 서비스에서 관리 합니다. 모든 비즈니스용 Skype 인증 휴대폰의 펌웨어가 비즈니스용 Skype 업데이트 서버에 업로드 되며 기본적으로 모든 전화기에서 장치 업데이트를 사용할 수 있습니다. 휴대폰 및 폴링 간격의 비활성 시간에 따라 전화는 자동으로 최신 인증 된 빌드를 다운로드 하 고 설치 합니다. [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet을 사용 하 고 _enabledeviceupdate_ 매개 변수를로 `false`설정 하 여 장치 업데이트 설정을 사용 하지 않도록 설정할 수 있습니다.
  
![전화 배포를 보여주는 스크린샷](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
새 펌웨어를 사용할 수 있고 다운로드 및 설치할 준비가 되 면 휴대폰에서 사용자에 게 알립니다. Polycom 휴대폰은 사용자에 게 알리고 **업데이트** 또는 **연기할**수 있는 옵션을 제공 합니다.
  
![업데이트 및 연기 옵션을 보여 주는 스크린샷](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Polycom 휴대폰의 경우 **Swupdate**를 선택 하 여 휴대폰에서 펌웨어를 업데이트할 수 있습니다.
  
![SwUpdate 옵션을 보여 주는 스크린샷](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
파트너 프로비저닝 시스템을 사용 하 여 펌웨어 업데이트를 관리 하도록 선택할 수도 있습니다. 고급 전화 사용자 지정을 비롯 한 파트너 프로비저닝 시스템 관리에 대 한 자세한 내용은 제조업체 관리 가이드를 참조 하세요.
  
> [!CAUTION]
> 업데이트 루프를 방지 하려면 단일 장치 업데이트 기관 (대역내 장치 업데이트 또는 타사 프로비저닝 서버)을 보유 하 고 있는지 확인 합니다. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>5 단계-구성 및 인프라 전화 설정

비즈니스용 Skype 대역 내 관리 Windows PowerShell cmdlet을 사용 하 여 가장 일반적으로 사용 되는 전화 옵션 및 정책을 설정할 수 있습니다. 이러한 매개 변수 및 설정에 대 한 자세한 내용은 [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) 를 참조 하세요.
  
네트워크 인프라 계획에 대해서는 [Skype 운영 프레임 워크](https://www.skypeoperationsframework.com/)를 참조 하세요.
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>6 단계-사용자가 로그인 하기 위해 준비

사용자가 비즈니스용 Skype Online 휴대폰에 성공적으로 로그인 하 여 전화를 걸 수 있도록 하려면 사용자에 게 올바른 라이선스가 할당 되었는지 확인 해야 합니다. 최소한 전화 시스템 라이선스와 통화 요금제를 할당 해야 합니다. 추가 정보는 비즈니스용 [skype 및 Microsoft 팀 추가 기능 라이선스](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) 를 확인 하 고 [비즈니스용 Skype 및 microsoft 팀 라이선스를 할당할](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)수 있습니다.
  
[전화 시스템 및 통화 요금제](/microsoftteams/calling-plan-landing-page) 를 읽고 통화 요금제에 대 한 자세한 내용을 확인할 수 있습니다.
  
- 온라인 사용자에 게 제공 되는 **로그인 옵션** 은 다음과 같습니다.
    
  - **Polycom VVX 5xx/6xx** 전화기를 사용 하는 사용자는 다음이 표시 됩니다.
    
     ![Polycom 전화 로그온을 보여 주는 스크린샷](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - **T48G/T46G** 휴대폰을 사용 하는 사용자는 다음이 표시 됩니다.
    
     ![옛 Alink 전화 로그온을 보여 주는 스크린샷](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    제조업체에서 지 원하는 로그인 옵션에 대 한 자세한 내용은 [비즈니스용 Skype Online에서 전화 받기](getting-phones-for-skype-for-business-online.md)를 참조 하세요.
    
- **사용자 ID** 휴대폰의 키패드 또는 화상 키보드 (사용 가능한 경우)를 사용 하 여 사용자는 조직의 사용자 이름 및 암호를 사용 하 여 휴대폰에 로그인 할 수 있습니다. 예를 들어 사용자 이름에 <em>amosm@contoso.com</em> 와 같은 UPN 형식을 사용 해야 합니다.
    
     ![로그인 화면을 보여 주는 스크린샷](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > LPE 및 파트너 IP 전화의 비즈니스용 Skype Online에는 PIN 인증이 지원 되지 않습니다. 
  
- **PC 사용** 사용자 PC에 설치 된 이더넷 (BToE) 소프트웨어를 사용 하는 경우 사용자는 Windows 비즈니스용 Skype 앱의 인증 창을 통해 전화에 로그인 할 수 있습니다. 다른 정보에 대 한 [디바이스 페어링 및 이더넷 (btoe))을 통해 더 잘 연결 된 경우에는 7 단계 (선택 사항)](deploying-skype-for-business-online-phones.md#BK_BTOE) 를 참조 하세요.
    
  > [!NOTE]
  > 사용자는 조직의 사용자 이름 및 암호를 사용 하 여 휴대폰에 로그인 해야 합니다. 예를 들어 사용자 이름에 <em>amosm@contoso.com</em> 와 같은 UPN 형식을 사용 해야 합니다.
  
     ![로그인 화면을 보여 주는 스크린샷](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **웹 로그인 사용**: 온라인 사용자가 표준 웹 브라우저를 사용 하 여 인증 하는 새로운 방법입니다. 사용자에 게 브라우저를 사용 하 여 로그인 할 때 수행할 수 있는 지침이 제공 됩니다.
    
  - **Polycom VVX 5xx/6xx** 전화기를 사용 하는 사용자는 다음이 표시 됩니다.
    
     ![Polycom 지침을 보여 주는 스크린샷](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - **T48G/T46G** 휴대폰을 사용 하는 사용자는 다음이 표시 됩니다.
    
     ![옛 Alink 명령을 보여주는 스크린샷](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    생성 되는 코드는 15 분 후에 만료 됩니다. 만료 되 면 사용자는 휴대폰에 따라 새 코드를 생성 하기 위해 **다시 시도** 또는 **확인** 을 클릭 해야 합니다.
    
  - **Polycom VVX 5xx/6xx** 전화기를 사용 하는 사용자는 다음이 표시 됩니다.
    
     ![만료 된 Polycom 코드를 보여 주는 스크린샷](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - **T48G/T46G** 휴대폰을 사용 하는 사용자는 다음이 표시 됩니다.
    
     ![만료 된 옛 Alink 코드를 보여 주는 스크린샷](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    브라우저를 사용 하 여 휴대폰에 표시 된 주소로 이동 하 고 비즈니스용 Skype 사용자 이름을 입력 합니다.
    
     ![전자 메일 확인을 보여 주는 스크린샷](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    휴대폰에 표시 되는 코드를 입력 합니다.
    
     ![로그인 화면에 코드 입력이 표시 된 스크린샷](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    사이트에 "[전화 제조업체 이름] **비즈니스용 Skype 인증 전화**"가 표시 되는지 확인 하 고 **계속**을 클릭 합니다.
    
     ![이름 확인을 보여 주는 스크린샷](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    사용자의 자격 증명을 클릭 하거나 **다른 계정 사용**을 클릭 합니다.
    
     ![자격 증명 옵션을 보여 주는 스크린샷](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    다음 페이지가 표시 되 면 브라우저를 닫는 것이 안전 합니다.
    
     ![확인 메시지를 보여주는 스크린샷](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > 비즈니스용 Skype Online 지원에 대 한 LPE 전화는 USB 테더 링만 통해 로그인 할 수 있습니다. 
  
- **지원 되는 배포** 아래 표에는 Exchange 통합, MFA (다단계 인증을 사용 하는 최신 인증), 비즈니스용 Skype Online 및 온-프레미스를 비롯 하 여 현재 지원 되는 배포 모델에 대 한 지원 되는 인증 유형이 나와 있습니다.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**비즈니스용 Skype** <br/> |**교환** <br/> |**휴대폰 로그인 방법** <br/> |**비즈니스용 Skype 액세스** <br/> |**최신 인증 및 MFA를 사용 하는 Exchange Access** <br/> |**최신 인증 및 MFA를 사용 하는 Exchange Access** <br/> |
|온라인  <br/> |온라인  <br/> |웹 로그인  <br/> |예  <br/> |예  <br/> |예  <br/> |
|온라인  <br/> |온라인  <br/> |사용자 이름/비밀 번호  <br/> |예  <br/> |예  <br/> |아니요  <br/> |
|온라인  <br/> |온-프레미스  <br/> |웹 로그인  <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |
|온라인  <br/> |온-프레미스  <br/> |사용자 이름/비밀 번호  <br/> |예  <br/> |예  <br/> |아니요  <br/> |
|온-프레미스  <br/> |온라인/온-프레미스  <br/> |PIN 인증  <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |
|온-프레미스  <br/> |온라인/온-프레미스  <br/> |사용자 이름/비밀 번호  <br/> |예  <br/> |예  <br/> |해당 없음  <br/> |
|온-프레미스  <br/> |온라인/온-프레미스  <br/> |PC를 통한 로그인 (BTOE)  <br/> |예  <br/> |예  <br/> |해당 없음  <br/> |
   
- **전화 기능** 기능 집합은 IP 전화 파트너에 따라 약간씩 다를 수 있습니다. 전체 기능 집합 및 각 전화 제조업체의 기능에 대 한 자세한 내용은 [비즈니스용 Skype Online에서 전화 받기](getting-phones-for-skype-for-business-online.md)를 참조 하세요.
    
- **전화-잠금** 기능은 휴대폰을 보호 하는 데 사용 되는 비즈니스용 Skype 인증 전화에서 최근에 소개 된 기능입니다. 이 설정을 사용 하면 인증에 성공한 사용자에 게 PIN을 만들라는 메시지가 표시 됩니다. 일단 만든 유휴 시간 제한이 만료 되는 경우, 사용자가 수동으로 휴대폰을 잠그거나 전화 연결을 사용 하 여 PC 잠금과 휴대폰 잠금을 동기화 할 때 전화가 잠깁니다. 전화 잠금 PIN을 여러 번 잘못 입력 한 경우, 휴대폰은 사용자에 게 로그인 하거나 전화를 잠금 해제 하기 위해 관리자의 코드가 필요 하지만,이는 휴대폰 파트너에 따라 달라 집니다. 사용자의 PIN은 6 ~ 15 자리 여야 합니다.
    
    조직에 대해 전화 (기본적으로 설정 되어 있음)를 사용 하지 않도록 설정할 수 있으며, 유휴 시간 제한을 변경 하 고, 사용자가 inband-설정을 사용 하지 않거나 잠겨 있는 동안 전화를 걸 수 있는지 여부를 선택 합니다. 이러한 설정에 대 한 자세한 내용은 [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) 를 참조 하세요.
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>7 단계 (선택 사항)-이더넷 (BToE)를 통해 디바이스 페어링과 더 나은 기능을 함께 사용 하는 경우
<a name="BK_BTOE"> </a>

BToE는 사용자의 휴대폰을 Windows 용 비즈니스용 Skype 앱과 쌍을 이루는 파트너 IP 전화에 대 한 전화기 메커니즘입니다. BToE 지를 통해 사용자는 다음을 수행할 수 있습니다.
  
- 비즈니스용 Skype 데스크톱 앱 (PC 사용)을 사용 하 여 자신의 IP 전화에 로그인
    
- 전화 동기화-PC 잠금과 잠금
    
- 클릭 하 여 전화 걸기
    
BToE는 두 가지 모드 ( *자동* (기본값)와 *수동* )에서 작동 하도록 구성할 수 있습니다. 비즈니스용 Skype 대역내 설정을 사용 하는 사용자에 대해 사용 하도록 설정 (기본값)/사용 하지 않도록 설정할 수도 있습니다. *수동* 모드에서 작업 하는 경우 사용자는 Windows 앱과 휴대폰을 연결 하는 추가 단계를 수행 해야 합니다.
  
 **사용자에 게 BToE를 배포 하려면**
  
1. PC 포트를 사용 하 여 PC를 전화기에 연결 합니다.
    
     ![PC 연결을 보여 주는 스크린샷](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. 아래 링크에서 제조업체 웹 사이트의 최신 BToE 소프트웨어를 다운로드 하 여 설치 합니다. 사용자 환경을 개선 하기 위해 Microsoft 끝점 구성 관리자와 같은 관리 배포 솔루션을 사용 하 여 BToE 소프트웨어를 배포 하 고 설치할 수 있습니다. 구성 관리자를 사용 하는 방법에 대 한 도움말은 [Configuration manager에서 패키지 및 프로그램](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)을 참조 하세요.
    
   - [Polycom BToE 소프트웨어 다운로드 사이트](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [옛 alink 소프트웨어 다운로드](http://www.yealink.com/products_list_10.html)
    
   - [오디오 코드 BToE 소프트웨어 다운로드](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. BToE에 대 한 서버 설정은 기본적으로 **사용** 으로 설정 되 고 **자동 모드** 입니다. 이러한 설정을 변경 하려면 [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx)을 참조 하세요.
    
> [!NOTE]
> BToE는 현재 Mac 및 VDI 플랫폼에서 지원 되지 않습니다. 
  
## <a name="related-topics"></a>관련 주제
[비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 가져오기](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[오디오 회의 및 통화 요금제 국가 및 지역 가용성](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
