---
title: 파일럿 Edge 서버 배포
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>파일럿 Edge 서버 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

이 항목에서는 Lync Server 2013 Edge 서버를 배포 하기 전에 알아야 하는 구성 설정을 강조 합니다. 이 섹션에서는 파일럿 Edge 풀 배포의 일부로 고려해 야 하는 주요 요점만 중점적으로 설명 합니다. 자세한 단계는 배포 설명서의 [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하 고 외부 사용자 액세스에 대 한 구성 정보도 제공 합니다.

**새 Edge 풀 정의** 마법사를 탐색할 때 다음 단계에 표시 된 키 구성 설정을 검토 합니다. **새 Edge 풀 정의** 마법사의 몇 페이지만 표시 됨에 유의 하세요.

**Edge 풀 정의**

1.  토폴로지 작성기를 사용 하 여 파일럿 풀 토폴로지를 엽니다.

2.  Lync Server 2013 노드로 이동 합니다. **Edge 풀**을 마우스 오른쪽 단추로 클릭 하 고 **새 edge 풀**을 클릭 합니다.
    
    ![새 Edge 풀을 정의 합니다].(images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "새 edge 풀") 대화 상자 정의

3.  Edge 풀은 **여러 컴퓨터 풀** 또는 **단일 컴퓨터 풀**일 수 있습니다.
    
    Edge ![풀 fqdn 대화 상자 정의](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "edge 풀 fqdn 대화 상자 정의")

4.  **기능 선택** 페이지에서 페더레이션 또는 xmpp 페더레이션을 사용 하지 않습니다. 페더레이션 및 XMPP 페더레이션은 현재 레거시 Office 통신 서버 2007 R2 Edge 서버를 통해 라우트됩니다. 이러한 기능은 이후 마이그레이션 단계에서 구성 됩니다.
    
    ![기능 선택 대화 상자](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "기능 선택 대화 상자")

5.  다음 마법사 페이지를 계속 진행 합니다. **IP 옵션**, **외부 FQDN**, **내부 IP 주소 정의**, **외부 ip 주소 정의**를 차례로 선택 합니다.

6.  **다음 홉 정의** 페이지에서 Lync Server 2013 Edge 풀의 다음 홉에 대 한 디렉터를 선택 합니다.
    
    ![새 Edge 풀 정의 대화 상자, 다음 홉 풀 목록](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "정의 새 edge 풀 대화 상자, 다음 홉 풀 목록")

7.  **프런트 엔드 풀 연결** 페이지에서 지금은이 Edge 풀과 풀을 연결 하지 않습니다. 외부 미디어 트래픽은 현재 레거시 Office 통신 서버 2007 R2 Edge 서버를 통해 라우트됩니다. 이 설정은 이후 마이그레이션 단계에서 구성 됩니다.
    
    ![새 Edge 풀을 정의]합니다.(images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "새 edge 풀 정의 대화 상자")

8.  **마침을** 클릭 한 다음 토폴로지를 **게시** 합니다.

9.  배포 설명서에서 [Lync server 2013에 대 한 Edge 서버 설치](lync-server-2013-install-edge-servers.md) 의 단계에 따라 새 Edge 서버에 파일을 설치 하 고 인증서를 구성한 다음 서비스를 시작 합니다.

배포 설명서의 [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 항목의 지침을 준수 하는 것이 매우 중요 합니다. 이 섹션에서는 이러한 서버 역할을 설치할 때 구성 설정에 대 한 몇 가지 지침만 제공 합니다.

이제 Lync Server 2013 Edge 서버 배포와 병행 하 여 BackCompatSite의 현재 상태에 따라 표시 되는 레거시 Office 통신 서버 2007 R2 Edge 서버 배포를 사용 해야 합니다. 페더레이션이 Office Communications Server 2007 R2 감독을 사용 하도록 구성 되어 있습니다. 두 배포가 모두 제대로 실행 되 고 있는지 확인 하 고 서비스가 시작 되며 다음 단계로 이동 하기 전에 각 배포를 관리할 수 있습니다.

(images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Ocs에 지 서버를 보여 주는") ![ocs Edge 서버 토폴로지 작성기를 보여 주는 토폴로지 작성기]

</div>

<span> </span>

</div>

</div>

</div>

