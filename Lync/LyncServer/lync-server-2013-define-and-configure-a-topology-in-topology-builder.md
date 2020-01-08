---
title: 'Lync Server 2013: 토폴로지 작성기에서 토폴로지 정의 및 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee952eef30fc50f30448c98956899c3a1a06dc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>Lync Server 2013에 대한 토폴로지 작성기에서 토폴로지 정의 및 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

토폴로지 작성기를 실행 하 여 새 토폴로지를 정의 하거나 기존 토폴로지를 수정 하는 것은 로컬 관리자 또는 특권 도메인 그룹의 구성원 자격이 필요 하지 않습니다. 토폴로지 작성기는 구성 요구 사항에 따라 Enterprise Edition 프런트 엔드 풀 또는 표준 버전에 대 한 토폴로지를 정의 하는 데 필요한 단계를 안내 합니다.

서버에 Lync Server 2013을 설치 하기 전에 토폴로지 작성기를 사용 하 여 토폴로지를 완료 하 고 게시 해야 합니다. 다음 절차에는 새 토폴로지를 정의 하는 데 필요한 단계가 포함 되어 있습니다.

<div>

## <a name="to-define-a-topology"></a>토폴로지를 정의 하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  토폴로지 작성기에서 **새 토폴로지**를 선택 합니다. 토폴로지를 저장할 위치와 파일 이름을 입력 하 라는 메시지가 표시 됩니다. 토폴로지 파일에 의미 있는 이름을 지정 하 고 tbxml의 기본 확장명을 그대로 사용 합니다. **확인**을 클릭합니다.

3.  새 토폴로지 XML 파일을 저장 하려는 위치로 이동 하 고 파일 이름을 입력 한 다음 **저장**을 클릭 합니다.

4.  **기본 도메인 정의** 페이지에서 조직의 기본 SIP 도메인 이름을 입력 하 고 **다음**을 클릭 합니다.

5.  **추가 지원 도메인 지정** 페이지에서 추가 도메인의 이름을 입력 하 고 **다음**을 클릭 합니다.

6.  **첫 번째 사이트 정의** 페이지에서 첫 번째 사이트의 이름과 설명을 입력 하 고 **다음**을 클릭 합니다.

7.  **사이트 세부 정보 지정** 페이지에서 사이트의 위치 정보를 입력 하 고 **다음**을 클릭 합니다.

8.  **새 토폴로지가 성공적으로 정의 되었습니다** 페이지에서 **마법사를 닫을 때 새 프런트 엔드 마법사 열기** 확인란을 선택 했는지 확인 하 고 **마침을**클릭 합니다.

토폴로지를 정의 하 고 저장 한 후 새 프런트 엔드 마법사를 사용 하 여 사이트의 프런트 엔드 풀 또는 Standard Edition 서버를 정의 합니다. 자세한 내용은 [Lync server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성을](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

