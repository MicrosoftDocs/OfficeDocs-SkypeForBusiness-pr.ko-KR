---
title: 'Lync Server 2013: 응답 그룹에서 사용 하는 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e6cf167917dc7d72484eb0fa833a688b0b4e4b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Lync Server 2013의 응답 그룹에서 사용 하는 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-11_

Enterprise Voice를 배포할 때 응답 그룹 응용 프로그램이 자동으로 사용 하도록 설정 됩니다. 이 섹션에서는 응답 그룹 응용 프로그램을 지 원하는 구성 요소에 대해 설명 합니다.

<div>

## <a name="response-group-components"></a>응답 그룹 구성 요소

다음 Microsoft Lync Server 2013 구성 요소는 응답 그룹 응용 프로그램을 지원 합니다.

  - **응용 프로그램 서비스**   응용 프로그램 서비스는 응답 그룹과 같은 통합 통신 응용 프로그램을 배포, 호스팅 및 관리 하기 위한 플랫폼을 제공 합니다. 응용 프로그램 서비스는 프런트 엔드 풀의 모든 프런트 엔드 서버와 모든 Standard Edition 서버에 자동으로 설치 됩니다.

  - **응답 그룹 응용**   프로그램 응답 그룹 응용 프로그램은 응용 프로그램 서비스에서 호스팅하는 통합 통신 응용 프로그램 중 하나입니다. 응답 그룹을 배포할 때 자동으로 포함 됩니다. 응답 그룹 응용 프로그램은 에이전트 그룹에 대 한 수신 전화를 라우팅하고 큐에 대기 시킵니다.

  - **언어 팩**   텍스트 음성 변환 및 음성 인식을 지원 하기 위해 언어 팩이 필요 합니다. 이러한 음성 기술은 시작 메시지나 기타 프롬프트, 그리고 IVR(대화형 음성 응답) 질문 및 대답과 같은 메시지를 구성할 때 사용됩니다. 기본적으로 Lync Server 2013를 배포할 때는 지원 되는 26 가지 언어 팩이 모두 설치 됩니다.

  - **오디오 파일**   오디오 파일은 메시지 및 대기 음악에 사용 됩니다.

  - **파일 저장소**   응답 그룹에서는 파일 저장소를 사용 하 여 오디오 파일을 저장 합니다. 여러 응답 그룹 풀이 같은 파일 저장소 인스턴스를 사용할 수 있습니다.

  - **응답 그룹 구성 도구**   응답 그룹 구성 도구는 응답 그룹을 만들고 구성 하는 데 사용 되는 웹 기반 도구입니다. 웹 서비스를 설치할 때 응답 그룹 구성 도구가 포함 됩니다.

  - **Microsoft lync server 2013 Control panel**   Lync server 제어판을 사용 하 여 응답 그룹용 에이전트 그룹 및 큐를 설정 하 고 구성할 수 있습니다.

  - **Lync server 관리 셸**   lync server 관리 셸 cmdlet을 사용 하 여 모든 응답 그룹 설정을 구성할 수 있습니다.

  - **Microsoft lync 2013**   공식 에이전트 (그룹에 대 한 호출을 수락 하기 전에이를 관리자에 게 로그인 해야 함) Lync 2013을 사용 하 여 그룹에 로그인 하 고 로그 아웃 합니다. 공식 에이전트에 대해 에이전트 그룹이 구성 된 경우, 에이전트는 Lync 2013에서 메뉴 항목을 클릭 하 여 Internet Explorer를 열고 그룹 로그인 및 로그 아웃을 위한 웹 페이지 콘솔을 표시 합니다.

  - **웹 서비스**   웹 서비스는 응답 그룹 구성 도구, 에이전트의 로그인 및 로그 아웃 콘솔, Lync Server 제어판 및 응답 그룹 클라이언트 웹 서비스에 필요 합니다.

  - **응답 그룹 클라이언트 웹 서비스**   응답 그룹 응용 프로그램은 타사 응용 프로그램에서 에이전트, 에이전트 그룹 구성원, 에이전트 로그인 상태, 그룹에 대 한 통화 상태 및 익명 통화를 지 원하는 그룹에 대 한 정보를 검색 하는 데 사용할 수 있는 클라이언트 웹 서비스를 제공 합니다. Lync 2013 및 Lync 2010 Attendant는 응답 그룹 클라이언트 웹 서비스를 사용 하 여 에이전트가 익명으로 전화를 거는 데 사용할 수 있는 응답 그룹 목록을 검색 합니다. 클라이언트 웹 서비스는 웹 서비스를 설치할 때 포함됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

