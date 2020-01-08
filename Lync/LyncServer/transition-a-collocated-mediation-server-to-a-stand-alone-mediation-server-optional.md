---
title: Collocated 중재 서버를 독립 실행형 중재 서버로 전환 (선택 사항)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c49b75845bb9a673872c5f08225dd6e1c96b69a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>Collocated 중재 서버를 독립 실행형 중재 서버로 전환 (선택 사항)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

다음 절차를 사용 하 여 Standard Edition Server 또는 프런트 엔드 풀에서 중재 서버를 collocated 단일 사이트 배포를 위한 독립 실행형 중재 서버로 전환 합니다.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>Collocated 중재 서버를 독립 실행형 중재 서버로 전환 하려면

1.  토폴로지 작성기에서 기존 토폴로지를 엽니다.

2.  왼쪽 창에서 **중재 풀**로 이동 합니다.

3.  **중재 풀** 을 마우스 오른쪽 단추로 클릭 하 고 **새 중재 서버**를 선택 합니다.

4.  **새 중재 풀 정의** 페이지에서 새 중재 서버 풀의 FQDN을 제공 합니다. 또한이 풀이 단일 서버 또는 다중 서버 풀 인지 여부를 선택 하 고 **다음**을 클릭 합니다.

5.  새 중재 서버가 인바운드 통화를 라우팅할 다음 홉 프런트 엔드 서버 풀을 선택 하 고 **다음**을 클릭 합니다.

6.  중재 서버에서 사용할 Edge 풀을 선택 하 고 **다음**을 클릭 합니다.

7.  **Pstn 게이트웨이 지정** 페이지에서 이전 PSTN 게이트웨이를 중재 서버와 연결 합니다. 게이트웨이를 선택 하 고 **추가**를 클릭 합니다.

8.  **마침을** 클릭 하 여 **새 중재 풀 정의** 마법사를 닫습니다.

9.  **토폴로지 작성기**에서 최상위 노드 **Lync 서버 2013**를 선택 합니다.

10. **작업** 창에서 **토폴로지 게시** 를 선택 하 고 마법사를 완료 합니다.

11. 배포 설명서의 [Lync server 2013에서 조정 용 파일 서버 설치](lync-server-2013-install-the-files-for-mediation-server.md) 의 단계에 따라 새 중재 서버에 파일을 설치 합니다.

12. 중재 서버에 파일을 설치한 후에 토폴로지 작성기로 돌아가서 왼쪽 창에서 풀로 이동 합니다.

13. 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다.

14. **중재 서버**에서 확인란의 선택을 취소 하 고 **Collocated 중재 서버를 사용 하도록 설정한** 다음 **확인**을 클릭 합니다.

15. **토폴로지 작성기**에서 최상위 노드 **Lync 서버 2013**를 선택 합니다.

16. **작업** 메뉴에서 **토폴로지 게시** 를 선택 하 고 마법사를 완료 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

