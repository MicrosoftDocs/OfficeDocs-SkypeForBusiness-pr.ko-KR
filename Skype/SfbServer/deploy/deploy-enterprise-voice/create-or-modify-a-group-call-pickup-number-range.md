---
title: 비즈니스용 Skype에서 그룹 통화 픽업 번호 범위 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 비즈니스용 Skype Server Enterprise Voice에서 그룹 통화 픽업 번호 범위를 만들거나 수정 합니다.
ms.openlocfilehash: 3098d7cf1554586dd2fd2ace934682ae58a90489
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233680"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>비즈니스용 Skype에서 그룹 통화 픽업 번호 범위 만들기 또는 수정

비즈니스용 Skype Server Enterprise Voice에서 그룹 통화 픽업 번호 범위를 만들거나 수정 합니다.

그룹 통화 픽업는 통화 공원 응용 프로그램을 기반으로 합니다. 그룹 통화 픽업을 배포 하는 경우 통화 픽업 그룹 번호로 지정 된 전화 번호 범위를 사용 하 여 통화 공원 궤도 테이블을 구성 해야 합니다. 이러한 그룹 번호는 다른 사용자에 게 연결 되는 통화를 선택 하기 위해 사용자가 전화를 거는 번호입니다.

통화 공원 번호와 같은 통화 픽업 그룹 번호는 사용자 또는 전화가 할당 되지 않은 가상 확장명 이어야 합니다. 그룹 통화 픽업을 배포 하는 각 프런트 엔드 풀에는 하나 이상의 통화 픽업 그룹 번호 범위가 포함 될 수 있습니다. 그룹 번호 범위는 배포에서 전역적으로 고유 해야 하며 **Grouppickup** 유형으로 할당 해야 합니다.

통화 공원 표에서 통화 픽업 그룹 번호 범위를 만들거나 수정 하려면 다음 절차를 사용 합니다.

> [!NOTE]
> 통화 공원 궤도 테이블에서 그룹 통화 픽업 번호 범위를 만들고, 수정 하 고, 제거 하 고, 표시 하려면 비즈니스용 Skype Server Management Shell을 사용 해야 합니다. 비즈니스용 Skype Server 제어판에서는 그룹 통화 픽업 번호 범위를 사용할 수 없습니다.

통화 픽업 그룹 번호 범위는 다음 규칙을 준수 해야 합니다.

- 범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.

- 범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.

- 번호 범위는 고유해야 합니다. 범위가 다른 범위와 겹쳐서는 안 됩니다.

- 숫자 범위가 문자로 \* 시작 하는 경우 범위는 100 보다 커야 합니다.

- 유효한 값: 정규식 문자열과 일치 해야 합니다 ([\\* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). 즉, value는 문자 \* 또는 숫자 1부터 9까지 (첫 문자는 0이 될 수 없음)로 시작 하는 문자열 이어야 합니다. 첫 번째 문자가 \* or # 이면 다음 문자는 1부터 9 까지의 숫자 (0이 될 수 없음) 여야 합니다. 이후 문자는 0 ~ 9 개 까지의 추가 문자 (예: "#6000", "\*92000", "\*95551212", "915551212") 일 수 있습니다. 첫 문자 \* 를 입력 하는 경우 첫 번째 문자는 1 ~ 9 (0이 될 수 없음) 다음에 최대 8 자, 즉 각각 0 ~ 9 (예: "915551212", "41212", "300") 여야 합니다.

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>통화 픽업 그룹 범위를 만들거나 수정 하려면

1. 비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

3. **New-CsCallParkOrbit** 를 사용 하 여 통화 픽업 그룹 번호의 새 범위를 만듭니다. **Set-CsCallParkOrbit** 를 사용 하 여 기존 통화 픽업 번호 범위를 수정 합니다.

    명령줄에서 다음을 실행 합니다.

   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    예를 들면 다음과 같습니다.

   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    다음 예제에서는 통화 공원 orbits에서 pickup 그룹으로 숫자 범위를 변경 하는 방법을 보여 줍니다.

   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > 이 cmdlet을 사용 하 여 처음에 잘못 된 유형을 지정 하 고 그룹 범위가 아직 사용 되지 않은 경우에만 숫자 범위에 할당 된 유형을 변경할 수 있습니다. 번호 범위를 CallPark에서 GroupPickup으로 변경 하거나 그 반대의 경우 또는 그 반대로, 그리고 해당 번호 범위를 이미 사용 중인 경우에는 통화 공원 또는 그룹 통화 픽업이 해당 번호 범위에 대해 작동을 중지 합니다. 예를 들어, 번호 범위를 CallPark에서 GroupPick로 변경 하면 통화 공원 응용 프로그램이 더 이상 통화를 파킹 하기 위해 해당 orbits 범위를 사용할 수 없습니다.

## <a name="see-also"></a>참고 항목

[새로운 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[통화 공원 궤도 범위 삭제](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
