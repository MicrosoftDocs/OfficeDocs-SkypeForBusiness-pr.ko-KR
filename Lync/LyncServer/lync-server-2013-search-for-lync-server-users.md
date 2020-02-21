---
title: 'Lync Server 2013: Lync Server 사용자 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f503736b22453f6c3aafd76bc2fac7211f11dec7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>Lync Server 2013에서 Lync Server 사용자 검색

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-14_

검색 쿼리의 결과를 사용 하 여 Lync Server 2013에 대 한 사용자를 구성할 수 있습니다. 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)로 사용자를 검색할 수 있습니다.

Lync Server 제어판 또는 Active Directory 사용자 및 컴퓨터 스냅인을 사용하여 사용자를 검색할 수 있습니다. 다음 절차에서는 Lync Server 제어판을 사용 하 여 사용자를 검색 하는 방법에 대해 설명 합니다.

<div>


> [!NOTE]  
> 중앙 포리스트 토폴로지가 있는 환경에서는 사용자의 전자 메일 주소로 사용자를 검색하는 경우 검색 결과가 정확하지 않을 수 있습니다. 이러한 경우에는 sip:name과 같은 SIP 주소 접두사를 지정하여 사용자를 검색하거나, 검색 필터를 추가하고 전자 메일 주소의 일부분이 포함된 SIP 주소를 선택하거나, <STRONG>Get-CSUser</STRONG> cmdlet을 사용할 수 있습니다.



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>한 명 이상의 사용자를 검색하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭합니다.

4.  **사용자 검색** 상자에 검색할 사용자 계정의 표시 이름, 이름, 성, SAM 계정 이름, SIP 주소 또는 줄 URI를 모두 입력하거나 첫 부분을 입력하고 **찾기**를 클릭합니다.

5.  (선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.
    
    1.  화면 오른쪽 위의 **검색 결과** 위에 있는 확장 화살표 단추를 클릭하고 **필터 추가**를 클릭합니다.
    
    2.  사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.
    
    3.  **같음** 목록에서 **같음** 또는 **같지 않음**을 클릭합니다.
    
    4.  텍스트 상자에 검색 결과를 필터링하는 데 사용할 검색 조건을 입력하고 **찾기**를 입력합니다.

6.  **검색 결과** 아래에 검색 결과가 나타납니다. 목록에서 원하는 사용자 또는 모든 사용자를 선택하고 선택한 사용자에 대해 구성 작업을 수행할 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대해 사용 하도록 설정 된 사용자 계정에 대 한 정보 보기](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Lync Server 2013에 대 한 사용자 사용 및 사용 안 함](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

