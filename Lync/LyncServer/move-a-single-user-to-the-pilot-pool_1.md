---
title: 단일 사용자를 시험 운용 풀로 이동
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 086af622644f8d8285ef5f7be8e17f75ff436000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>단일 사용자를 시험 운용 풀로 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

Lync Server 2013 제어판 또는 Lync Server 2013 Management Shell을 사용 하 여 Office Communications Server 2007 R2 풀에서 Lync Server 2013 파일럿 풀로 사용자를 이동할 수 있습니다. 아래 예제에서 레지스트라 풀 열의 ** \<office communications server\> ** 는 office communications server 2007 R2 풀 이며,이 풀에는 6 명의 사용자가 모두 연결 되어 있습니다. Lync Server 2013 제어판 및 Lync Server Management Shell을 사용 하 여 사용자를 Lync Server 2013 풀로 이동 하려면 다음 절차를 사용 합니다.

Lync server 제어판에서 ![ocs 사용자 검색](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "lync SERVER 제어판에서 ocs 사용자 검색")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Lync Server 2013 제어판을 사용 하 여 사용자를 이동 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 CsAdministrator 또는 CsUserAdministrator 관리 역할의 구성원 인 계정을 사용 하 여 프런트 엔드 서버에 로그온 합니다.

2.  Lync Server 제어판을 엽니다.

3.  **사용자**를 클릭 합니다.

4.  **사용자 검색** 탭에서 **검색** 단추를 클릭 합니다.

5.  그런 다음 **필터 추가**를 클릭 합니다.

6.  **Office Communications Server 사용자** 가 **True**인 필터를 만듭니다.

7.  **찾기를** 클릭 하 여 레거시 Office Communications Server 2007 R2 사용자를 검색 합니다.
    
    Lync server 제어판에서 ![ocs 사용자 검색](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "lync SERVER 제어판에서 ocs 사용자 검색")  

8.  Lync Server 2013 풀로 이동 하려는 사용자를 선택 합니다. 이 예제에서는 사용자 Sara 아를 이동 합니다.

9.  **작업** 메뉴에서 **선택한 사용자 이동을 선택 하 여 그룹으로 이동**합니다.

10. 드롭다운 목록에서 Lync Server 2013 풀을 선택 합니다.

11. **작업** 을 클릭 한 다음 **선택한 사용자 이동을 클릭 하 여 그룹을 선택**합니다. **확인**을 클릭합니다.
    
    (images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "사용자 이동") ![대화 상자에서 대상 풀을 설정]합니다.  

12. 사용자의 **등록자 그룹** 열에 사용자가 성공적으로 이동 되었음을 나타내는 Lync Server 2013 풀이 포함 되어 있는지 확인 합니다.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Lync Server 2013 관리 셸을 사용 하 여 사용자를 이동 하려면

1.  Lync Server 관리 셸을 엽니다.

2.  명령줄에 다음을 입력 합니다.
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  그런 다음 명령줄에 다음을 입력 합니다.
    
        Get-CsUser -Identity "David Pelton"

4.  이제 **RegistrarPool** Id는 Lync Server 2013 풀을 가리킵니다. 이 id가 있으면 사용자가 성공적으로 이동 했음을 확인 합니다.
    
    가져오기-csuser cmdlet에서 identity 필터(images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "를 사용 하는 Get csuser cmdlet의") ![id 필터 출력으로 출력]  
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Get-csuser</STRONG> cmdlet에 대 한 자세한 내용을 보려면 <STRONG>Get-help-Csuser-Detailed</STRONG> 를 실행 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

