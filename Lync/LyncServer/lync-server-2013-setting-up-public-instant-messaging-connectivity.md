---
title: 'Lync Server 2013: 공용 메신저 연결 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e77d8914a1f55ac10544591913a7347e271e9de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Lync Server 2013에서 공용 메신저 연결 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

조직에서 AOL과 공용 인스턴트 메시징 (IM) 연결을 지원 하려는 경우 Lync Server 배포 마법사를 사용 하 여 인증서를 요청할 수 없습니다. 대신 다음 절차의 단계를 수행 합니다.

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>공용 인스턴트 메시지 연결 설정

1.  프런트 엔드 서버에서 토폴로지 작성기를 엽니다. Edge 풀을 확장 한 다음 Edge 서버 또는 Edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다. 속성 편집을 선택 합니다.

2.  일반 아래에서 속성 편집에서이 Edge 풀에 페더레이션 사용 (포트 5061)을 선택 합니다. 확인을 클릭합니다.

3.  작업을 클릭 하 고 토폴로지를 선택한 다음 게시를 선택 합니다. 토폴로지를 게시할 것인지 묻는 메시지가 표시 되 면 다음을 클릭 합니다. 게시가 완료 되 면 마침을 클릭 합니다.

4.  Edge 서버에서 Lync Server 배포 마법사를 엽니다. Lync Server 시스템 설치 또는 업데이트를 클릭 한 다음 설정 또는 Lync Server 구성 요소 제거를 클릭 합니다. 다시 실행을 클릭 합니다.

5.  Lync Server 구성 요소를 설정 하 고 다음을 클릭 합니다. 요약 화면에 실행 되는 작업이 표시 됩니다. 배포가 완료 되 면 로그 보기를 클릭 하 여 사용 가능한 로그 파일을 봅니다. 마침을 클릭 하 여 배포를 완료 합니다.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>AOL과 공용 IM 연결을 지원 하기 위해 Edge 서버의 외부 인터페이스에 대 한 인증서 요청을 만들려면

1.  CA에서 필요한 템플릿을 사용할 수 있는 경우 Edge 서버에서 다음 Windows PowerShell cmdlet을 사용 하 여 인증서를 요청 합니다.
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Lync Server에 사용 되는 서식 파일의 기본 인증서 이름은 웹 서버입니다. 기본 서식 파일과 \<다른 서식\> 파일을 사용 해야 하는 경우에만 서식 파일 이름을 지정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 조직에서 AOL과 공용 IM 연결을 지원 하려는 경우 인증서 마법사 대신 Windows PowerShell을 사용 하 여 액세스에 지 서비스의 외부에 지에 할당할 인증서를 요청 해야 합니다. 이는 인증서 마법사가 인증서를 요청 하는 데 사용 하는 CA (인증 기관) 웹 서버 템플릿이 클라이언트 EKU 구성을 지원 하지 않기 때문입니다. Windows PowerShell을 사용 하 여 인증서를 만들려면 먼저 CA 관리자가 클라이언트 EKU를 지 원하는 새 템플릿을 만들고 배포 해야 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

