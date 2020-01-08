---
title: Lync Server 2010 환경 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248d779bc43b7c3e220728222aca030036f17e00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>Lync Server 2010 환경 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

Lync server 2010을 함께 사용 하는 상태에서 Lync 서버 2013를 배포 하기 전에 Lync Server 2010 서비스가 구성 및 시작 되었는지 확인 해야 합니다. Lync Server 2013 파일럿 풀을 배포 하기 전에 레거시 환경에 존재 하는 주요 서비스 및 기능을 확인 하는 것이 중요 합니다. Microsoft Lync Server 2013 XMPP를 레거시 XMPP 배포를 사용 하 여 공존 상태로 배포 하기 전에 레거시 XMPP 서비스가 구성 및 시작 되었는지 확인 하 고 레거시 XMPP 구성이 지 원하는 페더레이션 파트너를 확인 해야 합니다. 레거시 Lync Server 2010 배포 확인에는 다음이 수반 됩니다.

  - Lync Server 2010 서비스가 시작 되었는지 확인

  - Lync Server 2010에서 토폴로지와 사용자를 검토 합니다.

  - 페더레이션 및 Edge 서버 설정을 확인 하는 중입니다.

  - XMPP 서비스 및 페더레이션 파트너를 확인 합니다.

**Lync Server 2010 서비스가 시작 되었는지 확인**

1.  Lync Server 2010 프런트 엔드 서버에서 관리 도구\\서비스 애플릿으로 이동 합니다.

2.  프런트 엔드 서버에서 다음 서비스가 실행 중인지 확인 합니다.
    
    프런트 엔드(images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "서버에서 실행 중인 서비스의") ![프런트 엔드 서버 목록에서 실행 중인 서비스 목록]

**Lync Server 제어판에서 Lync Server 2010 토폴로지 검토**

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 CsAdministrator 또는 CsUserAdministrator 관리 역할의 구성원 인 계정을 사용 하 여 프런트 엔드 서버에 로그온 합니다.

2.  Lync Server 제어판을 엽니다.

3.  **토폴로지**를 선택 합니다. Lync Server 2010 배포의 다양 한 서버가 나열 되는지 확인 합니다.
    
    ![Lync server 2010 제어판 토폴로지 페이지](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync server 2010 제어판 토폴로지 페이지")

**Lync server 제어판에서 Lync Server 2010 사용자를 검토 하려면**

1.  Lync Server 제어판을 엽니다.

2.  **사용자** 를 선택 하 고 **찾기를**클릭 합니다.

3.  **등록자 그룹** 열이 나열 된 각 사용자의 Lync Server 2010 풀을 가리키는지 확인 합니다.
    
    ![Lync server 2010 제어판 목록 사용자]에 게(images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync server 2010 제어판의 목록을") 표시 합니다.

**Lync Server 2010 Edge 및 페더레이션 설정을 확인 하려면**

1.  토폴로지 작성기를 시작 합니다.

2.  **기존 배포에서 토폴로지 다운로드를**선택 합니다.

3.  파일 이름을 선택 하 고 기본 tbxml 파일 형식을 사용 하 여 토폴로지를 저장 합니다.

4.  Lync Server 2010 노드를 확장 하 여 배포에 다양 한 서버 역할을 표시 합니다.

5.  사이트 노드를 선택 하 고 **사이트 페더레이션 경로 할당** 값이 설정 되어 있는지 확인 합니다.
    
    ![토폴로지 작성기, 사이트 페더레이션 경로](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "토폴로지 작성기, 사이트 페더레이션 경로")

6.  다음으로 Standard Edition Server 또는 Enterprise Edition 프런트 엔드 풀을 선택 합니다. **연결**아래 미디어에 대 한 Edge 풀이 구성 되었는지 확인 합니다.
    
    서버 및 풀을 보여 주는 서버 및 풀(images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "토폴로지 작성기") 를 ![보여 주는 토폴로지 작성기]

7.  마지막으로 Edge 풀을 선택 하 고 다음 홉 풀이 **다음 홉 선택**아래에 구성 되어 있는지 확인 합니다.
    
    ![토폴로지 작성기, 다음 홉 선택](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "토폴로지 작성기, 다음 홉 선택")

**레거시 XMPP 페더레이션 파트너 구성 확인**

1.  레거시 XMPP 서버에서 관리 도구\\서비스 애플릿으로 이동 합니다.

2.  Office Communications Server XMPP 게이트웨이 서비스가 시작 되었는지 확인 합니다.
    
    ![Office Communications server XMPP 게이트웨이 서비스](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "office communications Server Xmpp 게이트웨이 서비스")

</div>

<span> </span>

</div>

</div>

</div>

