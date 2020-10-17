---
title: 'Lync Server 2013: 사전 인증서 요청 (선택 사항)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7e671fe61f5d8b9e43593bf99e0ecf0e1e37109
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511965"
---
# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Lync Server 2013에 대해 사전 인증서 요청 (선택 사항)

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

각 Enterprise Edition 프런트 엔드 서버, Standard Edition Server, 디렉터,에 지 서버 및 독립 실행형 중재 서버를 포함 하 여 Lync Server 2013을 실행 하는 모든 내부 서버에 인증서가 필요 합니다. 내부 서버에는 내부 엔터프라이즈 CA(인증 기관)를 사용하는 것이 좋지만 공용 CA를 사용할 수도 있습니다. 인증서 요구 사항 및 공용 CA 사용에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-internal-servers.md) 참조 하십시오.

Lync Server 2013 설치 프로그램에는 배포 중에 인증서를 요청, 할당 및 설치 하는 작업을 용이 하 게 하는 인증서 마법사가 포함 되어 있습니다. 서버를 설치 하기 전에 인증서를 요청 하려는 경우 (예를 들어 서버를 실제 배포 하는 동안 시간을 절약 하기 위해), 인증서를 내보낼 수 있고 필요한 주체 대체 이름을 모두 포함 하는 경우 Lync Server 2013 관리 도구가 설치 되어 있는 컴퓨터를 사용 하거나 조직에 정의 된 인증서 요청 절차를 사용 하 여이 작업을 수행 합니다. 사전에 인증서를 요청 하는 것은 선택 사항입니다. 이를 사전에 요청 하지 않으면 인증서가 필요한 각 서버 설정의 일부로 요청 해야 합니다.

이 배포 설명서에서는이 배포 설명서의 lync server [2013에서 서버에 대](lync-server-2013-configure-certificates-for-servers.md)한 인증서 구성, lync [Server 2013의 디렉터에 대 한 인증서 구성](lync-server-2013-configure-certificates-for-the-director.md), [중재 2013 서버용 파일 설치](lync-server-2013-install-the-files-for-mediation-server.md) 의 설명에 따라 인증서 마법사를 사용 하 여 인증서를 설치 프로세스의 일부로 요청 하는 절차를 제공 합니다. 인증서를 사전에 요청하려면 배포 시 인증서를 요청하는 대신 인증서를 가져오고 할당하는 관련 섹션에서 인증서 배포 절차를 수정해야 합니다.

<div>


> [!NOTE]  
> Lync Server 2013에는 Windows Vista, Windows Server &nbsp; 2008, Windows server &nbsp; 2008 &nbsp; R2 및 windows 7 운영 체제 및 Lync Phone Edition을 실행 하는 클라이언트의 연결에 대 한 SHA-256 인증서에 대 한 지원이 포함 되어 있습니다. SHA-256을 사용한 외부 액세스를 지원하기 위해 SHA-256을 사용하여 공용 CA에서 외부 인증서가 발급됩니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

