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
description: 올바른 펌웨어를 다운로드하고, 필요한 경우 업데이트하고, 라이선스를 할당하고, 비즈니스용 Skype 온라인 전화에 대한 설정을 구성하는 배포 단계에 대해 알아보십시오.
ms.openlocfilehash: 41c6ef53469ab2de3699fd17a2d181477e143fae
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220448"
---
# <a name="deploying-skype-for-business-online-phones"></a>비즈니스용 Skype Online 휴대폰 배포

이 배포 가이드는 비즈니스용 Skype Online IP 휴대폰을 배포하는 데 도움이 됩니다.
  
모든 유형의 비즈니스에서 전화 번호를 사용하면 사용자가 음성 통화를 걸고 받을 수 있으며 비즈니스를 해야 하는 중요한 요구 사항입니다. 전화 번호가 있는 사용자는 IP 전화, PC 및 모바일 장치를 비롯한 모든 비즈니스용 Skype 장치에서 음성 통화를 걸 수 있습니다. 비즈니스용 Skype Online용 전화기에서 비즈니스용 Skype IP 전화에 대해 자세히 [배울 수 있습니다.](getting-phones-for-skype-for-business-online.md)
  
## <a name="deployment-steps-for-ip-phones"></a>IP 휴대폰에 대한 배포 단계

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>1단계 - 제조업체의 관리자 가이드 및 전화 설명서 다운로드

시작하기 전에 휴대폰 제조업체의 관리 가이드 및 전화 사용자 설명서를 다운로드하는 것이 좋습니다.
  
- Polycom 휴대폰의 경우 [Poly 설명서 라이브러리를 참조하세요.](https://documents.polycom.com/category/voice)
    
- Yealink 휴대폰의 경우 [Yealink 비즈니스용 Skype HD SIP Phones 솔루션을 참조하세요.](http://www.yealink.com/products_top_2.html)
    
- AudioCodes 휴대폰의 경우 오디오 코드 프로비전 관리 [가이드를 참조하세요.](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>2단계 - 비즈니스용 Skype 지원 IP 전화 및 펌웨어를 구입하거나 마이그레이션하고 있는지 확인

비즈니스용 Skype Online 지원 전화 및 펌웨어도 비즈니스용 Skype Server와 호환되지만 항상 그렇지는 않습니다. 지원되는 휴대폰과 펌웨어를 구입하거나 프로비전하는지 확인은 [비즈니스용 Skype Online용 전화기 다운로드를 참조하세요.](getting-phones-for-skype-for-business-online.md)
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>3단계 - 올바른 펌웨어가 설치되어 있는지 확인하고 필요한 경우 펌웨어를 업데이트합니다.

휴대폰에서 펌웨어 버전을 검사합니다. For:
  
- **Polycom VVX 휴대폰에서** 설정 상태 플랫폼 애플리케이션  >    >    >  **주로**  >  **이동합니다.**
    
- **Yealink 전화기에서** 주 전화 **화면의** 상태로 이동
    
- **AudioCodes 휴대폰의** 시작 화면에서 **메뉴** 디바이스 상태  >    >  **펌웨어** 버전으로 이동하세요.
    
    > [!NOTE]
    > 전화 세부 정보에 대한 원격 액세스는 제조업체 관리 가이드를 참조하세요. 사용자 가이드 및 전화 설명서는 위의 링크를 참조하세요. 
  
- **LPE(Lync Phone Edition)** 휴대폰을 시작 화면에서 **메뉴**  >  **시스템** 정보로 이동
    
### <a name="step-4---device-update-considerations"></a>4단계 - 디바이스 업데이트 고려 사항

> [!NOTE]
> 5.5.1.X 이전의 Polycom 펌웨어에는 비즈니스용 Skype 구현 "Phone-Lock"으로 대체되는 제조업체별 장치 잠금 메커니즘이 있습니다. "Device-Lock"으로 보안이 유지된 5.4.X.X에서 "Phone-Lock"으로 보안이 유지된 휴대폰을 5.5.1.X로 업그레이드하면 "Device-Lock"에서 PIN 코드를 상속하지 않습니다. 이 경우 휴대폰이 보안되지 않은 것으로 남을 수 있습니다. "Device-Lock"을 활성화한 사용자는 사용자에게 업그레이드 시간(lync.deviceUpdate.popUpSK.enabled=1)을 제어하도록 다음 Polycom 디바이스 프로필 매개 변수를 사용하도록 설정해야 합니다. 
  
펌웨어 업데이트는 비즈니스용 Skype 서비스에서 관리됩니다. 모든 비즈니스용 Skype 인증 휴대폰 펌웨어는 비즈니스용 Skype 업데이트 서버에 업로드됩니다. 장치 업데이트는 기본적으로 모든 휴대폰에서 사용하도록 설정됩니다. 휴대폰의 비활성 시간 및 폴링 간격에 따라 휴대폰은 자동으로 인증된 최신 빌드를 다운로드하여 설치합니다. [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet을 사용하고 _EnableDeviceUpdate_ 매개 변수를 으로 설정하여 디바이스 업데이트 설정을 사용하지 않도록 설정할 수 `false` 있습니다.
  
![휴대폰 배포를 보여주는 스크린샷](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
새 펌웨어를 사용할 수 있으며 다운로드 및 설치가 준비되면 휴대폰에서 사용자에게 알릴 것입니다. Polycom 전화기에서 사용자에게 알리고 업데이트 또는  연기 옵션을 **제공합니다.**
  
![업데이트 및 연기 옵션을 보여주는 스크린샷](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Polycom 휴대폰의 경우 **SwUpdate를** 선택하여 휴대폰의 펌웨어를 업데이트할 수 있습니다.
  
![SwUpdate 옵션을 보여주는 스크린샷](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
파트너 프로비전 시스템을 사용하여 펌웨어 업데이트를 관리하기로 선택할 수도 있습니다. 고급 전화 사용자 지정을 포함한 파트너 프로비전 시스템 관리는 제조업체 관리 가이드를 참조하세요.
  
> [!CAUTION]
> 업데이트 루프를 방지하려면 단일 디바이스 업데이트 기관(대역 내 디바이스 업데이트 또는 타사 프로비전 서버)이 있는지 확인합니다. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>5단계 - 구성 및 인프라 전화 설정

비즈니스용 Skype 대역 내 관리 cmdlet을 사용하여 가장 일반적으로 사용되는 전화 옵션 및 정책을 Windows PowerShell 있습니다. 이러한 매개 변수 및 설정에 대한 자세한 내용은 [Set-CsIPPhonePolicy를](https://technet.microsoft.com/library/mt629497.aspx) 참조하세요.
  
네트워크 인프라 계획은 [Skype Operations Framework를 참조하세요.](https://www.skypeoperationsframework.com/)
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>6단계 - 사용자가 로그인할 수 있도록 준비

사용자가 비즈니스용 Skype Online 전화에 성공적으로 로그인하고 전화를 걸 수 있도록 설정하려면 사용자에게 올바른 라이선스가 할당되어 있는지 확인합니다. 최소한 전화 시스템 라이선스 및 통화 플랜을 할당해야 합니다. 자세한 내용은 비즈니스용 [Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) 및 Microsoft Teams 추가 기능 라이선스를 보고 비즈니스용 Skype 및 [Microsoft Teams 라이선스를 할당할 수 있습니다.](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)
  
전화 시스템 및 통화 요금제에서 통화 요금제에 대한 자세한 정보를 찾을 [수 있습니다.](/microsoftteams/calling-plan-landing-page)
  
- **온라인 사용자가** 사용할 수 있는 로그인 옵션은 다음과 같습니다.
    
  - **Polycom VVX 5XX/6XX** 휴대폰을 사용 하는 사용자는 다음을 볼 수 있습니다.
    
     ![Polycom 전화 로그온을 보여주는 스크린샷](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - **Yealink T48G/T46G** 휴대폰이 있는 사용자에게는 다음이 표시될 수 있습니다.
    
     ![Yealink 전화 로그온을 보여주는 스크린샷입니다.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    제조업체에서 지원하는 로그인 옵션에 대한 자세한 내용은 비즈니스용 [Skype Online용 전화기 보기를 참조하세요.](getting-phones-for-skype-for-business-online.md)
    
- **사용자 ID** 휴대폰의 키패드 또는 화면 키보드(사용 가능한 경우)를 사용하여 사용자는 조직의 사용자 이름 및 암호를 사용하여 휴대폰에 로그인할 수 있습니다. 예를 들어 사용자 이름에 대해 amosm@contoso.com <em>UPN</em>  형식을 사용해야 합니다.
    
     ![로그인 화면을 보여주는 스크린샷](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > PIN 인증은 LPE 및 파트너 IP 전화용 비즈니스용 Skype Online에서 지원되지 않습니다. 
  
- **PC 사용** BToE(Better Together over Ethernet) 소프트웨어가 사용자의 PC에 설치되어 사용하도록 설정되면 사용자는 Windows 비즈니스용 Skype 앱의 인증 창을 사용하여 휴대폰에 로그인할 수 있습니다. [7단계(선택 사항) -](deploying-skype-for-business-online-phones.md#BK_BTOE) 디바이스 페어링이 있는 경우 BToE(이더넷)를 통해 더 잘 짝을 이루는 경우 다른 정보를 참조하세요.
    
  > [!NOTE]
  > 사용자는 조직의 사용자 이름 및 암호를 사용하여 휴대폰에 로그인해야 합니다. 예를 들어 사용자 이름에 대해 amosm@contoso.com  <em>UPN</em>  형식을 사용해야 합니다.
  
     ![로그인 화면을 보여주는 스크린샷](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **웹 로그인 사용:** 이 방법은 온라인 사용자가 표준 웹 브라우저를 사용하여 인증할 수 있는 새로운 방법입니다. 사용자가 브라우저를 사용하여 로그인할 때 따라야 할 지침 집합이 제공됩니다.
    
  - **Polycom VVX 5XX/6XX** 휴대폰을 사용 하는 사용자는 다음을 볼 수 있습니다.
    
     ![Polycom 지침을 보여주는 스크린샷](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - **Yealink T48G/T46G** 휴대폰이 있는 사용자에게는 다음이 표시될 수 있습니다.
    
     ![Yealink 지침을 보여주는 스크린샷](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    생성된 코드는 15분 후에 만료됩니다. 만료되면 사용자는 휴대폰에 따라 **다시** 시도 또는  확인을 클릭하여 새 코드를 생성해야 합니다.
    
  - **Polycom VVX 5XX/6XX** 휴대폰을 사용 하는 사용자는 다음을 볼 수 있습니다.
    
     ![만료된 Polycom 코드를 보여주는 스크린샷](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - **Yealink T48G/T46G** 휴대폰이 있는 사용자에게는 다음이 표시될 수 있습니다.
    
     ![만료된 Yealink 코드를 보여주는 스크린샷](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    브라우저를 사용하여 전화에 표시된 주소로 이동하고 비즈니스용 Skype 사용자 이름을 입력합니다.
    
     ![전자 메일 확인을 보여주는 스크린샷](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    휴대폰에 표시된 코드를 입력합니다.
    
     ![로그인 화면에 코드 입력을 보여주는 스크린샷](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    사이트에 "[휴대폰 제조업체 이름] **비즈니스용 Skype 인증 전화"가 표시되고** 계속을 **클릭합니다.**
    
     ![이름 확인을 보여주는 스크린샷](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    사용자의 자격 증명을 클릭하거나 다른 계정 **사용:**
    
     ![자격 증명 옵션을 보여주는 스크린샷](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    다음 페이지가 표시되면 브라우저를 닫는 것이 안전합니다.
    
     ![확인 메시지를 보여주는 스크린샷](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > 비즈니스용 Skype Online용 LPE 휴대폰은 USB 테더링을 통해서만 로그인을 지원합니다. 
  
- **지원되는 배포** 아래 표에서는 Exchange 통합, MFA(Multi-Factor Authentication)를 사용하는 최신 인증, 비즈니스용 Skype Online 및 On-프레미스를 포함하여 현재 지원되는 배포 모델에 대해 지원되는 인증 유형을 보여줍니다.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**비즈니스용 Skype** <br/> |**Exchange** <br/> |**전화 Sign-In 방법** <br/> |**비즈니스용 Skype 액세스** <br/> |**최신 Auth 및 MFA를 사용하지 않도록 설정한 Exchange Access** <br/> |**최신 Auth 및 MFA를 사용하도록 설정된 Exchange Access** <br/> |
|온라인  <br/> |온라인  <br/> |웹 로그인  <br/> |예  <br/> |예  <br/> |예  <br/> |
|온라인  <br/> |온라인  <br/> |사용자 이름/암호  <br/> |예  <br/> |예  <br/> |아니요  <br/> |
|온라인  <br/> |On-premises  <br/> |웹 로그인  <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |
|온라인  <br/> |On-Premises  <br/> |사용자 이름/암호  <br/> |예  <br/> |예  <br/> |아니요  <br/> |
|On-premises  <br/> |온라인/온-프레미스  <br/> |PIN 인증  <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |
|On-premises  <br/> |온라인/온-프레미스  <br/> |사용자 이름/암호  <br/> |예  <br/> |예  <br/> |해당 없음  <br/> |
|On-premises  <br/> |온라인/온-프레미스  <br/> |PC(BTOE)를 통해 로그인  <br/> |예  <br/> |예  <br/> |해당 없음  <br/> |
   
- **전화 기능** 기능 집합은 IP 전화 파트너에 따라 약간 다를 수 있습니다. 전체 기능 집합 및 각 전화 제조업체의 기능에 대한 자세한 내용은 비즈니스용 [Skype Online용 전화기 보기를 참조하세요.](getting-phones-for-skype-for-business-online.md)
    
- **전화 잠금은** 휴대폰을 보호하는 데 사용되는 비즈니스용 Skype 인증 전화기에서 최근에 도입된 기능입니다. 사용하도록 설정하면 인증에 성공하면 사용자에게 PIN을 만들지 묻는 요청이 표시됩니다. 사용자가 정의한 유휴 시간 제한이 만료되거나, 사용자가 휴대폰을 수동으로 잠그거나, 휴대폰 페어링을 사용하여 휴대폰 잠금을 PC 잠금과 동기화하면 휴대폰이 잠기게 됩니다. 전화 잠금 PIN을 여러 번 잘못 입력한 경우 전화기에서 사용자를 로그인하거나 관리자의 코드로 전화 잠금을 해제하도록 요구하지만 전화 파트너에 따라 다릅니다. 사용자의 PIN은 6~15자리 사이입니다.
    
    조직에 대한 Phone-Lock(기본적으로 사용하도록 설정)를 사용하지 않도록 설정하고, 유휴 시간 제한을 변경하고, 사용자가 잠긴 동안 전화 통화를 걸 수 있는지 또는 인밴드 설정을 사용하지 않을지 여부를 선택할 수 있습니다. 이러한 설정에 대한 자세한 내용은 [Set-CsUCPhoneConfiguration을](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) 참조하세요.
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>7단계(선택 사항) - 디바이스 페어링이 있는 경우 이더넷(BToE)을 통해 더 잘 모일 수 있습니다.
<a name="BK_BTOE"> </a>

BToE는 사용자의 휴대폰을 비즈니스용 Skype 앱과 페어링하는 파트너 IP 전화기용 전화기입니다. BToE를 사용하면 사용자가
  
- 비즈니스용 Skype 데스크톱 앱(PC 사용)을 사용하여 IP 휴대폰에 로그인
    
- PC Phone-Lock 동기화
    
- 클릭하여 통화
    
BToE는 자동(기본값) 및 수동의  두 가지 모드로 작동하도록 구성할 수 *있습니다.* 또한 대역 내 비즈니스용 Skype 설정을 사용하는 사용자에 대해 활성화(기본값)/비활성화할 수도 있습니다. 수동 모드에서 *작동할*  때 사용자는 Windows 앱과 휴대폰을 페어링하기 위해 추가 단계를 취해야 합니다.
  
 **사용자에게 BToE를 배포하는 경우**
  
1. PC 포트를 사용하여 PC를 휴대폰에 연결합니다.
    
     ![PC에 대한 연결을 보여주는 스크린샷](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. 아래 링크에서 제조업체 웹 사이트에서 최신 BToE 소프트웨어를 다운로드하여 설치합니다. 더 나은 사용자 환경을 위해 Microsoft Endpoint Configuration Manager와 같은 관리 배포 솔루션을 사용하여 BToE 소프트웨어를 배포하고 설치할 수 있습니다. 구성 관리자 사용에 대한 도움말은 Configuration Manager의 패키지 [및 프로그램을 참조합니다.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)
    
   - [Polycom BToE 소프트웨어 다운로드 사이트](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Yealink BToe 소프트웨어 다운로드](http://www.yealink.com/products_list_10.html)
    
   - [AudioCodes BToE 소프트웨어 다운로드](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. BToE에 대한 서버 설정은 기본적으로 사용 및 자동 **모드로** 설정됩니다.  이러한 설정을 변경하려면 [Set-CsIPPhonePolicy를 참조하세요.](https://technet.microsoft.com/library/mt629497.aspx)
    
> [!NOTE]
> BToE는 현재 Mac 및 VDI 플랫폼에서 지원되지 않습니다. 
  
## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 가져오기](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[다음은 전화 시스템 기능입니다.](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[오디오 회의 및 통화 요금제 국가 및 지역 가용성](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
