---
title: 공통 지역 전화 설정
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
description: 올바른 펌웨어를 얻고, 필요한 경우 업데이트 하 고, 라이선스를 할당 하 고, 공통 지역 전화에 대 한 설정을 구성 하는 배포 단계를 알아보세요.
ms.openlocfilehash: 02cab34b4a1f220e8f28ceeee794470191582704
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220408"
---
# <a name="set-up-common-area-phones"></a>공통 지역 전화 설정
일반적으로 일반 지역 전화 (CAP)는 일부 사용자가 사용할 수 있는 대기실 또는 다른 영역 등의 영역에 배치 됩니다. 예를 들어 수신 지역 전화, 문 휴대폰 또는 회의실 전화, Cap는 사용자가 아닌 장치로 설정 되며 네트워크에 자동으로 로그인 됩니다. 아래 단계에서는 전화 요금제를 사용 하 여 회사에 대 한 이러한 유형의 전화를 배포할 수 있도록 전화 시스템 계정을 설정 하는 방법에 대해 알아봅니다.

## <a name="prerequisites-for-common-area-phones"></a>공통 지역 전화의 전제 조건

가장 먼저 할 일은 다음이 있는지 확인 하는 것입니다.

- 일반적인 지역 전화 라이선스와 통화 요금제를 구입 합니다.
- 승인 된 전화를 검색 하 고 구입 합니다 ( [여기](deploying-skype-for-business-online-phones.md)에서 목록 보기).
- 휴대폰의 펌웨어를 업데이트 합니다 ( [이 항목의](getting-phones-for-skype-for-business-online.md)지원 되는 펌웨어 참조).  다음과 같은 방법으로 휴대폰에서 펌웨어를 확인할 수 있습니다.
  - **Polycom vvx 휴대폰**: **설정**  >  **상태**  >  **플랫폼**  >  **응용 프로그램**  >  **메인**으로 이동 합니다.
  - **옛 alink 휴대폰**: 메인 전화 화면에서 **상태로** 이동 합니다.
  - **오디오 코드 전화**: **Menu**  >  시작 화면에서 메뉴**디바이스 상태**  >  **펌웨어 버전** 으로 이동 합니다.
  - **Lpe (Lync Phone Edition) 전화**: **Menu**  >  시작 화면에서 메뉴**시스템 정보** 로 이동 합니다.

    펌웨어 업데이트는 비즈니스용 Skype 서비스에서 관리 합니다. 모든 비즈니스용 Skype 인증 휴대폰의 펌웨어가 비즈니스용 Skype 업데이트 서버에 업로드 되며 기본적으로 모든 전화기에서 장치 업데이트를 사용할 수 있습니다.

    휴대폰 및 폴링 간격의 비활성 시간에 따라 전화는 자동으로 최신 인증 된 빌드를 다운로드 하 고 설치 합니다. [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet을 사용 하 고 *enabledeviceupdate* 매개 변수를로 설정 하 여 장치 업데이트 설정을 사용 하지 않도록 설정할 수 있습니다 `false` .

## <a name="setting-up-a-common-area-phone"></a>공통 지역 전화 설정
다음 단계를 수행 해야 합니다.

### <a name="step-1---buy-the-licenses"></a>1 단계-라이선스 구입
1. 관리 센터에서 **청구**  >  **구매 서비스로**이동 하 고 **다른 요금제**를 추가 합니다.

    ![CAP-license](../../images/cap-license.png)
2. **일반 지역 전화**  >  **구입** 을 클릭 하세요. **체크 아웃** 페이지의 **지금 구입**을 클릭 >.
3. **추가 기능 구독** 을 확장 하려면 on을 클릭 한 다음 통화 요금제를 구입 하려면을 클릭 합니다. **국내 통화 요금제** 또는 **국내 및 국제 통화 요금제**중 하나를 선택 합니다.

> [!Note]
> 전화 시스템 라이선스가 필요 하지 않습니다. **일반 지역 전화** 라이선스에 포함 되어 있습니다.

라이선스에 대 한 자세한 내용은 [비즈니스용 Skype 및 Microsoft 팀 추가 기능 라이선스](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)를 참조 하세요.

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>2 단계-휴대폰에 대 한 새 사용자 계정 만들기 및 라이선스 할당
1. 관리 센터 **에서 사용자**  >  **활성 사용자**를 추가할 사용자로 이동  >  **Add a user**합니다.
2. 이름에 "Main"과 같은 **사용자 이름을** 사용 하 고 두 번째 이름에는 "수신"을 붙여 넣으십시오.
3. "주요 수신"과 같이 자동으로 생성 되지 않는 경우 **표시 이름을** 둡니다.
4. "MainReception" 또는 "Mainreception"와 같은 **사용자 이름을** 넣으십시오.
5. 일반적인 지역 전화의 경우 암호를 수동으로 설정 하거나 모든 공통 지역 전화에 대해 같은 암호를 사용 하는 것이 좋습니다. 또한 선택을 취소 하는 **경우이 사용자가 처음 로그인 할 때 암호를 변경**하는 것을 고려해 야 할 수 있습니다.
6. 아직도 있으면이 사용자에 게 라이선스를 할당 합니다. 동일한 페이지에서 **제품 라이선스**를 클릭 하 여 확장 합니다. 다음을 설정 합니다.
   - 공통 지역 전화
   - 그런 다음 **국내 통화 요금제** 나 국내 및 **국제 통화 요금제**중 하나를 선택 해야 합니다.

     라이선스 할당에는 다음과 같은 모양이 표시 됩니다.

     ![TurnOnCapLicense](../../images/cap-license-turn-on.png)

     > [!Note]
     > 이에 대 한 자세한 내용은 비즈니스용 Skype 요금제 2가 **일반 지역 전화** 라이선스에 포함 되어 있습니다.

자세한 내용은 [사용자 추가](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)를 참조 하세요.

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>3 단계-일반 지역 전화 사용자 계정에 전화 번호 지정

![비즈니스용 skype 로고를 표시 하는 아이콘은 비즈니스용 ](../../images/sfb-logo-30x30.png) **skype 관리 센터** 를 사용 하 여 사용자에 게 전화 번호를 지정 합니다.

1. 관리 센터 > **관리**센터에서  >  **비즈니스용 Skype를 사용할**경우
2. **비즈니스용 Skype 관리 센터**의  >   **음성**  >  **전화 번호**.
3. 전화 번호 목록에서 번호를 선택 하 고 **할당**을 클릭 합니다.
4. **지정** 페이지의 **음성 사용자** 상자에 휴대폰에 사용 되는 사용자의 이름을 입력 한 다음 **음성 사용자 선택** 드롭다운에서 사용자를 선택 합니다.
5. 여기서 긴급 주소를 추가 해야 합니다. 검색을 마치면 **긴급 주소 선택** 아래에서 원하는 항목을 바로 확인 하세요.
6. **저장** 을 클릭 하면 사용자에 게 다음과 같은 모양이 표시 됩니다.

    ![cap-user-number](../../images/cap-user-number.png)

   > [!Note]
   > 사용자에 게 **전화 시스템** 라이선스가 적용 된 경우에만 표시 됩니다. 방금이 작업을 수행한 경우 사용자가 목록에 표시 되는 데 약간의 시간이 걸릴 수 있습니다.

자세한 내용은 [사용자의 전화 번호 가져오기를](/microsoftteams/getting-phone-numbers-for-your-users)참조 하세요.

다른 통신 회사와 "*포트*"를 사용 하 여 전화 번호를 받아 Microsoft 365 또는 Office 365에 전송할 수도 있습니다. [전화 번호를 팀에 게 양도](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)를 참조 하세요.

### <a name="step-4---setting-up-your-phone"></a>4 단계-휴대폰 설정

**휴대폰에서 모드 설정**

휴대폰 이나 전화기에는 **공통 영역 전화 모드가** 켜져 있어야 합니다. 이 작업을 수행할 수 있는지 확인 합니다.

**다음은 Polycom VVX 휴대폰을 설정 하는 방법의 예입니다.**

- 다음 단계에 따라 Polycom VVX에 대해 공통 영역 전화 모드를 사용 하도록 설정 합니다.
    1. 브라우저에서 CAP 모드를 사용할 수 있도록 웹 인터페이스에 연결 합니다.
    2. 그런 다음, **설정** 으로 이동 하 여 **비즈니스용 Skype 설정** 옵션에서 **일반 지역 전화**를 선택 합니다.
    3. **예** 를 클릭 하 여 설정을 저장 합니다.

- 이제 CAP 모드가 활성화 되 면 휴대폰 디스플레이를 사용 하 여 전화를 설정 합니다. 표시에는 **Caap가 사용 하도록 설정 되어**표시 되어야 합니다. 그런 후 다음을 수행 합니다.

    1. **설정을**클릭 합니다.
    2. **고급**을 선택 합니다.
    3. 비밀 번호를 입력 합니다.
    4. **관리 설정**에서 **일반 영역 전화 설정을**선택 합니다.
    5. **Cap** 및 **cap 관리 모드**를 사용 하도록 설정 합니다.
    6. **구성 저장**을 클릭 합니다.

- 이제 휴대폰을 사용할 준비가 되어 홈 화면에서 로그인 할 수 있습니다.

    1. **Settings**  >  **Features**  >  **비즈니스용 Skype의** 설정 기능을 선택 하 여 로그인 합니다.
    2. **사용자 자격 증명**을 선택 하 고 **웹 로그인 (CAP)** 을 선택 하 여 코드를 생성 합니다.
    3. [프로 비전 포털로](https://aka.ms/skypecap)이동 하 고 **관리자로**로그인 합니다.
    4. 표시 이름 (예: 메인 수신)을 입력 합니다.

       > [!Note]
       > **공용 지역 전화만 검색** 을 선택 하는 경우 확인란을 선택 취소 하 고 다시 검색 합니다.

    5. 페어링 코드 창에서 휴대폰에 표시 되는 코드를 입력 하 고 **프로 비전**을 클릭 합니다.

        이 마지막 단계를 따라 휴대폰에서 자동으로 로그인 해야 합니다.


> [!NOTE]
> CAP 프로비저닝 사이트 상태에서는 CAP 계정의 암호가 임의 암호로 재설정 됩니다. CAP가 참조 하는 계정이 Azure Active Directory (AAD) 계정이 된다는 점에 유의 하세요. AAD 에서만 계정을 만든 경우 프로세스는 간단 합니다. 온-프레미스 Active Directory를 AAD에 동기화 하 고 타사 IDP 또는 ADFS를 사용 하는 경우 CAP 프로비저닝이 실패 합니다. 이 경우 CAP 프로비저닝이 작동 하려면 Microsoft 365 또는 Office 365/Azure Active Directory 계정 (예: **onmicrosoft.com** 도메인을 사용 하는 계정)만 사용 해야 합니다.


### <a name="related-topics"></a>관련 항목

- [비즈니스용 Skype Online 휴대폰을 구축할](deploying-skype-for-business-online-phones.md)때 사용 가능한 전화에 대해 자세히 알아보세요.
- [비즈니스용 Skype Online 휴대폰 받기](getting-phones-for-skype-for-business-online.md)


