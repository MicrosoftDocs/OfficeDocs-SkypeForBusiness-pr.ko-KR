---
title: 'Lync Server 2013: Lync Server 사용자 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068fe07bf14894d22f929291514854360d6d0465
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Lync Server 2013에서 Lync Server 사용자 검색

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-14_

검색 쿼리의 결과를 사용 하 여 Lync Server 2013의 사용자를 구성할 수 있습니다. 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 URI (Uniform Resource Identifier)를 기준으로 사용자를 검색할 수 있습니다.

Lync Server 제어판 또는 Active Directory 사용자 및 컴퓨터 스냅인을 사용 하 여 사용자를 검색할 수 있습니다. 다음 절차에서는 Lync Server 제어판을 사용 하 여 사용자를 검색 하는 방법을 설명 합니다.

<div>


> [!NOTE]  
> 중앙 포리스트 토폴로지가 있는 환경에서는 사용자의 전자 메일 주소를 사용 하 여 사용자를 검색할 때 검색 결과가 정확 하지 않을 수 있습니다. 대신 sip: 이름, 검색 필터 추가, 부분 전자 메일 주소가 포함 된 SIP 주소 선택, <STRONG>Get-CSUser</STRONG> cmdlet을 사용 하 여 사용자를 검색할 수 있습니다.



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>한 명 이상의 사용자를 검색 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.

4.  **사용자 검색** 상자에 검색 하려는 사용자 계정의 표시 이름, 이름, 성, SAM 계정 이름, SIP 주소 또는 회선 URI의 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.

5.  ) 추가 검색 조건을 지정 하 여 결과의 범위를 좁힙니다.
    
    1.  **검색 결과**위에 있는 화면의 오른쪽 위 모서리에 있는 확장 화살표 단추를 클릭 한 다음 **필터 추가**를 클릭 합니다.
    
    2.  사용자 속성을 입력 하거나 드롭다운 목록에서 화살표를 클릭 하 여 사용자 속성을 선택 합니다.
    
    3.  **같음** 목록에서 **같음** 또는 **같지 않음을**클릭 합니다.
    
    4.  텍스트 상자에 검색 결과를 필터링 하는 데 사용할 검색 조건을 입력 한 다음 **찾기를**클릭 합니다.

6.  검색 **결과**에 검색 결과가 표시 됩니다. 목록에서 사용자를 하나 또는 모두 선택 하 고 선택한 사용자에 대해 구성 작업을 수행할 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 사용 하도록 설정 된 사용자 계정에 대 한 정보 보기](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Lync Server 2013에 대 한 사용자 설정 및 해제](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

