---
title: 파일럿 Edge 서버 배포
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27b7cf106cb8c65f01a1c1935ff98a8f9d428b27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502935"
---
# <a name="deploy-pilot-edge-server"></a>파일럿 Edge 서버 배포

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

이 항목에서는 Lync Server 2013에 지 서버를 배포 하기 전에 알아야 하는 구성 설정을 중점적으로 설명 합니다. 또한 이 섹션에서는 파일럿 에지 풀 배포 중에 고려해야 하는 핵심 사항에 대해서도 설명합니다. 자세한 단계에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하 고, 외부 사용자 액세스에 대 한 구성 정보도 제공 합니다.

**새 에지 풀 정의** 마법사를 탐색할 때 다음 단계에 표시된 핵심 구성 설정을 검토합니다. **새 에지 풀 정의** 마법사의 일부 페이지만 표시됩니다.

**에지 풀을 정의합니다.**

1.  토폴로지 작성기를 사용하여 파일럿 풀 토폴로지를 엽니다.

2.  Lync Server 2013 노드로 이동 합니다. **에지 풀**을 마우스 오른쪽 단추로 클릭하고 **새 에지 풀**을 클릭합니다.
    
    ![새에 지 풀 정의 대화 상자](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "새에 지 풀 정의 대화 상자")

3.  에지 풀은 **다중 컴퓨터 풀** 또는 **단일 컴퓨터 풀**일 수 있습니다.
    
    ![에 지 풀 FQDN 정의 대화 상자](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "에 지 풀 FQDN 정의 대화 상자")

4.  **기능 선택** 페이지에서 페더레이션을 사용하도록 설정하지 마십시오. 페더레이션 및 XMPP 페더레이션은 현재 레거시 Office Communications Server 2007 R2에 지 서버를 통해 라우팅됩니다. 이러한 기능은 마이그레이션의 이후 단계에서 구성됩니다.
    
    ![기능 선택 대화 상자](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "기능 선택 대화 상자")

5.  그런 후 **IP 옵션 선택**, **외부 FQDN**, **내부 IP 주소 정의** 및 **외부 IP 주소 정의** 마법사 페이지를 계속해서 완료합니다.

6.  **다음 홉 정의** 페이지에서 Lync Server 2013에 지 풀의 다음 홉에 대 한 디렉터를 선택 합니다.
    
    ![새에 지 풀 정의 대화 상자, 다음 홉 풀 목록](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "새에 지 풀 정의 대화 상자, 다음 홉 풀 목록")

7.  **프런트 엔드 풀 연결** 페이지에서 지금은이에 지 풀과 풀을 연결 하지 않습니다. 외부 미디어 트래픽은 현재 레거시 Office Communications Server 2007 R2에 지 서버를 통해 라우팅됩니다. 이 설정은 마이그레이션의 이후 단계에서 구성됩니다.
    
    ![새에 지 풀 정의 대화 상자](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "새에 지 풀 정의 대화 상자")

8.  **마침**을 클릭한 후 토폴로지를 **게시**합니다.

9.  배포 설명서의 [설치에 지 서버 2013](lync-server-2013-install-edge-servers.md) 의 단계에 따라 새에 지 서버에 파일을 설치 하 고, 인증서를 구성 하 고, 서비스를 시작 합니다.

배포 설명서에서 [Lync Server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 항목에 설명 된 지침을 따르는 것이 매우 중요 합니다. 이 섹션에는 단순히 이러한 서버 역할을 설치할 때의 구성 설정에 대한 일부 지침만 제공됩니다.

이제 Lync Server 2013에 지 서버 배포와 동시에 BackCompatSite에 표시 되는 레거시 Office Communications Server 2007 R2 Edge 서버 배포를 수행 해야 합니다. 페더레이션이 Office Communications Server 2007 R2 디렉터를 사용 하도록 구성 되어 있습니다. 두 배포가 올바르게 실행되고 있는지, 서비스가 시작되었는지, 다음 단계로 이동하기 전에 각 배포를 관리할 수 있는지를 확인합니다.

![OCS에 지 서버를 보여 주는 토폴로지 작성기](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "OCS에 지 서버를 보여 주는 토폴로지 작성기")

</div>

<span> </span>

</div>

</div>

</div>

