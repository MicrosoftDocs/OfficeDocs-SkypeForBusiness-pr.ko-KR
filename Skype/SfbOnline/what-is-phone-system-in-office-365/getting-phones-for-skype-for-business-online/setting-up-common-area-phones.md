---
title: 공용 영역 휴대폰 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
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
description: 배포 단계에 대해 알아보고, 올바른 펌웨어를 다운로드하고, 필요한 경우 업데이트하고, 라이선스를 할당하고, 공통 영역 휴대폰에 대한 설정을 구성합니다.
ms.openlocfilehash: 4fd45f446d71e581305f7e596c7eacc62f54f8ca
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237354"
---
# <a name="set-up-common-area-phones"></a>공통 지역 전화 설정

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]
일반적으로 CAP(공용 영역 전화)는 많은 사람들이 사용할 수 있는 로비 또는 다른 영역과 같은 영역에 배치됩니다. 예를 들어 수신 영역 전화, 도어 전화 또는 회의실 전화, CAP는 사용자 대신 디바이스로 설정되고 네트워크에 자동으로 로그인됩니다. 아래 단계에서는 이러한 유형의 휴대폰을 조직에 배포할 수 있도록 전화 시스템 통화 요금제로 계정 설정에 도움이 됩니다.

## <a name="prerequisites-for-common-area-phones"></a>공용 영역 휴대폰에 대한 전제

가장 먼저 해야 할 일은 다음이 있는지 확인하는 것입니다.

- 공용 지역 전화 라이선스 및 통화 계획을 구입합니다.
- 승인된 휴대폰을 검색하고 구입합니다(목록 [보기).](deploying-skype-for-business-online-phones.md)
- 휴대폰에서 펌웨어를 업데이트합니다(이 항목에서 지원되는 펌웨어 [참조).](getting-phones-for-skype-for-business-online.md)  다음을 수행하여 휴대폰에서 펌웨어를 확인할 수 있습니다.
  - **Polycom VVX 휴대폰**: 설정 플랫폼 애플리케이션  >    >    >    >  **메인으로 이동합니다.**
  - **Yealink 휴대폰**: 기본 전화 화면에서 **상태로** 이동합니다.
  - **AudioCodes 휴대폰**: 시작 화면에서 **메뉴**  >  **디바이스 상태** 펌웨어  >  **버전으로** 이동합니다.
  - **Lync 전화 버전(LPE)** 휴대폰: 시작 화면에서 메뉴 시스템 정보 메뉴로  >   이동하세요.

    펌웨어 업데이트는 서비스에서 비즈니스용 Skype 관리됩니다. 모든 비즈니스용 Skype 인증된 휴대폰의 펌웨어는 업데이트 비즈니스용 Skype 업데이트 서버에 업로드하고 기본적으로 모든 휴대폰에서 디바이스 업데이트를 사용하도록 설정됩니다.

    휴대폰의 비활성 시간 및 폴링 간격에 따라 휴대폰이 자동으로 최신 인증된 빌드를 다운로드하고 설치합니다. [Set-CsIPPhonePolicy](/powershell/module/skype/set-csipphonepolicy) cmdlet을 사용하고 *EnableDeviceUpdate* 매개 변수를 로 설정하여 디바이스 업데이트 설정을 사용하지 않도록 설정할 수 `false` 있습니다.

## <a name="setting-up-a-common-area-phone"></a>공용 영역 설정 전화
다음 단계를 따라야 합니다.

### <a name="step-1---buy-the-licenses"></a>1단계 - 라이선스 구매
1. 관리 센터에서 청구 구매 서비스로  >  **이동하고** 다른 요금제 **를 추가합니다.**

    ![공용 영역 라이선스의 전화 스크린샷](../../images/cap-license.png)
2. 체크 아웃 **페이지에서** 지금 전화 구입을 클릭하고 지금 >  >   **구매를 클릭합니다.** 
3. 클릭을 클릭하여 **추가 기능 구독을 확장한** 다음 클릭하여 통화 요금제 구입을 클릭합니다. 국내 통화  계획 또는 국내 및 국제 통화 계획 **중 하나를 선택 합니다.**

> [!Note]
> 라이선스가 필요 전화 시스템 없습니다. 공용 영역 라이선스에 전화 **포함되어** 있습니다.

라이선스에 대한 자세한 내용은 추가 비즈니스용 Skype 및 Microsoft Teams [를 참조하세요.](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>2단계 - 휴대폰에 대한 새 사용자 계정 만들기 및 라이선스 할당
1. 관리 센터에서 사용자 활성 사용자 추가 으로  >    >  **이동하세요.**
2. 이름의  "Main"과 같은 사용자 이름과 두 번째 이름의 "수신"을 입력합니다.
3. "Main  Reception"처럼 자동으로 자생하지 않는 경우 표시 이름을 입력합니다.
4. "MainReception" 또는 "Mainlobby"같은 사용자 이름을 입력합니다. 
5. 공통 영역 휴대폰의 경우 암호를 수동으로 설정하거나 모든 공통 영역 휴대폰에 대해 동일한 암호를 사용할 수 있습니다. 또한 이 사용자가 처음 로그인할 때 암호를 변경하도록 선택을 선택하지 않는 **것으로 생각할 수도 있습니다.**
6. 여전히 있는 경우 이 사용자에게 라이선스를 할당합니다. 동일한 페이지에서 제품 **라이선스를 확장하려면 를 클릭합니다.** 다음을 설정합니다.
   - 공용 영역 전화
   - 그런 다음 국내 통화  계획 또는 국내 및 국제 통화 계획을 **선택해야 합니다.**

     라이선스 할당은 다음과 같습니다.

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > 알다시 비즈니스용 Skype 계획 2는 공용 영역 라이선스에 전화 **있습니다.**

자세한 내용은 사용자 추가 [를 참조합니다.](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>3단계 - 공용 영역 사용자 계정에 전화 전화 할당

![관리 센터를 사용하여 사용자에게 비즈니스용 Skype 로고를 표시하는 아이콘 비즈니스용 Skype ](../../images/sfb-logo-30x30.png) **지정**

1. 관리 센터에서 > **관리 센터에서**  >  비즈니스용 Skype.
2. 관리 **비즈니스용 Skype 음성 전화**  >     >  **번호입니다.**
3. 전화 번호 목록에서 숫자를 선택하고 **할당을 클릭합니다.**
4. 할당 **페이지에서** **음성** 사용자 상자에 휴대폰에 사용되는 사용자의 이름을 입력한 다음 음성 사용자  선택 드롭다운에서 사용자를 선택합니다.
5. 이 경우 긴급 주소를 추가해야 합니다. 검색하면 긴급 주소  선택 아래에서 적합한 주소를 선택합니다.
6. **저장을** 클릭하고 사용자는 다음과 같이 봐야 합니다.

    ![사용자 전화 번호 스크린샷](../../images/cap-user-number.png)

   > [!Note]
   > 라이선스가 적용된 전화 시스템 사용자에게만 표시됩니다.  방금 이 경우 사용자가 목록에 표시하는 데 약간의 시간이 걸리는 경우도 있습니다.

자세한 내용은 [사용자에 대한 전화 번호 보기를 참조합니다.](/microsoftteams/getting-phone-numbers-for-your-users)

궁금한 경우 다른 통신사 및 "포트"에 있는 휴대폰번호를 찍거나 해당 휴대폰을 Microsoft 365 또는 Office 365. 를 [참조하여 전화 번호를](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)Teams.

### <a name="step-4---setting-up-your-phone"></a>4단계 - 휴대폰 설정

**휴대폰에서 모드 설정**

공용 영역 모드가 켜져 있어야 전화 **전화** 또는 휴대폰입니다. 해당 작업을 확인하여 해당 작업을 확인할 수 있습니다.

**Polycom VVX 휴대폰을 설정하는 방법에 대한 예제는 다음과 같습니다.**

- 다음 전화 다음 단계를 수행하여 Polycom VVX에 공통 영역 설정 모드를 사용하도록 설정합니다.
    1. 브라우저에서 CAP 모드를 사용하도록 설정할 수 있도록 웹 인터페이스에 연결합니다.
    2. 그런 다음  설정으로 **이동하여** 비즈니스용 Skype 설정 옵션에서 공통 영역 **전화.**
    3. 예를 **클릭하여** 설정을 저장합니다.

- 이제 CAP 모드를 사용하도록 설정하고 휴대폰의 디스플레이를 사용하여 휴대폰을 설정합니다. 표시에는 **CaAP가 사용하도록 설정되어 있습니다.** 그런 다음 다음을 합니다.

    1. 를 **설정** 클릭합니다.
    2. 고급 **을 선택합니다.**
    3. 암호를 입력합니다.
    4. 관리 **설정에서** **공통** 영역 전화 설정.
    5. **CAP 및** CAP 관리 모드를 **사용하도록 설정합니다.**
    6. 구성 **저장 을 클릭합니다.**

- 이제 휴대폰이 준비되어 있으므로 홈 화면에 로그인할 수 있습니다.

    1. 기능 설정   >  **선택하여 로그인**  >  **비즈니스용 Skype.**
    2. 사용자 **자격 증명을** 선택하고 **CAP(웹 로그인)를** 선택하여 코드를 생성합니다.
    3. [프로비전 포털로 이동하고](https://aka.ms/skypecap)관리자로 **로그인합니다.**
    4. 표시 이름(예: Main Reception)을 입력합니다.

       > [!Note]
       > 공용 **영역** 휴대폰 검색만 선택된 경우 확인란을 선택 취소하고 다시 검색합니다.

    5. 페어링 코드 창에서 휴대폰에 표시된 코드를 입력하고 프로비전 을 **클릭합니다.**

        이 마지막 단계에 따라 휴대폰이 자동으로 로그인해야 합니다.


> [!NOTE]
> CAP 프로비전 사이트는 CAP 계정의 암호를 임의 암호로 재설정합니다. CAP가 참조하는 계정은 AAD(Azure Active Directory) 계정입니다. AAD에서만 계정을 만든 경우 프로세스가 간단합니다. AAD에 On-Premises Active Directory를 동기화하고 타사 IDP 또는 ADFS를 사용하는 경우 CAP 프로비전이 실패합니다. 이 경우 CAP 프로비전이 작동하려면 Microsoft 365 Office 365/Azure Active Directory 계정(예: onmicrosoft.com 도메인이 있는 **계정)만** 사용해야 합니다.


### <a name="related-topics"></a>관련 주제

- 온라인 휴대폰 배포에서 사용 가능한 [비즈니스용 Skype 자세히 알아보기](deploying-skype-for-business-online-phones.md)
- [비즈니스용 Skype Online 휴대폰 받기](getting-phones-for-skype-for-business-online.md)
