---
title: 'Lync Server 2013: 웹 팜 Fqdn 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46cca998a35a7519675cd787f5887f2a65d491c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Lync Server 2013에 대 한 웹 팜 Fqdn 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-29_

토폴로지 작성기에서 Standard Edition server, 프런트 엔드 풀, 디렉터 또는 디렉터 풀의 구성을 정의한 경우 외부 웹 서비스 FQDN (정규화 된 도메인 이름)을 구성 합니다. Standard Edition server 또는 프런트 엔드 풀에 있는 클라이언트의 로그온 프로세스 중에 구성 된 웹 서비스 Fqdn은 대역내 프로비저닝을 통해 전송 됩니다. 외부 웹 서비스 URL을 추가 하거나 변경 해야 하는 경우이 항목의 절차를 사용 하 여 토폴로지 작성기를 사용 하 여 웹 서비스 구성을 구성 하거나 다시 구성할 수 있습니다.

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>웹 서비스에 대해 외부 풀 FQDN을 구성하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  토폴로지 작성기의 콘솔 트리 **Standard Edition 프런트 엔드**, **Enterprise Edition 프런트 엔드**및 **감독**아래에서 편집 해야 하는 풀 이름을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.

3.  **웹 서비스** 섹션에서 **외부 웹 서비스 FQDN**을 추가하거나 편집합니다.

4.  HTTP 및 HTTPS 모두에 대해 **수신 대기 포트**를 검토하여 조정합니다. 기본값은 다음과 같습니다.
    
      - **수신 대기 포트:** HTTP 8080, HTTPS 4443
    
      - **게시된 포트:** HTTP 80, HTTPS 443
    
    **수신 대기 포트**는 역방향 프록시로부터의 요청을 수신하도록 구성된 외부 웹 서비스의 포트이며, **게시된 포트**는 역방향 프록시에 의해 외부적으로 게시되어 인밴드 구축 동안 클라이언트와 통신하는 포트입니다.

5.  추가 및 업데이트 작업을 완료했으면 **확인**을 클릭하여 계속 진행합니다.

6.  **Lync Server 2013**를 마우스 오른쪽 단추로 클릭 한 다음 **게시**를 클릭 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 게시가 성공적으로 완료되면 추가적으로 진행해야 할 단계가 있음을 알려주는 링크가 나타날 수 있습니다. 링크를 클릭 하면 추가, 제거 또는 변경 된 구성 요소에 대 한 구성을 업데이트 하기 위해 각 서버에서 Lync Server 배포 마법사를 다시 실행 해야 하는 토폴로지 작성기의 변경 사항으로 인해 영향을 받는 서버 목록이 표시 됩니다.

    
    </div>

7.  조직의 각 Standard Edition server, 프런트 엔드 풀, 디렉터 또는 디렉터 풀에 대해이 단계를 반복 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

