---
title: 'Lync Server 2013: 모임 초대 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 014a42597e3df416d9e502eaaa90e2f1e71e35ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Lync Server 2013에서 모임 초대 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-07-16_

모임 초대의 본문에 다음 선택 항목을 포함 하 여 Lync 2013의 온라인 모임 추가 기능에서 보낸 모임 초대를 사용자 지정할 수 있습니다.

  - **조직의 로고** 로고 URL 옵션을 사용 하 여 모임 초대에 조직의 로고를 추가 합니다. 조직 외부의 사용자에 게 모임 초대를 보내는 경우 이미지가 공개적으로 사용할 수 있는 URL에 위치 해야 합니다. 지원 되는 이미지 형식은 GIF 및 JPG입니다. Lync Server 2013에서 이미지에 크기 제한이 없는 URL을 저장 하는 경우 최상의 결과를 위해 이미지의 최대 크기는 너비가 각각 30 픽셀, 높이 188 픽셀 이어야 합니다.

  - **사용자 지정 도움말 또는 지원 링크** 조직의 도움말 또는 지원 팀 웹 사이트에 대 한 URL을 추가 합니다. 조직 외부의 사용자에 게 모임 초대를 보내는 경우 URL을 공개적으로 사용할 수 있어야 합니다. 최대 URL 길이는 1kb입니다.

  - **법적 고 지 사항 텍스트** 모든 모임 초대에 표시 되는 법적 고 지 사항 또는 내용에 대 한 URL을 추가 합니다. 조직 외부의 사용자에 게 모임 초대를 보내는 경우 URL을 공개적으로 사용할 수 있어야 합니다. 최대 URL 길이는 1kb입니다.

  - **사용자 지정 바닥글 텍스트** 초대에 사용자 지정 바닥글로 렌더링할 텍스트를 추가 합니다. 추가할 수 있는 최대 텍스트 길이는 2kb입니다.

Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 이러한 옵션을 구성할 수 있습니다.

<div>


**Lync Server 제어판을 사용 하 여 모임 초대를 사용자 지정 하려면**

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **모임 구성을**클릭 합니다.

4.  **모임 구성** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.
    
      - 사이트 수준 정책을 만들려면 **사이트 구성을**클릭 합니다. 사이트 검색 **선택** 필드에 모임 참가 설정을 정의할 사이트 이름의 전부 또는 일부를 입력 합니다. 사이트 결과 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.
    
      - 풀 수준 정책을 만들려면 **풀 구성을**클릭 합니다. 서비스 검색 **선택** 필드에 모임 참가 설정을 정의할 풀 서비스 이름의 전부 또는 일부를 입력 합니다. 결과 서비스 목록에서 원하는 풀을 클릭 한 다음 **확인**을 클릭 합니다.

5.  다음 중 하나를 수행 합니다.
    
      - **로고 url** 필드에 조직의 로고 이미지에 대 한 URL을 입력 합니다.
    
      - **도움말 url** 필드에 조직의 도움말 또는 지원 사이트에 대 한 URL을 입력 합니다.
    
      - **법적** 고 지 사항 필드에 약관에 대 한 URL을 입력 하 고 모임 초대에 포함할 법률 또는 책임의 텍스트
    
      - **사용자 지정 바닥글 텍스트** 필드에 바닥글 텍스트 (최대 2kb)를 입력 합니다.

**Lync Server Management Shell을 사용 하 여 모임 초대를 사용자 지정 하려면**

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  **새 CsMeetingConfiguration** 또는 **Set-CsMeetingConfiguration** cmdlet을 실행 하 여 모임 초대 옵션을 만들거나 구성 합니다. 예를 들어 다음을 실행합니다.
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

