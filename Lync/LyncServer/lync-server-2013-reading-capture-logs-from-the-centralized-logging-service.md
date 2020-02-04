---
title: 'Lync Server 2013: 중앙 로깅 서비스에서 캡처 로그 읽기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2713c9a1209aad4a96fcb3a76afaf7c2bc61c0dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013의 중앙 로깅 서비스에서 캡처 로그 읽기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-12-28_

검색을 실행 한 후 보고 된 문제를 추적 하는 데 사용할 수 있는 파일을가지고 있는 경우 중앙 로깅 서비스의 실질적인 이점을 얻게 됩니다. 파일을 읽을 수 있는 방법에는 여러 가지가 있습니다. 출력 파일은 표준 텍스트 형식으로 되어 있으며, Notepad.exe 또는 텍스트 파일을 열고 읽는 데 사용할 수 있는 다른 프로그램을 사용 하면 됩니다. 대용량 파일과 복잡 한 문제가 발생 하는 경우 중앙 로깅 서비스에서 로깅 출력을 읽고 구문 분석 하도록 디자인 된 Snooper 같은 도구를 사용할 수 있습니다. Snooper는 별도의 다운로드로 제공 되는 Lync Server 2013 디버그 도구에 포함 되어 있습니다. 다음과 같은 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)Lync Server 2013 디버그 도구를 다운로드할 수 있습니다. Lync Server 2013 디버그 도구를 설치 하면 짧은 잘라내기 및 메뉴 항목이 만들어지지 않습니다. Lync Server 2013 디버그 도구를 설치한 후 Windows 탐색기, 명령줄 창 또는 Lync Server Management Shell을 열고 디렉터리로 이동 합니다 (기본 위치) C:\\프로그램 파일\\Microsoft Lync Server 2013\\디버깅 도구. Snooper를 두 번 클릭 하거나 Snooper를 입력 하 고 명령줄 또는 Lync Server 관리 셸을 사용 하는 경우 enter 키를 누릅니다.

<div>


> [!IMPORTANT]  
> 이 항목의 목적은 문제 해결 기법을 자세히 설명 하 고 논의 하는 것이 아닙니다. 문제 해결 및 관련 프로세스는 복잡 한 주제입니다. 해결 방법에 대 한 자세한 내용과 특정 작업 부하 문제 해결에 대 한 자세한 내용은의 <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>Microsoft Lync Server 2010 Resource Kit 책을 참조 하세요. 프로세스와 절차는 여전히 Lync Server 2013에 적용 됩니다.



</div>

Lync Server 2013는 몇 가지 새로운 기능을 포함 하는 업데이트 된 버전의 Snooper을 소개 합니다. 다음 스크린샷은 Office Communications Server 2007의 Snooper 버전을 보여 줍니다.

![Office Communications 2007 버전의 Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 버전의 Snooper.")

다음 스크린샷은 Lync Server 2013 디버그 도구에 포함 된 새 버전의 Snooper를 보여 줍니다.

![Lync Server 2013 버전의 Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 버전의 Snooper.")

다음 스크린샷은 자주 사용 하는 함수가 있는 도구 모음을 보여 줍니다.

![Snooper 2013 도구 모음.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 도구 모음.")

값을 추가 하는 최신 기능은 흐름 차트 (호출 흐름) 다이어그램 보기입니다. **메시지** 탭에서 메시지 흐름을 선택 하 고 **호출 흐름** 단추를 클릭 합니다. 메시지를 진행할 때 통화 흐름 다이어그램이 새 데이터로 업데이트 됩니다.

![Snooper 2013 통화 흐름 다이어그램.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 통화 흐름 다이어그램.")

다이어그램 보기를 마우스로 가리키고 흐름 및 메시지의 메시지와 내용, 서버 요소에 대 한 세부 정보를 볼 수 있습니다. 통화 흐름 화살표를 클릭 하 여 메시지 보기의 메시지로 이동 합니다.

![통화 흐름 다이어그램 메시지 정보.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "통화 흐름 다이어그램 메시지 정보.")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>Snooper에서 로그 파일을 열려면

1.  Snooper를 사용 하 고 로그 파일을 열려면 로그 파일에 대 한 읽기 권한이 필요 합니다. Snooper를 사용 하 고 로그 파일에 액세스 하려면 CsAdministrator의 구성원 이거나,이 두 그룹 중 하나를 포함 하는 CsServerAdministrator 역할 기반 액세스 컨트롤 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할 이어야 합니다.

2.  Lync Server 디버깅 도구 (LSnooper Cdebugtools)를 설치한 후에 Windows 탐색기 또는 명령줄에서 디렉터리를의 위치로 변경 합니다. 기본적으로 디버깅 도구는 C:\\프로그램 파일\\Microsoft Lync Server 2013\\디버깅 도구에 있습니다. Snooper를 두 번 클릭 하거나 실행 합니다.

3.  Snooper가 열리면 **파일**을 마우스 오른쪽 단추로 클릭 하 고 **OpenFile**을 클릭 하 고 로그 파일을 찾은 다음 **열기** 대화 상자에서 파일을 선택 하 고 **열기**를 클릭 합니다.

4.  **추적** 탭에 로그 파일의 **추적** 메시지가 표시 됩니다. 수집 된 추적의 메시지 내용을 보려면 **메시지** 탭을 클릭 합니다.

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>통화 흐름 다이어그램을 표시 하려면

1.  Snooper를 사용 하 고 로그 파일을 열려면 로그 파일에 대 한 읽기 권한이 필요 합니다. Snooper를 사용 하 고 로그 파일에 액세스 하려면 CsAdministrator의 구성원 이거나,이 두 그룹 중 하나를 포함 하는 CsServerAdministrator 역할 기반 액세스 컨트롤 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할을 만들어야 합니다.

2.  로그 파일을 열고 **메시지** 탭을 클릭 하 고 메시지 보기에서 대화를 선택 하거나 **추적** 탭에서 추적 구성 요소를 선택 합니다.

3.  **통화 흐름**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 호출 흐름의 일부가 아닌 메시지 또는 추적을 클릭 하면 다이어그램이 나타나지 않으며 "이 메시지는 callSnooper에 적합 하지 않습니다." 라는 상태 메시지가 표시 됩니다. 다른 메시지 또는 추적을 선택 하면 메시지 또는 추적이 호출 흐름의 일부인 경우 호출 흐름이 표시 됩니다.

    
    </div>

4.  메시지 또는 추적 선을 이동 하 고 새 다이어그램을 표시 하기 위해 호출 흐름 다이어그램이 업데이트 또는 변경 되는지 확인 합니다.

5.  요소 위에 커서를 올리면 호출 메시지, 끝점 및 기타 구성 요소에 대 한 정보를 얻을 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

