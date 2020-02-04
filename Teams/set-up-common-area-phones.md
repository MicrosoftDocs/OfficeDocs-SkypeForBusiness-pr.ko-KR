---
title: Microsoft 팀을 위한 공통 영역 전화 라이선스 설정
ms.author: lolaj
author: LolaJacobsen
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
- NOCSH
ms.custom:
- Phone System
description: '로비, 수신 지역 및 회의실에 대 한 공통 영역 전화를 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: f678dba02506672be7176a75a355d606927d76d6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693913"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Microsoft 팀을 위한 공통 영역 전화 라이선스 설정
> [!NOTE]
> 일반 지역 전화는 보이스 메일을 지원 하지 않습니다.

일반적으로 일반적인 지역 전화는 대기실 또는 여러 사람이 전화를 걸 수 있는 다른 영역과 같은 영역에 위치 합니다. 예를 들어 수신 영역, 대기실 또는 전화 회의 전화. 일반적인 지역 전화는 사용자가 아닌 장치로 설정 되며 네트워크에 자동으로 로그인 할 수 있습니다.

아래 단계에서는 전화 시스템의 계정을 설정 하 여 조직의 공통 영역 전화를 배포 하는 방법에 대해 알아봅니다. 오디오 회의를 포함 하 여 더 완벽 한 회의실 환경을 보려면 회의실 장치를 사용 하 여 전용 회의실 라이선스를 구입 하는 것이 좋습니다. 

먼저, 공통 CAP (지역 전화) 라이선스를 구입 하 고 인증 된 전화기를 보유 하 고 있는지 확인 해야 합니다. 인증 된 휴대폰에 대 한 자세한 정보를 검색 하 고 자세한 내용을 보려면 [Microsoft 팀 장치로](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)이동 하세요. 

## <a name="step-1---buy-the-licenses"></a>1 단계-라이선스 구입

1. Microsoft 365 관리 센터에서 **청구** > **구매 서비스로** 이동한 다음 **다른 요금제**를 확장 합니다.

    ![공통 영역 전화 타일을 보여 주는 스크린샷](media/set-up-common-area-phone-image1.png)

2. 지금 **일반 지역 전화** > **구입**을 선택 합니다.

3. 체크 아웃 페이지에서 **지금 구입**을 클릭 합니다.

4. **추가 기능 구독** 을 확장 한 다음을 클릭 하 여 통화 요금제를 구입 합니다. **국내 통화 요금제** 또는 **국내 및 국제 통화 요금제**중 하나를 선택 합니다.

> [!NOTE]
> 전화 시스템 라이선스가 필요 하지 않습니다. 일반 지역 전화 라이선스에 포함 되어 있습니다.

라이선스에 대 한 자세한 내용은 [Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.

일반 지역 전화 라이선스는 다음을 지원 합니다. 


|   |  공통 지역 전화  |
|---------|---------|
|비즈니스용 Skype |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|전화 시스템 |    &#x2714; |
|오디오 회의 |       &#x2718; &sup1  |
|Microsoft Intune |        &#x2718; &sup2 |
|전세계 가용성 |    &#x2714; |
|채널 가용성 |    EA, EAS, CSP, GCC, EES, 웹 다이렉트  |
|      |         |

&sup1 일반 지역 전화는 모임 이끌이가 제공 하는 전화 접속 번호를 통해 오디오 회의에 참가할 수 있습니다.

&sup2 Sovereign 클라우드에서는 사용할 수 없음  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>2 단계-휴대폰에 대 한 새 사용자 계정 만들기 및 라이선스 할당

1. Microsoft 365 관리 센터에서 사용자 > **활성 사용자** > 가 사용자를**추가** **하도록 이동**합니다.

2. 이름에 "Main"과 같은 사용자 이름을 입력 하 고 두 번째 이름에 대해 "수신"을 선택 합니다.

3. "주요 수신"이 자동으로 생성 되지 않는 경우 표시 이름을 입력 합니다.

4. "MainReception" 또는 "Mainreception"와 같은 사용자 이름을 입력 합니다.

5. 일반적인 지역 전화의 경우 암호를 수동으로 설정 하거나 모든 공통 지역 전화에 대해 같은 암호를 사용 하는 것이 좋습니다. 또한 **이 사용자가 처음 로그인 할 때 암호를 변경 하도록 설정** 확인란의 선택을 취소 하는 방법을 고려해 야 할 수 있습니다.

6. 사용자에 게 라이선스를 할당 합니다. 동일한 페이지에서 **제품 라이선스**를 클릭 하 여 확장 합니다. 일반 지역 전화를 켜고 **국내 통화 요금제** 또는 **국내 및 국제 통화 요금제**를 선택 합니다. 

    ![라이선스 할당을 보여 주는 스크린샷](media/set-up-common-area-phone-image2.png)

자세한 내용은 [사용자 추가](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide)를 참조 하세요.

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>3 단계-일반 지역 전화 사용자 계정에 전화 번호 지정

팀 관리 센터를 사용 하 여 사용자에 게 번호를 할당 합니다.

1. 팀 관리 센터에서 **음성** > **전화 번호**를 선택 합니다.

3.  전화 번호 목록에서 번호를 선택 하 고 **할당**을 클릭 합니다.

4. **지정** 페이지의 음성 사용자 상자에 휴대폰을 사용 하는 사용자의 이름을 입력 한 다음 **음성 사용자 선택** 드롭다운 목록에서 사용자를 선택 합니다.

5. 다음으로 긴급 주소를 추가 해야 합니다. **도시별로 검색**, **설명으로 검색**또는 드롭다운 목록에서 **위치를 기준으로 검색** 을 선택 하 고 텍스트 상자에 구/군/시, 설명 또는 위치를 입력 합니다. 검색 하 고 나 서 **긴급 주소 선택** 에서 바로 확인을 클릭 하 여 적절 하 게 선택 합니다.

6. **저장** 을 클릭 하면 사용자에 게 다음과 같은 모양이 표시 됩니다.

   ![라이선스 할당을 보여 주는 스크린샷](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> 사용자에 게 전화 시스템 라이선스가 적용 된 경우에만 표시 됩니다. 방금이 작업을 수행한 경우 사용자가 목록에 표시 되는 데 약간의 시간이 걸릴 수 있습니다.

자세한 내용은 [사용자의 전화 번호 가져오기를](getting-phone-numbers-for-your-users.md)참조 하세요.

다른 통신 회사와 "포트"를 사용 하 여 전화 번호를 가져와 Office 365으로 양도할 수도 있습니다. [팀에 전화 번호 전송을](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)참조 하세요.


