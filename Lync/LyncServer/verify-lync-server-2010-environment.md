---
title: Lync Server 2010 환경 확인
description: Lync Server 2010 environment를 확인 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 570fd2a9efdc90899ff4f91146b7aeb1991f6764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555584"
---
# <a name="verify-lync-server-2010-environment"></a>Lync Server 2010 환경 확인

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

Lync server 2010와 함께 동시 사용 상태에 Lync Server 2013을 배포 하기 전에 Lync server 2010 서비스가 구성 및 시작 되었는지 확인 해야 합니다. Lync Server 2013 파일럿 풀을 배포 하기 전에 레거시 환경에 있는 주요 서비스와 기능을 파악 하는 것이 중요 합니다. 레거시 XMPP 배포를 사용 하 여 Microsoft Lync Server 2013 XMPP를 공존 상태로 배포 하기 전에 레거시 XMPP 서비스가 구성 및 시작 되었는지 확인 하 고 레거시 XMPP 구성에서 지 원하는 페더레이션 파트너를 확인 해야 합니다. 레거시 Lync Server 2010 배포를 확인 하면 다음이 수반 됩니다.

  - Lync Server 2010 서비스가 시작 되었는지 확인

  - Lync Server 2010에서 토폴로지와 사용자를 검토 합니다.

  - 페더레이션 및 에지 서버 설정 확인

  - XMPP 서비스 및 페더레이션 파트너 확인

**Lync Server 2010 서비스가 시작 되었는지 확인**

1.  Lync Server 2010 프런트 엔드 서버에서 관리 도구 \\ 서비스 애플릿으로 이동 합니다.

2.  프런트 엔드 서버에서 다음 서비스가 실행되고 있는지 확인합니다.
    
    ![프런트 엔드 서버에서 실행 중인 서비스 목록](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "프런트 엔드 서버에서 실행 중인 서비스 목록")

**Lync Server 제어판에서 Lync Server 2010 토폴로지 검토**

1.  RTCUniversalServerAdmins 그룹의 구성원이나 CsAdministrator 또는 CsUserAdministrator 관리자 역할의 구성원인 계정으로 프런트 엔드 서버에 로그온합니다.

2.  Lync Server 제어판을 엽니다.

3.  **토폴로지**를 선택합니다. Lync Server 2010 배포의 다양 한 서버가 나열 되는지 확인 합니다.
    
    ![Lync Server 2010 제어판 토폴로지 페이지](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 제어판 토폴로지 페이지")

**Lync Server 제어판에서 Lync Server 2010 사용자를 검토 하려면**

1.  Lync Server 제어판을 엽니다.

2.  **사용자**를 선택한 후 **찾기**를 클릭합니다.

3.  나열 된 각 사용자에 대해 **등록자 풀** 열이 Lync Server 2010 풀을 가리키는지 확인 합니다.
    
    ![Lync Server 2010 제어판 사용자가 나열 됩니다.](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 제어판 사용자가 나열 됩니다.")

**Lync Server 2010 Edge 및 페더레이션 설정을 확인 하려면**

1.  토폴로지 작성기를 시작합니다.

2.  **기존 배포에서 토폴로지 다운로드**를 선택합니다.

3.  파일 이름을 선택하고 기본 .tbxml 파일 형식으로 토폴로지를 저장합니다.

4.  Lync Server 2010 노드를 확장 하 여 배포의 다양 한 서버 역할을 표시 합니다.

5.  사이트 노드를 선택하고 **사이트 페더레이션 경로 지정** 값이 설정되어 있는지 확인합니다.
    
    ![토폴로지 작성기, 사이트 페더레이션 경로](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "토폴로지 작성기, 사이트 페더레이션 경로")

6.  그런 다음 Standard Edition Server 또는 Enterprise Edition 프런트 엔드 풀을 선택합니다. **연결** 아래에서 미디어에 대한 에지 풀이 구성되었는지 확인합니다.
    
    ![서버 및 풀을 보여 주는 토폴로지 작성기](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "서버 및 풀을 보여 주는 토폴로지 작성기")

7.  마지막으로 에지 풀을 선택하고 **다음 홉 선택** 아래에서 다음 홉 풀이 구성되어 있는지 확인합니다.
    
    ![토폴로지 작성기, 다음 홉 선택](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "토폴로지 작성기, 다음 홉 선택")

**레거시 XMPP 페더레이션 파트너 구성 확인**

1.  레거시 XMPP 서버에서 관리 도구 \\ 서비스 애플릿으로 이동 합니다.

2.  Office Communications Server XMPP 게이트웨이 서비스가 시작되었는지 확인합니다.
    
    ![Office Communications Server XMPP 게이트웨이 서비스](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP 게이트웨이 서비스")

</div>

<span> </span>

</div>

</div>

</div>

