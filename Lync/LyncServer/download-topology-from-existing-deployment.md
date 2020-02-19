---
title: 기존 배포에서 토폴로지 다운로드
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ebf73ad647003a1835a235bda240229433ac6d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>기존 배포에서 토폴로지 다운로드

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-29_

Lync Server 2013 풀을 만들 때는 Lync Server 2010와 연결 된 중앙 관리 저장소를 사용 합니다. 최초 사용 시와 후속 편집 세션에서 토폴로지 작성기를 시작하면 토폴로지 작성기에서 현재 구성 문서를 로드할 위치를 선택하라는 메시지가 표시됩니다. 이미 Lync Server 2010 토폴로지가 정의 되어 있고 중앙 관리 저장소를 설정 했기 때문에 기존 배포에서 토폴로지를 다운로드 하도록 선택 해야 합니다. 그러면 토폴로지 작성기에서 데이터베이스를 읽고 현재 정의를 검색합니다.

**기존 배포에서 토폴로지를 다운로드하려면**

1.  **Lync Server 배포 마법사**를 엽니다.

2.  **Lync Server 2013 – 배포 마법사** 페이지에서 **관리 도구 설치**를 클릭합니다.

3.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013** 을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

4.  **기존 배포에서 토폴로지 다운로드**를 선택합니다.
    
    ![배포 마법사 토폴로지 작성기 설정](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "배포 마법사 토폴로지 작성기 설정")

5.  파일 이름을 선택하고 토폴로지를 기본 .tbxml 파일 형식으로 저장합니다.

6.  표시된 것처럼 Lync Server 노드를 확장하여 배포에 있는 다양한 서버 역할을 표시합니다.
    
    ![토폴로지 작성기 서버 역할 일반 속성](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "토폴로지 작성기 서버 역할 일반 속성")

</div>

<span> </span>

</div>

</div>

</div>

