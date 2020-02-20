---
title: 배치 된 중재 서버를 독립 실행형 중재 서버로 전환 (선택 사항)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03e182bc32ba07ae22b2c14cc0a51f36ac93ba57
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>배치 된 중재 서버를 독립 실행형 중재 서버로 전환 (선택 사항)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

단일 사이트 배포를 위해 Standard Edition 서버 또는 프런트 엔드 풀에 배치된 중재 서버를 독립 실행형 중재 서버로 전환하려면 이 절차를 사용합니다.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>배치된 중재 서버를 독립 실행형 중재 서버로 전환하려면

1.  토폴로지 작성기에서 기존 토폴로지를 엽니다.

2.  왼쪽 창에서 **중재 풀**로 이동합니다.

3.  **중재 풀**을 마우스 오른쪽 단추로 클릭한 후 **새 중재 서버**를 선택합니다.

4.  **새 중재 풀 정의** 페이지에서 새 중재 서버 풀의 FQDN을 제공합니다. 또한 이 풀이 단일 서버인지 또는 다중 서버 풀인지 여부를 선택한 후 **다음**을 클릭합니다.

5.  새 중재 서버가 인바운드 호출을 라우팅할 다음 홉 프런트 엔드 서버 풀을 선택한 후 **다음**을 클릭합니다.

6.  중재 서버에서 사용할 에지 풀을 선택한 후 **다음**을 클릭합니다.

7.  **PSTN 게이트웨이 지정** 페이지에서 이전 PSTN 게이트웨이를 중재 서버와 연결합니다. 게이트웨이를 선택한 후 **추가**를 클릭합니다.

8.  **마침**을 클릭하여 **새 중재 풀 정의** 마법사를 닫습니다.

9.  **토폴로지 작성기**에서 최상위 노드 **Lync Server 2013**을 선택 합니다.

10. **동작** 창에서 **토폴로지 게시**를 선택한 후 마법사를 완료합니다.

11. 배포 설명서의 [Lync server 2013에서 중재 서버용 파일 설치](lync-server-2013-install-the-files-for-mediation-server.md) 의 단계에 따라 새 중재 서버에 파일을 설치 합니다.

12. 파일이 중재 서버에 설치된 후 토폴로지 작성기로 돌아가고 왼쪽 창에서 해당 풀로 이동합니다.

13. 풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 선택합니다.

14. **중재 서버**에서 **배치된 중재 서버 사용됨** 확인란의 선택을 취소한 후 **확인**을 클릭합니다.

15. **토폴로지 작성기**에서 최상위 노드 **Lync Server 2013**을 선택 합니다.

16. **동작** 메뉴에서 **토폴로지 게시**를 선택한 후 마법사를 완료합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

