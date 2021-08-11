---
title: 공용 영역 라이선스 전화 설정
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: '로비, 수신 공간 및 회의실에 대한 공용 영역 휴대폰을 설정하는 방법에 대해 자세히 알아보기 '
ms.openlocfilehash: 6b97c931364ec9a1c589b0a677e0ec82d6288d945b8f0c002e48824921fe3107
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301054"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>공용 영역 전화 라이선스를 Microsoft Teams
> [!NOTE]
> 공용 영역 전화는 음성메일을 지원하지 않습니다.

일반적인 영역 전화는 일반적으로 로비 또는 전화를 걸 수 있는 다른 영역에 배치됩니다. 예를 들어 수신 영역, 로비 또는 전화 회의 전화가 있습니다. 공용 영역 휴대폰은 공용 영역 라이선스에 묶인 계정으로 전화 있습니다. 또한 휴대폰에 공통 영역 사용자 환경을 하도록 TeamsIPPhone 정책을 적절하게 설정해야 합니다.

아래 단계에서는 조직에 대한 공용 영역 휴대폰을 배포하기 위해 전화 시스템 계정을 설정하는 데 도움이 됩니다. 오디오 회의를 비롯한 보다 완전한 회의실 환경을 위해 회의실 디바이스로 전용 미팅룸 라이선스를 구입하는 것이 고려됩니다. 

먼저 CAP(Common Area 전화) 라이선스를 구입하고 인증된 휴대폰이 있는지 확인해야 합니다. 인증된 휴대폰을 검색하고 자세히 알아보시고자 하는 경우 을 Microsoft Teams [으로 이동합니다.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1) 

## <a name="step-1---buy-the-licenses"></a>1단계 - 라이선스 구매

1. 이 Microsoft 365 관리 센터 청구 서비스로 이동한 다음 다른 요금제  >   **를 확장합니다.**

    ![공용 영역 타일을 보여 전화 스크린샷](media/set-up-common-area-phone-image1.png)

2. 지금 **구입에서 전화**  >  **영역을 선택합니다.**

3. 체크 아웃 페이지에서 지금 **구입을 클릭합니다.**

4. 추가 **기능 구독을 확장한** 다음 클릭하고 통화 요금제 구입을 클릭합니다. 국내 통화  계획 또는 국내 및 국제 통화 계획 **중 하나를 선택 합니다.**

> [!NOTE]
> 시스템 직접 Microsoft 전화 사용하는 경우 통화 계획 라이선스가 필요하지 않습니다.

> [!NOTE]
> 라이선스를 추가할 필요가 전화 시스템 없습니다. 공용 영역 라이선스에 전화 포함되어 있습니다.

라이선스에 대한 자세한 내용은 추가 Microsoft Teams 라이선스를 [참조하세요.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

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



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>2단계 - 휴대폰에 대한 새 사용자 계정 만들기 및 라이선스 할당

1. 이 Microsoft 365 관리 센터 활성 사용자로   >    >  **이동하여 사용자를 추가합니다.**

2. 이름의 "Main"과 같은 사용자 이름과 두 번째 이름의 "수신"을 입력합니다.

3. "Main Reception"처럼 자동으로 자생하지 않는 경우 표시 이름을 입력합니다.

4. "MainReception" 또는 "Mainlobby"같은 사용자 이름을 입력합니다.

5. 공용 영역 휴대폰의 경우 암호를 수동으로 설정하거나 모든 공통 영역 휴대폰에 대해 동일한 암호를 설정해야 할 수 있습니다. 또한 이 사용자가 처음 로그인할 때 암호를 변경하도록 확인란을 **지우는 것이** 생각할 수 있습니다.

6. 사용자에게 라이선스를 할당합니다. 동일한 페이지에서 제품 **라이선스를 확장하려면 를 클릭합니다.** 공용 지역을 켜고 전화 국내 통화  계획 또는 국내 및 국제 전화 요금제 중 하나를 **선택합니다.** 

    ![국내 통화 계획 및 국내 및 국제 계획 옵션이 강조 표시된 라이선스 할당을 보여주는 스크린샷](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> 시스템 직접 Microsoft 전화 사용하는 경우 통화 계획 라이선스를 할당할 필요가 없습니다.

자세한 내용은 사용자에게 [라이선스 할당을 참조하세요.](/microsoft-365/admin/manage/assign-licenses-to-users)

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>3단계 - 공용 영역 사용자 계정에 전화 전화 할당

관리자 Teams 관리 센터를 사용하여 사용자에게 번호를 할당합니다.

1. 관리 Teams 에서 **Voice**  >  **전화 선택합니다.**

3.    전화 번호 목록에서 숫자를 선택하고 **할당을 클릭합니다.**

4. 할당 **페이지에서** 음성 사용자 상자에 전화를 사용할 사용자의 이름을 입력한 다음 음성 사용자 드롭다운  목록에서 사용자를 선택합니다.

5. 다음으로 긴급 주소를 추가해야 합니다. 도시로 **검색,** 설명 검색  **또는** 드롭다운 목록에서 위치 검색을 선택한 다음, 텍스트 상자에 도시, 설명 또는 위치를 입력합니다. 검색하면 긴급 주소  선택 아래에서 적합한 주소를 선택합니다.

6. **저장을** 클릭하고 사용자는 다음과 같이 봐야 합니다.

   ![스크린샷은 샘플 사용자 라이선스 할당을 보여줍니다.](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> 사용자는 라이선스가 적용된 전화 시스템 표시됩니다. 방금 이 경우 사용자가 목록에 표시하는 데 약간의 시간이 걸리는 경우도 있습니다.

자세한 내용은 사용자의 전화 [번호 보기를 참조하세요.](getting-phone-numbers-for-your-users.md)

다른 통신사 및 "포트"에 있는 전화 번호를 찍거나 전화 번호를 Microsoft 365 또는 Office 365. 전화 번호 전송을 [Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
