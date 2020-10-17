---
title: 공존 시나리오에서 Lync Server 2010 관리 팩 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb614726458f2cf9c77bdfe740ddb13d99d54f2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529925"
---
# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>공존 시나리오에서 Lync Server 2010 관리 팩 사용

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

대부분의 고객은 사용자가 Microsoft Lync Server 2010에서 Lync Server 2013로 점진적으로 마이그레이션되는 기업 내부에 롤아웃 프로그램을 채택 하 고 있습니다. 이러한 회사의 관리자는 두 버전의 Lync Server를 모니터링 하 여 모든 최종 사용자가 최상의 통신 환경을 얻을 수 있도록 하는 데 도움이 됩니다. 이 시나리오의 경우 Lync Server 2013 관리 팩은 Lync Server 2010 관리 팩과 함께 병행 마이그레이션 경로를 지원 합니다.

Lync Server 2010에서는 중앙 관리 저장소와 함께 저장 된 토폴로지 문서를 통해 Lync Server 컴퓨터를 검색 했습니다. 이 구성에서는 단일 컴퓨터에서 다른 모든 Lync Server 컴퓨터가 있는지 여부를 보고 합니다.

Lync Server 2013의 관리 팩은 이제 Lync Server 2010에서 사용 된 중앙 검색 메커니즘 대신 컴퓨터 수준 검색을 사용 합니다. 즉, 각 System Center 에이전트가 자신의 상태를 검색해서 이를 System Center Operations Manager에 보고합니다. 컴퓨터 수준 검색을 사용 하면 시스템 센터 인프라를 간편 하 게 관리할 수 있으며 lync server 관리 팩 (예: lync server 2010 및 Lync Server 2013 용 관리 팩)의 다양 한 버전을 보다 편리 하 게 사용 하도록 설정할 수도 있습니다.

이 마이그레이션을 지원 하려면 먼저 기존 Lync Server 2010 모니터링을 업그레이드 하 여 범위에 대 한 차이를 방지 해야 합니다. 이렇게 하려면 중앙 관리 저장소를 Lync Server 2013로 업그레이드 하기 전에 Lync Server 2010에 대 한 중앙 검색 스크립트를 서비스 하기 위해 기존 Lync Server 2010 컴퓨터를 선택 합니다. 이 프로세스는 다음 4단계로 구성됩니다.

1.  Lync Server 2010 관리 팩을 누적 업데이트 7로 업그레이드 합니다.

2.  Lync Server 2010 컴퓨터에 중앙 검색 스크립트를 실행 하도록 지시 합니다.

3.  Microsoft Lync Server 2010 관리 팩의 중앙 검색 후보를 재정의 합니다.

4.  새 중앙 검색 후보가 검색되었는지 확인합니다.

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>중앙 검색 스크립트를 실행할 Lync Server 2010 컴퓨터 지정

중앙 검색을 처리 하기 위해 중앙 집중식 관리 저장소 컴퓨터 (예: Lync Server 프런트 엔드) 서버를 위한 비 중앙 관리 저장소 서버에 다음과 같은 레지스트리 키를 만들어야 합니다.

HKLM \\ Software \\ Microsoft \\ 실시간 통신 \\ 상태 \\ 만들어졌으면 centraldiscoverycandidate

이 레지스트리 키는 다음 절차에 따라 만들 수 있습니다.

1.  **시작**을 클릭한 다음 **실행**을 클릭합니다.

2.  **실행** 대화 상자에 **regedit**를 입력한 다음 Enter 키를 누릅니다.

3.  레지스트리 편집기에서 **HKEY \_ 로컬 \_ 컴퓨터**를 확장 하 고 **소프트웨어**, **Microsoft**를 차례로 확장 한 다음 **실시간 통신**을 확장 합니다.

4.  **Health**를 마우스 오른쪽 단추로 클릭하고, **새로 만들기**를 클릭한 후 **키**를 클릭합니다. **Health** 키가 없으면 **Real-Time Communications**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 후 **키**를 클릭합니다. 새 키가 만들어졌으면 Health를 입력한 후 Enter 키를 누릅니다.
    
    새 키가 만들어졌으면 **CentralDiscoveryCandidate**를 입력한 후 Enter 키를 눌러서 키 이름을 바꿉니다.

컴퓨터에서 이 변경 내용을 선택하려면 몇 시간 정도 걸릴 수 있습니다. 변경 내용을 즉시 적용하려면 상태 에이전트 서비스를 중지한 후 다시 시작합니다. 상태 에이전트 서비스를 다시 시작 하려면 Lync Server 2010 컴퓨터에서 다음 절차를 완료 합니다.

1.  **시작**, **모든 프로그램**, **보조 프로그램**을 차례로 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행**을 클릭합니다.

2.  콘솔 창에 다음 명령을 입력한 다음 Enter 키를 누릅니다.
    
        Net stop HealthService

3.  "System Center 관리 서비스를 중지하는 중입니다."라는 메시지가 표시되고 이후 서비스가 중지되었다는 메시지가 나타납니다. 서비스가 중지된 후 다음 명령을 입력하고 Enter 키를 눌러서 서비스를 다시 시작할 수 있습니다.
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Lync Server 2010 관리 팩의 중앙 검색 후보 재정의

Lync server 2010 컴퓨터에 Lync Server 2010 컴퓨터에 대 한 보고를 한 후에는이 변경 사항에 대 한 정보를 Lync Server 2010 관리 팩에도 알려야 합니다. 이렇게 하려면 관리 팩에서 재정의를 만들어야 합니다. 이 작업은 다음 절차에 따라 수행할 수 있습니다.

1.  Operations Manager 콘솔에서 **제작**을 클릭합니다.

2.  제작 탭에서 **관리 팩 개체**를 확장하고, **개체 검색**을 클릭한 후 **범위**를 클릭합니다.

3.  **관리 팩 개체 범위 지정** 대화 상자에서 대상 **LS 검색 후보**가 포함된 항목을 선택한 후 **확인**을 클릭합니다. LS 검색 후보는 Lync Server 2010 관리 팩을 설치한 경우에만 표시 됩니다.

4.  Operations Manager 콘솔에서 **LS 검색 후보**를 마우스 오른쪽 단추로 클릭하고 **재정의**, **개체 검색 재정의**를 가리킨 후 **클래스의 모든 개체: LS 검색 후보**를 클릭합니다.

5.  **재정의 속성** 대화 상자에서 **중앙 검색 감시자 노드 FQDN** 매개 변수 옆에 있는 **재정의** 확인란을 선택합니다. **값 재정의** 및 **유효 값** 상자에 Lync Server 2010 컴퓨터의 정규화 된 도메인 이름을 입력 합니다. **적용** 확인란을 선택하고 **확인**을 클릭합니다.

재정의를 만든 후에는 루트 관리 서버의 상태 서비스를 다시 시작해야 합니다. 상태 서비스를 다시 시작하려면 루트 관리 서버에서 다음 절차를 완료합니다.

1.  **시작**, **모든 프로그램**, **보조 프로그램**을 차례로 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행**을 클릭합니다.

2.  콘솔 창에 다음 명령을 입력한 다음 Enter 키를 누릅니다.
    
        Net stop HealthService

3.  "System Center 관리 서비스를 중지하는 중입니다."라는 메시지가 표시되고 이후 서비스가 중지되었다는 메시지가 나타납니다. 서비스가 중지된 후 다음 명령을 입력하고 Enter 키를 눌러서 서비스를 다시 시작할 수 있습니다.
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>새 중앙 검색 후보가 검색되었는지 확인

중앙 관리 저장소를 업그레이드 하기 전 마지막 단계는 새 중앙 검색 후보가 Lync Server 2010 관리 팩에서 검색 되었는지 확인 하는 것입니다. 이를 위해서는 Operations Manager 콘솔을 열고 모니터링을 클릭합니다. 모니터링 탭에서 **Microsoft Lync Server 2010 Health**, **토폴로지 검색**을 확장한 후 **검색 상태 보기**를 클릭합니다. 디스플레이의 행에 중앙 검색 후보의 FQDN(정규화된 도메인 이름)이 나열된 **경로**가 있는지 확인합니다. 또한 컴퓨터 상태가 **정상**으로 보고되었는지 확인해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

