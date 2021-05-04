---
title: 전화 Microsoft 365 Business Voice 설정
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 조직의 사용자 및 서비스에 Microsoft 365 Business Voice 전화 번호를 설정하는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cec0bc8e55ef6be169de1f48a375ab40ca8ccf7
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130118"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a>2단계: 비즈니스 음성 전화 번호 설정

조직에서 사용자 또는 자동 참석자 를 설정하려면 먼저 해당 사용자에 대한 전화 번호를 얻게 해야 합니다. 전화 번호에는 여러 가지 유형이 있습니다. 그러나 이 단계에서 추가해야 하는 두 가지 유형의 숫자는 다음과 같습니다.

- **서비스 번호** 이러한 숫자는 자동 참석자, 오디오 회의 및 호출 큐에 사용됩니다. 이 번호는 무료 전화 또는 무료 번호일 수 있으며 동시에 많은 양의 통화를 처리할 수 있습니다. 회사 전화 번호는 나중에 자동 담당자에 할당되어 있기 때문에 서비스 번호가 되어야 합니다.
- **구독자 번호** 이러한 숫자는 일반 사용자에게 사용 하여 전화를 걸고 받을 수 있습니다.

> [!IMPORTANT]
> 기존 전화 번호를 사용하려는 경우에도 회사의 주 전화선 및 사용자에게 임시 전화 번호를 만들고 할당해야 합니다. 나중에 이러한 임시 번호를 기존 전화 번호로 바꿀 수 있습니다.

> [!NOTE]
> 새 전화 번호를 사용할 수 있도록 하는 데 몇 시간이 Teams.

## <a name="set-up-a-service-number"></a>서비스 번호 설정

이제 설정한 서비스 번호는 회사의 주 전화 번호에 대한 이후 단계에서 사용됩니다.

1. 관리 센터 Microsoft Teams 로 이동하세요.
2. 왼쪽 탐색에서 Voice   >  전화 번호로 이동한 다음 **추가를 클릭합니다.**
3. 주문 이름을 입력하고 설명을 추가합니다.
4. 위치 및 수량 페이지에서 다음을 합니다.
    1. 국가 **또는 지역에서** 국가 또는 지역을 선택합니다.
    2. 숫자 **형식에서** 다음 옵션 중 하나를 선택합니다.

        - **자동 참석자(Toll)** 일반, 비-무료 전화 번호. 장거리 요금은 발신자에 청구됩니다.
        - **자동 참석자(무료)** 무료(미국 및 캐나다) 또는 무료 전화(영국) 전화 번호입니다. 장거리 요금은 회사에 청구됩니다. 이 옵션을 선택하려면 먼저 통신 크레딧을 구입해야 합니다. 자세한 내용은 사용하려면 구입해야 하는 [Microsoft 365 Business Voice.](what-to-buy.md)

    3. **수량에서** **1 을 선택합니다.**
        > [!NOTE]
        > 이 유형의 더 많은 수를 요청할 수 있는 라이선스가 충분하지 않은 경우 비즈니스 음성 라이선스를 구입한지 확인해야 합니다. 자세한 내용은 사용하려면 구입해야 하는 [Microsoft 365 Business Voice.](what-to-buy.md)
    4. 위치 **아래에서** 긴급 위치 설정 단계에서 만든 위치의 이름을 [입력합니다.](set-up-emergency-locations.md)
    5. 영역 **코드에서** 영역 코드를 선택한 다음 다음을 **클릭하여** 숫자를 선택합니다.
5. 원하는 숫자를 선택합니다. 전화 번호를 선택하고 주문할 수 있는 10분이 있습니다. 10분 이상이면 전화 번호가 번호 풀로 반환됩니다.
6. 주문할 준비가 됐을 때 주문 장소를 **클릭한** 다음 **마쳤습니다.**

## <a name="set-up-phone-numbers-for-your-users"></a>사용자에 대한 전화 번호 설정

1. 관리 센터 Microsoft Teams 로 이동하세요.
2. 왼쪽 탐색에서 Voice   >  전화 번호로 이동한 다음 **추가를 클릭합니다.**
3. 주문 이름을 입력하고 설명을 추가합니다.
4. 위치 및 수량 페이지에서 다음을 합니다.

    1. 국가 **또는 지역에서** 국가 또는 지역을 선택합니다.
    2. 숫자 **형식에서** **사용자(구독자)를 선택합니다.**
    3. 수량 **아래에서** 조직에 대해 원하는 숫자 수를 입력합니다.
    4. 위치 **아래에서** 위치를 선택합니다. 긴급 위치 설정 단계에서 추가한 응급 [](set-up-emergency-locations.md) 위치를 선택하거나 다른 사무실 또는 홈 오피스에 대한 새 위치를 만들어야 하는 경우 위치 추가를 **클릭합니다.**
    5. 영역 **코드에서** 영역 코드를 선택한 다음 다음을 **클릭하여** 숫자를 선택합니다.
5. 원하는 숫자를 선택합니다. 전화 번호를 선택하고 주문할 수 있는 10분이 있습니다. 10분 이상이면 전화 번호가 번호 풀로 반환됩니다.
6. 주문할 준비가 됐을 때 주문 장소를 **클릭한** 다음 을 **마쳤습니다.**

> [!div class="nextstepaction"]
> [다음 단계: 사용자에게 라이선스 Teams 할당](set-up-licenses.md)
