---
title: 'Lync Server 2013: 중앙 로깅 서비스에서 캡처 로그 읽기'
description: 'Lync Server 2013: 중앙 로깅 서비스에서 캡처 로그를 읽습니다.'
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
ms.openlocfilehash: fcdd70c924b49098814e80a375ae34d2bf48dc41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559164"
---
# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013의 중앙 로깅 서비스에서 캡처 로그 읽기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-12-28_

검색을 실행 하 고 보고 된 문제를 추적 하는 데 사용할 수 있는 파일이 있는 경우 중앙 로깅 서비스의 실질적인 이점을 얻게 됩니다. 파일을 읽을 수 있는 방법은 여러 가지가 있습니다. 출력 파일이 표준 텍스트 형식이면 Notepad.exe 또는 텍스트 파일을 열고 읽을 수 있는 기타 프로그램을 사용할 수 있습니다. 파일 크기가 크거나 복잡 한 문제를 해결 하려면 중앙 로깅 서비스에서 로깅 출력을 읽고 구문 분석 하도록 설계 된 Snooper.exe 등의 도구를 사용할 수 있습니다. Snooper는 Lync Server 2013 Debug Tools에 포함되어 있으며 별도로 다운로드할 수 있습니다. Lync Server 2013 디버그 도구는 다음 위치에서 다운로드할 수 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) 있습니다. Lync Server 2013 디버그 도구를 설치 하면 짧은 컷 및 메뉴 항목은 만들어지지 않습니다. Lync Server 2013 디버그 도구를 설치 하 고 나면 Windows 탐색기, 명령줄 창 또는 Lync Server 관리 셸을 열고 디렉터리로 이동 합니다 (기본 위치) C: \\ Program Files \\ Microsoft Lync Server 2013 \\ 디버깅 도구 Snooper.exe를 두 번 클릭 하거나 Snooper.exe 입력 한 다음 명령줄 또는 Lync Server 관리 셸을 사용 하는 경우 enter 키를 누릅니다.

<div>


> [!IMPORTANT]  
> 이 문서에서는 문제 해결 기술에 대해 자세히 설명하거나 논의하지 않습니다. 문제 해결 및 관련 프로세스는 복잡한 주제입니다. 문제 해결 기본 사항과 특정 작업의 문제 해결에 대 한 자세한 내용은에서 Microsoft Lync Server 2010 Resource Kit book을 참조 하십시오 <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A> . 프로세스 및 절차는 Lync Server 2013에도 적용 됩니다.



</div>

Lync Server 2013에는 몇 가지 새로운 기능을 포함 하는 업데이트 된 버전의 Snooper가 도입 되었습니다. 다음 스크린샷은 Office Communications Server 2007의 Snooper 버전을 보여 줍니다.

![Office Communications 2007 Snooper 버전입니다.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 Snooper 버전입니다.")

다음 스크린샷은 Lync Server 2013 디버그 도구에 포함 된 Snooper의 새 버전을 보여 줍니다.

![Lync Server 2013 Snooper 버전입니다.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 Snooper 버전입니다.")

다음 스크린 샷은 자주 사용되는 기능이 포함된 도구 모음을 보여줍니다.

![Snooper 2013 도구 모음](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 도구 모음")

또한 가치를 더 발하는 최신 기능으로는 순서도(또는 흐름) 다이어그램 보기가 있습니다. **Message(메시지)** 탭에서 메시지 흐름을 선택하고 **Call Flow(통화 흐름)** 단추를 클릭합니다. 메시지 간을 이동하면 통화 흐름 다이어그램이 새 데이터로 업데이트됩니다.

![Snooper 2013 통화 흐름 다이어그램입니다.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 통화 흐름 다이어그램입니다.")

다이어그램 보기에 마우스 커서를 놓으면 메시지에 대한 정보, 흐름 및 메시지의 구성 내용, 서버 요소 등을 볼 수 있습니다. 통화 흐름 화살표를 클릭하면 메시지 보기의 메시지로 이동합니다.

![통화 흐름 다이어그램 메시지 세부 정보입니다.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "통화 흐름 다이어그램 메시지 세부 정보입니다.")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>Snooper에서 로그 파일을 열려면

1.  Snooper를 사용하여 로그 파일을 열려면 로그 파일에 대한 읽기 액세스 권한이 있어야 합니다. Snooper를 사용하여 로그 파일에 액세스하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹의 구성원이거나 이들 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이어야 합니다.

2.  Lync Server 디버깅 도구 (LyncDebugTools.msi)를 설치한 후 Windows 탐색기나 명령줄을 사용 하 Snooper.exe 위치로 디렉터리를 변경 합니다. 기본적으로 디버깅 도구는 C: \\ Program Files \\ Microsoft Lync Server 2013 디버깅 도구에 있습니다 \\ . Snooper.exe를 두 번 클릭하거나 실행합니다.

3.  Snooper가 열리면 **File(파일)** 을 클릭하고 **OpenFile**을 클릭한 다음 **Open(열기)** 대화 상자에서 로그 파일을 찾아 선택한 후 **Open(열기)** 을 클릭합니다.

4.  로그 파일의 **Trace(추적)** 메시지가 **Trace(추적)** 탭에 표시됩니다. **Messages(메시지)** 탭을 클릭하여 수집된 추적 메시지 내용을 봅니다.

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>통화 흐름 다이어그램을 표시하려면

1.  Snooper를 사용하여 로그 파일을 열려면 로그 파일에 대한 읽기 액세스 권한이 있어야 합니다. Snooper를 사용하여 로그 파일에 액세스하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹의 구성원이거나 이들 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이어야 합니다.

2.  로그 파일을 열고 **Messages(메시지)** 탭을 클릭한 다음 메시지 보기에서 대화를 선택하거나, **Trace(추적)** 탭에서 추적 구성 요소를 선택합니다.

3.  **Call Flow(통화 흐름)** 을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 통화 흐름의 일부가 아닌 메시지나 추적을 클릭하면 다이어그램이 나타나지 않고 "이 메시지는 통화 흐름에 적용되지 않습니다"와 같은 상태 메시지가 Snooper 아래에 나타납니다. 통화 흐름의 일부인 다른 메시지나 추적을 선택하면 통화 흐름이 나타납니다.

    
    </div>

4.  메시지 또는 추적 줄 간을 이동하여 통화 흐름 다이어그램이 새로운 다이어그램을 표시하도록 업데이트 또는 변경되는지 확인합니다.

5.  통화 메시지, 끝점, 기타 구성 요소에 대한 정보를 확인하려면 요소 위에 마우스 커서를 놓습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

