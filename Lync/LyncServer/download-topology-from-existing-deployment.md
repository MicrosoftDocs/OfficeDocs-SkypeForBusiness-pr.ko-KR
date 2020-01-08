---
title: 기존 배포에서 토폴로지 다운로드
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26c47e6d78d3bd9522b8f0369924f05f8f939037
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>기존 배포에서 토폴로지 다운로드

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-29_

Lync Server 2013 풀을 만들 때 Lync Server 2010와 연결 된 중앙 관리 저장소를 사용 합니다. 첫 번째 사용 및 후속 편집 세션에서 토폴로지 작성기를 시작 하면 토폴로지 작성기가 현재 구성 문서를 로드할 위치를 묻는 메시지가 표시 됩니다. 이미 Lync Server 2010 토폴로지가 정의 되어 있으며 중앙 관리 저장소를 설정 했기 때문에 기존 배포에서 토폴로지를 다운로드 하도록 선택 해야 합니다. 토폴로지 작성기는 데이터베이스를 읽고 현재 정의를 검색 합니다.

**기존 배포에서 토폴로지를 다운로드 하려면**

1.  **Lync 서버 배포 마법사**를 엽니다.

2.  **Lync Server 2013 – 배포 마법사** 페이지에서 **관리 도구 설치**를 클릭 합니다.

3.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013** 을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

4.  **기존 배포에서 토폴로지 다운로드를**선택 합니다.
    
    ![배포 마법사 토폴로지 작성기 설정](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "배포 마법사 토폴로지 작성기 설정")

5.  파일 이름을 선택 하 고 기본 tbxml 파일 형식을 사용 하 여 토폴로지를 저장 합니다.

6.  표시 된 대로 Lync Server 노드를 확장 하 여 배포의 다양 한 서버 역할을 나타냅니다.
    
    ![토폴로지 작성기 서버 역할 일반 속성](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "토폴로지 작성기 서버 역할 일반 속성")

</div>

<span> </span>

</div>

</div>

</div>

