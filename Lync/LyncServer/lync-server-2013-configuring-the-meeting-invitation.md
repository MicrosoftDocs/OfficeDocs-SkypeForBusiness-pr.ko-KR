---
title: 'Lync Server 2013: 모임 초대 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5697605b4560fc91a153869204756f0ddda356fc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Lync Server 2013에서 모임 초대 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-16_

모임 초대 본문에 다음과 같은 선택적 항목을 포함 하 여 Lync 2013에 대 한 온라인 모임 추가 기능을 통해 전송 되는 모임 초대를 사용자 지정할 수 있습니다.

  - **조직의 로고** 로고 URL 옵션을 사용 하 여 모임 초대에 조직의 로고를 추가 합니다. 모임 초대를 조직 외부의 사용자에 게 전송 하는 경우 이미지는 공개적으로 사용할 수 있는 URL에 배치 해야 합니다. 지원 되는 이미지 형식은 GIF 및 JPG입니다. Lync Server 2013에서는 이미지에 크기 제한이 없는 URL을 저장 하지만 최상의 결과를 위해 이미지의 최대 크기는 30 픽셀, 너비 188 픽셀 이어야 합니다.

  - **사용자 지정 도움말 또는 지원 링크** 조직의 도움말 또는 지원 팀 웹 사이트에 대 한 URL을 추가 합니다. 모임 초대를 조직 외부의 사용자에 게 전송 하는 경우 URL을 공개적으로 사용할 수 있어야 합니다. 최대 URL 길이는 1kb입니다.

  - **법적 고 지 사항 텍스트** 모든 모임 초대에 표시할 법적 텍스트 또는 고 지 사항에 대 한 URL을 추가 합니다. 모임 초대를 조직 외부의 사용자에 게 전송 하는 경우 URL을 공개적으로 사용할 수 있어야 합니다. 최대 URL 길이는 1kb입니다.

  - **사용자 지정 바닥글 텍스트** 초대에 사용자 지정 바닥글로 렌더링 될 텍스트를 추가 합니다. 추가할 수 있는 최대 텍스트 길이는 2kb입니다.

Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 이러한 옵션을 구성할 수 있습니다.

<div>


**Lync Server 제어판을 사용 하 여 모임 초대를 사용자 지정 하려면**

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 표시줄에서 **회의**, **모임 구성**을 차례로 클릭합니다.

4.  **모임 구성** 페이지에서 **새로 만들기**를 클릭하고 다음 중 하나를 수행합니다.
    
      - 사이트 수준 정책을 만들려면 **사이트 구성**을 클릭합니다. **사이트 선택** 검색 필드에 모임 참가 설정을 정의할 사이트의 이름 일부나 전체를 입력합니다. 사이트 결과 목록에서 원하는 사이트를 클릭한 다음 **확인**을 클릭합니다.
    
      - 풀 수준 정책을 만들려면 **풀 구성**을 클릭합니다. **서비스 선택** 검색 필드에 모임 참가 설정을 정의할 풀 서비스의 이름 일부나 전체를 입력합니다. 서비스 결과 목록에서 원하는 풀을 클릭하고 **확인**을 클릭합니다.

5.  다음을 수행합니다.
    
      - **로고 url** 필드에 조직의 로고 이미지 URL을 입력 합니다.
    
      - **도움말 url** 필드에 조직의 도움말 또는 지원 사이트에 대 한 URL을 입력 합니다.
    
      - 법적 고 지 사항 **텍스트** 필드에 모임 초대에 포함할 법적 텍스트 또는 고 지 사항에 대 한 URL을 입력 합니다.
    
      - **사용자 지정 바닥글 텍스트** 필드에 바닥글 텍스트를 2kb로 입력 합니다.

**Lync Server 관리 셸을 사용 하 여 모임 초대를 사용자 지정 하려면**

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  **Get-csmeetingconfiguration** 또는 **get-csmeetingconfiguration** cmdlet을 실행 하 여 모임 초대 옵션을 만들거나 구성 합니다. 예를 들어 다음을 실행합니다.
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

