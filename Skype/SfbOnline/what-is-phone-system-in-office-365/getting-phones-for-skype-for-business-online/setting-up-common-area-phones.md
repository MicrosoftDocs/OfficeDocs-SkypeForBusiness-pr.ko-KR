---
title: 공용 영역 전화 설정
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
description: 배포 단계에 대해 알아보고, 올바른 펌웨어를 다운로드하고, 필요한 경우 업데이트하고, 라이선스를 할당하고, 공용 영역 전화에 대한 설정을 구성합니다.
ms.openlocfilehash: 02cab34b4a1f220e8f28ceeee794470191582704
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220408"
---
# <a name="set-up-common-area-phones"></a>공통 지역 전화 설정
공용 영역 전화(CAP)는 일반적으로 대기실 또는 많은 사람들이 사용할 수 있는 다른 영역에 배치됩니다. 예를 들어 수신 지역 전화, 문 전화 또는 회의실 전화, CAP는 사용자가 아닌 장치로 설정되고 네트워크에 자동으로 로그인합니다. 아래 단계에서는 조직에 대해 이러한 유형의 휴대폰을 배포할 수 있도록 통화 요금제로 전화 시스템에 대한 계정을 설정하는 방법을 설명합니다.

## <a name="prerequisites-for-common-area-phones"></a>공용 지역 전화에 대한 전제적 준비

가장 먼저 해야 할 일은 다음이 있는지 확인하는 것입니다.

- 일반 지역 전화 라이선스 및 통화 플랜을 구매합니다.
- 승인된 휴대폰을 검색하여 구입합니다(여기에서 목록 [보기).](deploying-skype-for-business-online-phones.md)
- 휴대폰에서 펌웨어를 업데이트합니다(이 항목에서 지원되는 펌웨어 [참조).](getting-phones-for-skype-for-business-online.md)  다음을 수행하여 휴대폰에서 펌웨어를 확인할 수 있습니다.
  - **Polycom VVX 휴대폰:** 설정  >  **상태 플랫폼** 애플리케이션  >    >    >  **주로 이동합니다.**
  - **Yealink 휴대폰:** 주 전화 **화면에서** 상태로 이동
  - **AudioCodes 휴대폰:** 시작 화면에서 **메뉴** 디바이스 상태  >    >  **펌웨어** 버전으로 이동
  - **LPE(Lync Phone Edition)** 전화기: 시작 화면에서 **메뉴**  >   시스템 정보로 이동

    펌웨어 업데이트는 비즈니스용 Skype 서비스에서 관리됩니다. 모든 비즈니스용 Skype 인증 휴대폰 펌웨어는 비즈니스용 Skype 업데이트 서버에 업로드됩니다. 장치 업데이트는 기본적으로 모든 휴대폰에서 사용하도록 설정됩니다.

    휴대폰의 비활성 시간 및 폴링 간격에 따라 휴대폰은 자동으로 인증된 최신 빌드를 다운로드하여 설치합니다. [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet을 사용하고 *EnableDeviceUpdate* 매개 변수를 으로 설정하여 디바이스 업데이트 설정을 사용하지 않도록 설정할 수 `false` 있습니다.

## <a name="setting-up-a-common-area-phone"></a>공용 영역 전화 설정
다음 단계를 따라야 합니다.

### <a name="step-1---buy-the-licenses"></a>1단계 - 라이선스 구입
1. 관리 센터에서 청구 구매 서비스로 이동하고  >  다른 계획을 **추가합니다.**

    ![CAP-license.png](../../images/cap-license.png)
2. 이제 체크 **아웃** 페이지에서 일반 지역 전화 > 클릭하고 지금  >   구입을 **클릭합니다.** 
3. 추가 기능 **구독을** 확장하려면 클릭한 다음 클릭하여 통화 요금제 구입을 클릭합니다. 국내 통화 요금제 또는 **국내** 및 국제 통화 요금제 중 하나를 **선택 합니다.**

> [!Note]
> 전화 시스템 라이선스가 필요하지 않습니다. 공용 영역 전화 **라이선스에 포함되어** 있습니다.

라이선스에 대한 자세한 내용은 비즈니스용 Skype 및 Microsoft Teams 추가 기능 라이선스를 [참조하세요.](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>2단계 - 휴대폰에 대한 새 사용자 계정 만들기 및 라이선스 할당
1. 관리 센터에서 사용자   >  **활성 사용자**  >  **추가로 이동하여 사용자를 추가합니다.**
2. 이름의  경우 "Main"과 같은 사용자 이름을 입력하고 두 번째 이름은 "수신"을 입력합니다.
3. "주  수신"처럼 자동으로 표시되지 않는 경우 표시 이름을 입력합니다.
4. "MainReception" 또는 "Mainlobby"처럼 사용자 이름을 입력합니다. 
5. 일반 지역 전화의 경우 암호를 수동으로 설정하거나 일반 지역 전화에 대해 동일한 암호를 사용하는 것이 좋습니다. 또한 이 사용자가 처음 로그인할 때 암호를 변경하도록 **선택하지 않는 것이 생각할 수 있습니다.**
6. 그래도 이 사용자에게 라이선스를 할당합니다. 같은 페이지에서 제품 라이선스를 **확장하려면 클릭합니다.** 다음을 켜야 합니다.
   - 공용 지역 전화
   - 그런 다음 국내 통화  요금제 또는 국내 및 국제 통화 요금제 중 하나를 **선택해야 합니다.**

     라이선스 할당은 다음과 같습니다.

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > 비즈니스용 Skype 요금제 2는 일반 지역 전화 **라이선스에 포함되어** 있습니다.

자세한 내용은 사용자 [추가를 참조합니다.](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>3단계 - 일반 지역 전화 사용자 계정에 전화 번호 할당

![비즈니스용 Skype 관리 센터를 사용하여 사용자에게 비즈니스용 Skype 로고를 표시하는 아이콘 ](../../images/sfb-logo-30x30.png) 

1. 관리 센터에서 >   >  **비즈니스용 Skype를 관리합니다.**
2. 비즈니스용 **Skype 관리**  >   **센터의 음성** 전화  >  **번호.**
3. 전화 번호 목록에서 번호를 선택하고 할당을 **클릭합니다.**
4. 할당 **페이지의** **음성** 사용자 상자에 전화에 사용되는 사용자의 이름을 입력한 다음 음성 사용자  선택 드롭다운에서 사용자를 선택합니다.
5. 여기에 있는 동안 긴급 주소를 추가해야 합니다. 검색한 후 긴급  주소 선택 아래에서 적합한 주소를 선택합니다.
6. **저장을** 클릭하면 사용자가 다음과 같이 됩니다.

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > 사용자는 전화 시스템 라이선스가  적용된 경우만 표시 됩니다. 방금 이 경우 사용자가 목록에 표시하는 데 약간의 시간이 걸리는 경우도 있습니다.

자세한 내용은 사용자의 전화 번호 [보기를 참조합니다.](/microsoftteams/getting-phone-numbers-for-your-users)

궁금한 경우 다른 통신 사업자 및 "포트"에 있는전화 번호를 옮기거나 Microsoft 365 또는 Office 365로 이전할 수도 있습니다. Teams로 [전화 번호 이전을 참조합니다.](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)

### <a name="step-4---setting-up-your-phone"></a>4단계 - 휴대폰 설정

**휴대폰에서 모드 설정**

일반 지역 전화 모드가 켜져 있어야 하는 전화 또는  전화기입니다. 해당 작업을 확인하여 확인할 수 있습니다.

**Polycom VVX 휴대폰을 설정하는 방법에 대한 예제는 다음과 같습니다.**

- 다음 단계를 수행하여 Polycom VVX에 공통 영역 전화 모드를 사용하도록 설정합니다.
    1. 브라우저에서 CAP 모드를 사용하도록 설정할 수 있도록 웹 인터페이스에 연결합니다.
    2. 그런 다음 설정으로 **이동하여** 비즈니스용 **Skype** 설정 옵션에서 일반 지역 **전화(Common Area Phone)를 선택합니다.**
    3. 예를 **클릭하여** 설정을 저장합니다.

- 이제 CAP 모드를 사용하도록 설정하고 휴대폰의 디스플레이를 사용하여 휴대폰을 설정합니다. 표시에는 **CaAP가 사용하도록 설정되어 있습니다.** 그런 다음, 다음을 합니다.

    1. 설정을 **클릭합니다.**
    2. 고급을 **선택합니다.**
    3. 암호를 입력합니다.
    4. 관리 **설정에서** **일반 영역 전화 설정을 선택합니다.**
    5. **CAP 및** CAP 관리자 모드를 **사용하도록 설정**
    6. [구성 **저장]을 클릭합니다.**

- 이제 휴대폰이 준비되어 홈 화면에서 로그인할 수 있습니다.

    1. 비즈니스용 Skype의 설정  >  **기능을 선택하여**  >  **로그인합니다.**
    2. 사용자 **자격 증명을 선택하고** **CAP(웹** 로그인)를 선택하여 코드를 생성합니다.
    3. [프로비전 포털로 이동하고](https://aka.ms/skypecap)관리자로 **로그인합니다.**
    4. 표시 이름(예: 주 수신)을 입력합니다.

       > [!Note]
       > 공용 **영역 전화 검색만** 선택된 경우 확인란의 선택을 취소하고 다시 검색합니다.

    5. 페어링 코드 창에서 휴대폰에 표시된 코드를 입력하고 프로비전을 **클릭합니다.**

        이 마지막 단계를 수행하면 휴대폰이 자동으로 로그인됩니다.


> [!NOTE]
> CAP 프로비전 사이트는 CAP 계정의 암호를 임의 암호로 다시 설정하게 됩니다. CAP가 참조하는 계정은 AAD(Azure Active Directory) 계정입니다. AAD에서만 계정을 만든 경우 프로세스는 간단합니다. AAD에 On-Premises Active Directory를 동기화하고 타사 IDP 또는 ADFS를 사용하는 경우 CAP 프로비전이 실패합니다. 이 경우 CAP 프로비전이 작동하려면 Microsoft 365 또는 Office 365/Azure Active Directory 계정(예: onmicrosoft.com 도메인이 있는 **계정)만** 사용해야 합니다.


### <a name="related-topics"></a>관련 항목

- 비즈니스용 Skype Online 휴대폰 배포에서 사용 가능한 전화에 [대해 자세히 알아보면 됩니다.](deploying-skype-for-business-online-phones.md)
- [비즈니스용 Skype Online 휴대폰 받기](getting-phones-for-skype-for-business-online.md)


