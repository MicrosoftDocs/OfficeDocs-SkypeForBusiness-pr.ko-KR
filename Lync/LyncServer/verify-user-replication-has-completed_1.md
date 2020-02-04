---
title: 사용자 복제가 완료되었는지 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc6d8100a7bd0d348c3414da627584bae8697a1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>사용자 복제가 완료되었는지 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

**CsLegacyUser** cmdlet을 실행 하는 경우에는 AD DS (Active Directory 도메인 서비스) 간 사용자 정보로 인해 오류가 발생 하 고 초기 복제가 완료 되지 않아 Lync Server 2013 데이터베이스가 동기화 되지 않을 수 있습니다. Lync Server를 성공적으로 완료 하는 데 걸리는 시간 2013 사용자 복제기 서비스의 초기 동기화는 Lync Server 2013 풀을 호스팅하는 Active Directory 포리스트에서 호스팅되는 도메인 컨트롤러 수에 따라 달라 집니다. Lync server 2013 사용자 복제기 서비스 초기 동기화 프로세스는 Lync Server 2013 프런트 엔드 서버가 처음으로 시작 될 때 발생 합니다. 이후 동기화는 사용자 복제기 간격을 기준으로 합니다. **CsLegacyUser** cmdlet을 실행 하기 전에 사용자 복제가 완료 되었는지 확인 하려면 다음 단계를 완료 합니다.

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>사용자 복제가 완료 되었는지 확인 하려면

1.  Lync Server 2013 프런트 엔드 서버에서 **시작** 메뉴를 클릭 한 다음 **실행**을 클릭 합니다.

2.  **Eventvwr** 을 입력 한 다음 **확인을**클릭 합니다.

3.  이벤트 뷰어에서 **응용 프로그램 및 서비스 로그** 를 클릭 하 여 확장 한 다음 Lync Server를 선택 합니다.

4.  **작업** 창에서 **현재 로그 필터링**을 클릭 합니다.

5.  **이벤트 원본** 목록에서 **LS 사용자 복제기**를 클릭 합니다.

6.  ** \<모든 이벤트 id\> ** 에서 **30024** 을 입력 한 다음 **확인**을 클릭 합니다.

7.  필터링 된 이벤트 목록의 **일반** 탭에서 사용자 복제가 성공적으로 완료 되었음을 나타내는 항목을 찾습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

