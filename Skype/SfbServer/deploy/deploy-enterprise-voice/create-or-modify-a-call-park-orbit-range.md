---
title: 통화 파크 궤도 범위를 만들거나 수정하는 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 통화 파크 궤도 범위 테이블을 만들거나 수정하는 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 8a283ee9fd63a9c034385821d397d54156da9ba9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581102"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>통화 파크 궤도 범위를 만들거나 수정하는 비즈니스용 Skype

통화 파크 궤도 범위 테이블을 만들거나 수정하는 비즈니스용 Skype 서버 Enterprise Voice.

통화 파킹된 통화는 통화를 파킹하는 데 파킹된 통화를 사용하는 파킹된 통화입니다. 사용자가 통화를 파기하고 검색하려면 먼저 통화 파크 파크 파선 테이블을 구성해야 합니다. 조직에서 통화를 파킹하기 위해 예약할 내선 번호 범위(파킹된 통화 번호)를 지정하고 각 범위를 처리하는 통화 파킹 풀을 지정하여 해당 범위에 대한 라우팅을 정의해야 합니다. 궤도 범위를 정의할 때 목표는 하나의 궤도를 너무 빨리 다시 사용할 수 없는 충분한 궤도를 가지지만, 사용자 또는 기타 서비스에 사용할 수 있는 내선 번호 수를 제한하는 것이 목표입니다. 통화 파크 응용 프로그램이 배포된 각 풀에 대해 여러 통화 비즈니스용 Skype 서버 만들 수 있습니다. 각 통화 파크 파크 파선 범위에는 전역적으로 고유한 이름과 고유한 내선이 있어야 합니다.

> [!IMPORTANT]
> 궤도 범위에는 일반적으로 100 이하의 궤도가 있습니다. 범위당 최대 10,000개 궤도보다 작고 풀당 50,000개 미만인 경우 각 범위는 훨씬 클 수 있습니다. 범위가 너무 작을 경우 궤도는 더 빠르게 다시 사용됩니다.

궤도 범위에 가상 내선 번호 블록(사용자 또는 전화가 할당되지 않은 내선 번호)을 사용 합니다.

> [!NOTE]
> DID(Direct Inward Dialing) 번호를 통화 파킹된 통화 번호 테이블의 파킹된 통화 번호 번호로 할당하는 것은 지원되지 않습니다.

다음 절차 중 하나를 사용하여 통화 대기 번호 범위를 만들거나 수정할 수 있습니다.

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>제어판을 비즈니스용 Skype 서버 사용하여 통화를 파킹된 통화에 사용할 번호 범위를 만들거나 수정하려면

1. RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다. 자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3. 왼쪽 탐색 모음에서 **음성 기능** 을 클릭하고 **통화 대기** 를 클릭합니다.

4. **통화 대기** 페이지에서 다음 중 하나를 수행합니다.

   - 새 번호 범위를 만들려면 **새로 만들기** 를 클릭합니다. **이름** 에 이 번호 범위에 대한 식별 이름을 입력합니다.

     > [!NOTE]
     > 번호 범위를 데이터베이스에 커밋하고 나면 이 이름을 변경할 수 없습니다.

   - 기존 번호 범위를 수정하려면 검색 필드에 번호 범위의 이름 전체 또는 일부를 입력합니다. 결과로 표시된 번호 목록에서 원하는 번호를 클릭하고 **편집** 을 클릭한 후 **세부 정보 표시** 를 클릭합니다.

5. 첫 번째 **번호 범위** 필드에는 이 통화 대기 파킹된 통화 번호에 대한 내선 번호 범위의 시작 번호를 입력하고, 두 번째 **번호 범위** 필드에는 해당 범위의 끝 번호를 입력합니다. 유의해야 합니다.

   - 범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.

   - 범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.

   - 파킹된 통화 번호 범위는 고유해야 하며, 다른 범위와 겹칠 수 없습니다.

   - 번호 범위가 문자 또는 #으로 시작하는 경우 범위는 \* 100보다 커야 합니다.

   - 유효한 값: 정규식 문자열([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). 즉, 값은 문자나 #으로 시작되는 문자열 또는 1에서 9까지의 숫자(첫 번째 문자는 \* 0일 수 없습니다.)입니다. 첫 문자가 또는 #이면 다음 문자는 1에서 9까지의 숫자가 되어야 합니다. 0이 될 \* 수 없습니다. 이후 문자는 "#6000", \* "92000", "95551212" 및 "915551212")까지 0에서 9까지의 숫자를 사용할 수 \* 있습니다. 첫 번째 문자가 또는 #이면 첫 번째 문자는 1에서 9까지의 숫자가 되어야 합니다(0일 수 없습니다). 그 다음에 숫자 0에서 9까지의 숫자를 입력할 수 \* 있습니다(예: "915551212", "41212", "300").

   - 풀당 파킹된 통화 번호는 5만 개까지 포함할 수 있습니다. 각 파킹된 통화 번호 범위에는 일반적으로 100개 이하의 파킹된 통화 번호가 포함되지만, 그보다 훨씬 커질 수도 있습니다(1만 개 이하의 파킹된 통화 번호 포함). 예를 들어 시작 번호를 "7000000"로, 끝 번호를 "8000000"으로 지정하는 대신 시작 번호를 "7000000"로, 끝 번호를 "7000100"으로 지정할 수 있습니다.

6. **대상 서버의 FQDN** 에서 통화 대기 응용 프로그램을 호스팅하는 응용 프로그램 서비스의 FQDN(정규화된 도메인 이름) 또는 서비스 ID를 클릭합니다. 파킹된 통화 번호 범위의 시작 번호 및 끝 번호에 의해 지정된 범위 내의 번호에 대기된 모든 통화는 이 서버나 풀로 라우팅됩니다.

7. **커밋** 을 클릭합니다.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>관리 비즈니스용 Skype 서버 셸을 사용하여 통화를 파킹하기 위한 번호 범위를 만들거나 수정하려면

1. 비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치되거나 설치 권한 위임에 설명된 필요한 사용자 권한으로 컴퓨터에 **로그온합니다.**

2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

3. 번호의 새 범위를 만들려면 **New-CsCallParkOrbit** 를 사용합니다. 번호의 기존 범위를 수정하려면 **Set-CsCallParkOrbit** 를 사용합니다.

    명령줄에서 다음을 실행합니다.

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    예:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    다음 예에서는 기존 번호 범위의 번호를 수정하는 방법을 보여줍니다.

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>참고 항목

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[통화 대기 파킹된 통화 번호 범위 삭제](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)