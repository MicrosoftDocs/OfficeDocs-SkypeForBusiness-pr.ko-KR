---
title: 'Lync Server 2013: 사전 인증서 요청(선택 사항)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6b376a2c1652dcaf255e39f6d112568b7c3bf31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Lync Server 2013에 대한 사전 인증서 요청(선택 사항)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

각 Enterprise Edition 프런트 엔드 서버, Standard Edition Server, 디렉터, Edge 서버 및 독립 실행형 조정 서버를 포함 하 여 Lync Server 2013을 실행 하는 모든 내부 서버에 인증서가 필요 합니다. 내부 서버에는 내부 엔터프라이즈 CA (인증 기관)가 권장 되지만 공용 CA를 사용할 수도 있습니다. 인증서 요구 사항과 공개 CA 사용에 대 한 자세한 내용은 계획 문서에서 [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-internal-servers.md) 참조 하세요.

Lync Server 2013 설정에는 배포 중에 인증서 요청, 할당, 설치 작업을 용이 하 게 하는 인증서 마법사가 포함 되어 있습니다. 서버를 설치 하기 전에 인증서를 요청 하는 경우 (예를 들어 서버를 실제 배포 하는 동안 시간을 절약 하려면) Lync Server 2013 관리 도구가 설치 된 컴퓨터를 사용 하거나 인증서 요청을 사용 하 여 수행할 수 있습니다. 인증서를 내보낼 수 있고 필요한 모든 주체 대체 이름을 포함 하 고 있는지 확인 하는 경우 조직에 정의 된 절차 미리 인증서 요청은 선택 사항입니다. 미리 요청 하지 않으면 인증서를 필요로 하는 각 서버 설정의 일부로 요청 해야 합니다.

이 배포 설명서에서는 인증서 마법사를 사용 하 여 설치 프로세스의 일부로 인증서를 요청 하는 절차를 제공 합니다. [Lync server 2013에서 서버의 인증서 구성](lync-server-2013-configure-certificates-for-servers.md), [lync Server 2013에서 디렉터에 대 한 인증서 구성](lync-server-2013-configure-certificates-for-the-director.md),이 배포 설명서의 [Lync server 2013에서 중재 서버용 파일 설치](lync-server-2013-install-the-files-for-mediation-server.md) 섹션을 참조 하세요. 인증서를 미리 요청 하는 경우 배포 시 요청 하는 대신 해당 섹션의 인증서 배포 절차를 적절 하 게 수정 하 여 인증서를 가져오고 할당 해야 합니다.

<div>


> [!NOTE]  
> Lync Server 2013에는 Windows Vista, Windows Server&nbsp;2008, windows server&nbsp;2008&nbsp;R2, Windows 7 운영 체제, Lync Phone Edition을 실행 하는 클라이언트의 연결에 대 한 SHA-256 인증서 지원이 포함 되어 있습니다. SHA-256를 사용 하 여 외부 액세스를 지원 하기 위해 외부 인증서는 SHA-256를 사용 하 여 공용 CA에서 발급 합니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

