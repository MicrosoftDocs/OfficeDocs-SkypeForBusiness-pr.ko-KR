---
title: 비즈니스용 Skype에서 통화 공원 궤도 범위 만들기 또는 수정
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 비즈니스용 Skype Server Enterprise Voice에서 통화 공원 궤도 범위 테이블을 만들거나 수정 합니다.
ms.openlocfilehash: 305404ce74d3aec26741c0e26b999f6227dabe37
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233683"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>비즈니스용 Skype에서 통화 공원 궤도 범위 만들기 또는 수정

비즈니스용 Skype Server Enterprise Voice에서 통화 공원 궤도 범위 테이블을 만들거나 수정 합니다.

통화 공원는 orbits 통화를 사용 합니다. 사용자가 전화를 걸고 검색할 수 있으려면 통화 공원 표를 구성 해야 합니다. 조직에서 파킹 통화를 위해 예약 하는 내선 번호 범위 (orbits)를 지정 하 고 각 범위에 대 한 통화 공원 풀 핸들을 지정 하 여 해당 범위에 대 한 라우팅을 정의 해야 합니다. 궤도 범위를 정의 하는 경우 orbits 충분 한 회전을 사용 하는 것이 목표는 하지만, 사용자 또는 다른 서비스에 대해 제공 되는 확장 수를 제한 하는 것이 여러 orbits 되지 않도록 하는 것입니다. 통화 공원 응용 프로그램이 배포 된 각 비즈니스용 Skype 서버 풀에 대해 여러 통화 공원 궤도 범위를 만들 수 있습니다. 각 통화 공원 궤도 범위에는 전역 고유 이름과 고유한 확장명 집합이 있어야 합니다.

> [!IMPORTANT]
> 궤도 범위는 일반적으로 100 이하의 orbits를 포함 합니다. 각 범위는 범위 당 최대 1만 orbits 보다 작고 orbits 5만 보다 적은 수의 용량을 보유 한 경우에 한 하 여 훨씬 더 커질 수 있습니다. 범위가 너무 작으면 orbits 보다 빠르게 다시 사용 됩니다.

궤도 범위에 대 한 가상 확장 블록 (사용자 또는 전화 번호를 지정 하지 않은 확장명)을 사용 합니다.

> [!NOTE]
> 직접 연결 된 전화 접속 (연결) 번호를 통화 공원 궤도 테이블의 궤도 번호로 지정 하는 것은 지원 되지 않습니다.

다음 절차 중 하나를 사용 하 여 통화 공원 궤도 범위를 만들거나 수정 합니다.

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>비즈니스용 Skype Server 제어판을 사용 하 여 파킹 통화에 대 한 번호 범위를 만들거나 수정 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 **대리인 설정 사용**을 참조 하세요.

2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.

3. 왼쪽 탐색 모음에서 **음성 기능** 을 클릭 한 다음 **통화 공원**을 클릭 합니다.

4. **통화 공원** 페이지에서 다음 중 하나를 수행 합니다.

   - 새 궤도 범위를 만들려면 **새로**만들기를 클릭 합니다. **이름**에이 숫자 범위에 대 한 식별 이름을 입력 합니다.

     > [!NOTE]
     > 데이터베이스에 궤도 범위를 커밋한 후에는이 이름을 변경할 수 없습니다.

   - 기존 궤도 범위를 수정 하려면 검색 필드에 궤도 범위의 이름 전체 또는 일부를 입력 합니다. Orbits의 결과 목록에서 원하는 궤도를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5. 첫 번째 **숫자 범위** 필드에이 통화 공원 궤도에 대 한 확장 범위의 시작 번호를 입력 하 고 두 번째 **숫자 범위** 필드에 범위의 끝 번호를 입력 합니다. 주의 해야 합니다.

   - 범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.

   - 범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.

   - 궤도 범위는 고유 해야 합니다. 범위가 다른 범위와 겹쳐서는 안 됩니다.

   - 궤도 범위가 문자 \* 또는 번호로 시작 하는 경우 범위는 100 보다 커야 합니다.

   - 유효한 값: 정규식 문자열과 일치 해야 합니다 ([\\* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). 즉, value는 문자 \* 또는 숫자 1부터 9까지 (첫 문자는 0이 될 수 없음)로 시작 하는 문자열 이어야 합니다. 첫 번째 문자가 \* or # 이면 다음 문자는 1부터 9 까지의 숫자 (0이 될 수 없음) 여야 합니다. 이후 문자는 0 ~ 9 개 까지의 추가 문자 (예: "#6000", "\*92000", "\*95551212", "915551212") 일 수 있습니다. 첫 문자 \* 를 입력 하는 경우 첫 번째 문자는 1 ~ 9 (0이 될 수 없음) 다음에 최대 8 자, 즉 각각 0 ~ 9 (예: "915551212", "41212", "300") 여야 합니다.

   - 풀 당 총 5만 orbits를 넘지 않아야 합니다. 일반적으로 각 궤도 범위는 100 개 이하의 orbits에 포함 되지만, 1만 orbits 보다 적은 만큼 더 커질 수 있습니다. 예를 들어 시작 번호를 "7000000"으로, 끝 번호를 "8000000"으로 지정하는 대신 시작 번호를 "7000000"으로, 끝 번호를 "7000100"으로 지정할 수 있습니다.

6. **대상 서버의 fqdn**(정규화 된 도메인 이름) 또는 통화 공원 응용 프로그램을 호스팅하는 응용 프로그램 서비스의 서비스 ID (fqdn)를 클릭 합니다. 궤도 범위의 시작 번호와 끝 번호로 지정 된 범위 내에 있는 모든 통화는이 서버 또는 풀로 라우팅됩니다.

7. **커밋**을 클릭합니다.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 파킹 통화에 대 한 숫자 범위를 만들거나 수정 하려면

1. 비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

3. **New-CsCallParkOrbit** 를 사용 하 여 궤도 번호의 새 범위를 만듭니다. **Set-CsCallParkOrbit** 를 사용 하 여 기존 궤도 번호 범위를 수정 합니다.

    명령줄에서 다음을 실행 합니다.

   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    예를 들면 다음과 같습니다.

   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    다음 예제에서는 기존 궤도 범위에서 숫자를 수정 하는 방법을 보여 줍니다.

   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>참고 항목

[새로운 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[통화 공원 궤도 범위 삭제](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
