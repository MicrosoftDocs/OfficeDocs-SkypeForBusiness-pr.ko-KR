---
title: 'Lync Server 2013: 새 웹 서비스 구성 설정 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c3e81379eb411b2b77129e51b59ce675887394
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 새 웹 서비스 구성 설정 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

**웹 서비스** 페이지를 사용 하 여 Lync Server 2013 관련 웹 서버 및 웹 서비스에 액세스 하기 위한 인증 방법을 구성할 수 있습니다.

새 웹 서비스 정책을 만들려면 다음 단계를 따르세요.

<div>

## <a name="to-create-new-web-service-configuration-settings"></a>새 웹 서비스 구성 설정을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **웹 서비스**를 클릭 합니다.

4.  **웹 서비스** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.
    
      - 사이트에 대 한 웹 서비스를 구성 하려면 **사이트 구성을**클릭 합니다. **사이트 선택**에서 웹 서비스 정책이 사이트를 적용 하는 사이트를 클릭 하 고 **확인**을 클릭 합니다.
    
      - 풀에 대 한 웹 서비스를 구성 하려면 **풀 구성을**클릭 합니다. **서비스 선택**에서 웹 서비스 정책이 적용 되는 서비스를 클릭 하 고 **확인**을 클릭 합니다.

5.  **새 웹 서비스 설정**에서 **windows 통합 인증**에서 **협상**, **windows 통합 인증**또는 **없음**을 선택 합니다.

6.  해당 환경의 클라이언트 및 지원 기능에 따라 다음 중 하나 이상을 선택 합니다.
    
      - Pin **인증** 을 사용 하 여 클라이언트가 pin 번호를 사용 하 여 인증할 수 있도록 합니다.
    
      - **인증서 인증을 사용 하도록 설정** 하 여 풀의 서버가 클라이언트에 인증서를 발급 하도록 합니다.
    
      - **인증서 체인 다운로드 사용** 인증 인증서를 사용 하 여 서버에 제공 되는 경우 해당 인증서의 인증서 체인을 다운로드 합니다.

7.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

