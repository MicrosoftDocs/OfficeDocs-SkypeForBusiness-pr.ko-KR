---
title: 내부 서버와 에지 서버 간의 연결 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27ca4874ac8c991828383afb524be1a1868bb7e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a>Lync Server 2013에서 내부 서버와 에지 서버 간의 연결 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

Lync Server 2013에서는 Edge 서버와 내부 서버 간의 연결을 확인 하는 데 도움이 되는 별도의 유효성 검사 마법사가 제공 됩니다. Lync Server 2013에 Edge 서버를 설치할 때 연결의 유효성 검사가 자동으로 완료 됩니다.

중앙 관리 저장소가 있는 내부 컴퓨터에서 Windows PowerShell **CsManagementStoreReplicationStatus** cmdlet을 실행 하 여 edge에 대 한 구성 정보 복제의 유효성을 검사할 수 있습니다 (또는 Lync Server 2013 Core 구성 요소 (ocscore. msi)가 설치 되어 있는 도메인에 가입 된 컴퓨터). 초기 결과에는 복제용으로 "True" 대신 상태가 "False"로 표시 될 수 있습니다. 이 경우 **CsManagementStoreReplication** cmdlet을 실행 하 고 **Get-CsManagementStoreReplicationStatus** 를 다시 실행 하기 전에 복제를 완료 하는 데 걸리는 시간을 허용 합니다.

Office Communications Server 원격 연결 분석기를 사용 하 여 원격 사용자 연결을 확인 하는 등 외부 사용자 연결을 개별적으로 확인할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 외부 사용자에 대 한 연결 확인](lync-server-2013-verify-connectivity-for-external-users.md)을 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

