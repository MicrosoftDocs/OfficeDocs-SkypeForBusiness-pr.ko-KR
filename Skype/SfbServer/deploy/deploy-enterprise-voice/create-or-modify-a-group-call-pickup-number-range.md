---
title: 그룹 통화 선택 번호 범위를 만들거나 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 그룹 통화 선택 번호 범위를 만들거나 수정하는 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 73c2c0b74c27fd59d94d97c5ee05e0da88219601e839d42dc12e0ec659db0aa3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307879"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>그룹 통화 선택 번호 범위를 만들거나 비즈니스용 Skype

그룹 통화 선택 번호 범위를 만들거나 수정하는 비즈니스용 Skype 서버 Enterprise Voice.

그룹 통화 Pickup은 통화 파크 응용 프로그램을 기반으로 합니다. 그룹 통화 Pickup을 배포할 때 통화 Pickup 그룹 번호로 지정된 전화 번호 범위로 통화 파크 파크 번호 테이블을 구성해야 합니다. 이러한 그룹 번호는 사용자가 다른 사용자를 위해 울리는 전화를 걸기 위해 전화를 걸 수 있는 번호입니다.

통화 파크 파노라마 번호와 마찬가지로 통화 Pickup 그룹 번호는 사용자에게 할당된 사용자 또는 전화가 없는 가상 내선 번호가 아니어도 됩니다. 그룹 통화 선택을 배포하는 각 프런트 엔드 풀에는 하나 이상의 통화 Pickup 그룹 번호 범위가 있습니다. 그룹 번호 범위는 배포에서 전역적으로 고유해야 하며 **GroupPickup** 유형으로 할당해야 합니다.

다음 절차에 따라 통화 파크 통화 번호 테이블에서 통화 Pickup 그룹 번호 범위를 만들거나 수정합니다.

> [!NOTE]
> 통화 파크 비즈니스용 Skype 서버 표에서 그룹 통화 선택 번호 범위를 만들고, 수정하고, 제거하고, 보기 위해 관리 셸을 사용해야 합니다. 그룹 통화 선택 번호 범위는 제어판에서 사용할 비즈니스용 Skype 서버 없습니다.

통화 Pickup 그룹 번호 범위는 다음 규칙을 준수해야 합니다.

- 범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.

- 범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.

- 번호 범위는 고유해야 합니다. 이 범위는 다른 범위와 겹칠 수 없습니다.

- 숫자 범위가 문자나 #로 시작하는 경우 범위는 \* 100보다 커야 합니다.

- 유효한 값: 정규식 문자열([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). 즉, 값은 문자나 #으로 시작되는 문자열 또는 1에서 9까지의 숫자(첫 번째 문자는 \* 0일 수 없습니다.)입니다. 첫 문자가 또는 #이면 다음 문자는 1에서 9까지의 숫자가 되어야 합니다. 0이 될 \* 수 없습니다. 이후 문자는 "#6000", \* "92000", "95551212" 및 "915551212")까지 0에서 9까지의 숫자를 사용할 수 \* 있습니다. 첫 번째 문자가 또는 #이면 첫 번째 문자는 1에서 9까지의 숫자가 되어야 합니다(0일 수 없습니다). 그 다음에 숫자 0에서 9까지의 숫자를 입력할 수 \* 있습니다(예: "915551212", "41212", "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>통화 Pickup 그룹 범위를 만들거나 수정하려면

1. 비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치되거나 설치 권한 위임에 설명된 필요한 사용자 권한으로 컴퓨터에 **로그온합니다.**

2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

3. **New-CsCallParkOrbit을** 사용하여 새 통화 선택 그룹 번호 범위를 만들 수 있습니다. **Set-CsCallParkOrbit을** 사용하여 기존 통화 선택 번호 범위를 수정할 수 있습니다.

    명령줄에서 다음을 실행합니다.

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    예를 들면 다음과 같습니다.

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    다음 예에서는 통화 파크 궤도에서 통화 Pickup 그룹으로 번호 범위를 변경하는 방법을 보여 제공합니다.

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > 이 cmdlet을 사용하여 처음에 잘못된 형식을 지정하고 그룹 범위가 아직 사용되지 않은 경우 번호 범위에 할당된 유형을 변경할 수 있습니다. 번호 범위를 CallPark에서 GroupPickup으로 변경하거나 그 반대로 변경하고 번호 범위가 이미 사용 중이면 통화 파킹 또는 그룹 통화 Pickup이 해당 번호 범위에 대해 작동하지 않습니다. 예를 들어 번호 범위를 CallPark에서 GroupPick으로 변경하는 경우 통화 파킹 응용 프로그램은 더 이상 해당 파킹된 통화 번호 범위를 사용하여 통화를 파킹할 수 없습니다.

## <a name="see-also"></a>참고 항목

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[통화 대기 파킹된 통화 번호 범위 삭제](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)