---
title: 공존 시나리오에서 Lync Server 2010 관리 팩 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159aaa55e61068356701abaed3c0a67a60265c75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>공존 시나리오에서 Lync Server 2010 관리 팩 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

대부분의 고객은 사용자가 Microsoft Lync Server 2010에서 Lync Server 2013로 점진적으로 마이그레이션되는 기업 내에 출시 프로그램을 채택 하 고 있습니다. 이러한 회사의 관리자는 모든 최종 사용자가 최상의 통신 환경을 제공 하도록 하기 위해 두 버전의 Lync Server를 모니터링 하는 데 신경을 써야 합니다. 이 시나리오에서는 Lync Server 2013 관리 팩이 Lync Server 2010 관리 팩과 함께 나란히 마이그레이션 경로를 지원 합니다.

Lync Server 2010에서 중앙 관리 저장소와 함께 저장 된 토폴로지 문서를 통해 Lync Server 컴퓨터를 검색 했습니다. 이 구성에서 단일 컴퓨터는 다른 모든 Lync Server 컴퓨터의 존재를 보고 합니다.

Lync Server 2013의 관리 팩은 이제 Lync Server 2010에서 사용 된 중앙 검색 메커니즘 대신 컴퓨터 수준 검색을 사용 합니다. 즉, 각 System Center 에이전트는 본질적으로 자체를 검색 하 고 System Center Operations Manager에 대 한 존재를 보고 합니다. 컴퓨터 수준 검색을 사용 하 여 시스템 센터 인프라의 관리를 간소화 하 고 lync server 관리 팩 (예: lync server 2010 및 Lync Server 2013 관리 팩 용 관리 팩)을 사용 하도록 설정 합니다. 더 쉽게 공존할 수 있습니다.

이 마이그레이션을 지원 하려면 먼저 기존 Lync Server 2010 모니터링을 업그레이드 하 여 범위 간격을 방지 해야 합니다. 이렇게 하려면 중앙 관리 저장소를 Lync Server 2013로 업그레이드 하기 전에 Lync server 2010에 대 한 중앙 검색 스크립트를 서비스 하기 위해 기존 Lync Server 2010 컴퓨터를 먼저 시작 합니다. 4 단계 프로세스입니다.

1.  Lync Server 2010 관리 팩을 누적 업데이트 7로 업그레이드 합니다.

2.  중앙 검색 스크립트를 실행 하도록 Lync Server 2010 컴퓨터에 지시 합니다.

3.  Microsoft Lync Server 2010 관리 팩의 중앙 검색 후보를 재정의 합니다.

4.  새로운 중앙 검색 후보가 검색 되었는지 확인 합니다.

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>Lync Server 2010 컴퓨터에 중앙 검색 스크립트를 실행 하도록 지시

중앙 검색을 처리 하기 위해 중앙 집중화 되지 않은 관리 저장소 컴퓨터 (예: Lync Server 프런트 엔드) 서버를 지명할 중앙 집중화 되지 않은 관리 저장소 서버에 다음 레지스트리 키를 만들어야 합니다.

HKLM\\소프트웨어\\Microsoft\\실시간 통신\\상태\\CentralDiscoveryCandidate

다음 절차를 완료 하 여이 레지스트리 키를 만들 수 있습니다.

1.  **시작** 을 클릭 한 다음 **실행**을 클릭 합니다.

2.  **실행** 대화 상자에서 **regedit** 를 입력 한 다음 enter 키를 누릅니다.

3.  레지스트리 편집기에서 **\_HKEY LOCAL\_MACHINE**을 확장 하 고 **소프트웨어**를 확장 한 다음 **Microsoft**를 확장 하 고 **실시간 통신**을 확장 합니다.

4.  **상태**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 클릭 한 다음 **키**를 클릭 합니다. **상태** 키가 없는 경우 **실시간 통신**을 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **키**를 클릭 합니다. 새 키가 만들어지면 체력을 입력 한 다음 enter 키를 누릅니다.
    
    새 키를 만든 후 **CentralDiscoveryCandidate** 를 입력 하 고 enter 키를 눌러 키의 이름을 바꿉니다.

이 변경 사항을 적용 하는 데 몇 시간이 걸릴 수 있습니다. 변경 내용이 즉시 적용 되도록 하려면 상태 에이전트 서비스를 중지 한 다음 다시 시작 합니다. 상태 에이전트 서비스를 다시 시작 하려면 Lync Server 2010 컴퓨터에서 다음 절차를 완료 합니다.

1.  **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **보조 프로그램**을 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.

2.  콘솔 창에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Net stop HealthService

3.  "System Center 관리 서비스를 중지 하 고 있습니다" 라는 메시지가 표시 되 고 그 뒤에 서비스가 중지 되었음을 알려 주는 두 번째 메시지가 나타납니다. 서비스가 중단 되 면 다음 명령을 입력 하 고 ENTER 키를 눌러 다시 시작할 수 있습니다.
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Lync Server 2010 관리 팩의 중앙 검색 후보 재정의

Lync server 2010 컴퓨터에서 Lync Server 2010 컴퓨터를 보고 하도록 설정한 후에는 Lync Server 2010 관리 팩에이 변경 사항에 대 한 정보를 알려 주어 야 합니다. 이렇게 하려면 관리 팩에서 재정의를 만들어야 합니다. 다음 절차를 완료 하 여이 작업을 수행할 수 있습니다.

1.  Operations Manager 콘솔에서 **작성**을 클릭 합니다.

2.  제작 탭에서 **관리 팩 개체**를 확장 하 고 **개체**검색을 클릭 한 다음 **범위**를 클릭 합니다.

3.  **범위 관리 팩 개체** 대화 상자에서 대상 **LS 검색 후보가** 있는 항목을 선택한 다음 **확인**을 클릭 합니다. LS 검색 후보는 Lync Server 2010 관리 팩을 설치한 경우에만 표시 됨을 참고 하세요.

4.  Operations Manager 콘솔에서 **Ls 검색 후보**를 마우스 오른쪽 단추로 클릭 하 고 **재정의**를 가리킨 다음 **개체 검색 재정의**를 가리킨 다음 **Class: LS 검색 후보의 모든 개체를**클릭 합니다.

5.  **속성 재정의** 대화 상자에서 매개 변수 **중앙 검색 WatcherNode Fqdn**옆에 있는 **재정의** 확인란을 선택 합니다. 값 및 **유효 값** **다시 정의** 상자에 Lync Server 2010 컴퓨터의 정규화 된 도메인 이름을 입력 합니다. **적용** 확인란을 선택 하 고 **확인**을 클릭 합니다.

재정의를 만든 후 루트 관리 서버에서 상태 서비스를 다시 시작 해야 합니다. 상태 서비스를 다시 시작 하려면 루트 관리 서버에서 다음 절차를 완료 합니다.

1.  **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **보조 프로그램**을 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.

2.  콘솔 창에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Net stop HealthService

3.  "System Center 관리 서비스를 중지 하 고 있습니다" 라는 메시지가 표시 되 고 서비스가 중지 되었음을 알리는 두 번째 메시지가 나타납니다. 서비스가 중단 되 면 다음 명령을 입력 하 고 ENTER 키를 눌러 다시 시작할 수 있습니다.
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>새 중앙 검색 후보가 검색 되었는지 확인

중앙 관리 저장소를 업그레이드 하기 전의 마지막 단계는 Lync Server 2010 관리 팩에서 새 중앙 검색 후보가 검색 되었는지 확인 하는 것입니다. 이렇게 하려면 Operations Manager 콘솔을 열고 모니터링을 클릭 합니다. 모니터링 탭에서 **Microsoft Lync Server 2010 상태**를 확장 하 고 **토폴로지 검색**을 확장 한 다음 **검색 상태 보기**를 클릭 합니다. 표시의 행에 중앙 검색 후보의 정규화 된 도메인 이름이 나열 되는 **경로가** 있는지 확인 합니다. 또한 컴퓨터 상태가 **정상**으로 보고 되었는지 확인 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

