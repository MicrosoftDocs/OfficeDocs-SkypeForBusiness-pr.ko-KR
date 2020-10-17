---
title: 'Lync Server 2013: 토폴로지 디자인 확인'
description: 'Lync Server 2013: 토폴로지 디자인을 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb1e65343aacddbc11d3b909dfdff715503cab93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560194"
---
# <a name="verify-the-topology-design-in-lync-server-2013"></a>Lync Server 2013에서 토폴로지 디자인 확인

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-01-02_

토폴로지 작성기가 토폴로지를 자동으로 확인 합니다. 모든 토폴로지 오류는 유효성 검사 오류로 식별 되며 서버 역할 옆에 유효성 검사 오류 아이콘으로 표시 됩니다. 또한 토폴로지가 배포의 토폴로지를 올바르게 나타내는지도 확인해야 합니다.

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>게시 전에 토폴로지를 확인하려면

1.  모든 단순 URL이 올바르게 구성되어 있는지 확인합니다.

2.  SQL Server 기반 서버가 온라인 상태이 고 필요한 방화벽 규칙을 포함 하 여 토폴로지 작성기가 설치 된 컴퓨터에서 해당 서버를 사용할 수 있는지 확인 합니다.

3.  파일 공유를 사용할 수 있으며 적절 한 사용 권한이 정의 되어 있는지 확인 합니다.

4.  배포 요구 사항을 충족하는 올바른 서버 역할이 토폴로지에 정의되어 있는지 확인합니다.

5.  Active Directory 도메인 서비스에 서버가 있는지 확인 합니다. 서버를 도메인에 가입시킨 경우에는 이 확인이 자동으로 수행됩니다.

토폴로지를 확인한 결과 유효성 검사 오류가 없으면 토폴로지를 게시할 수 있습니다. 유효성 검사 오류가 있는 경우에는 토폴로지를 게시하기 전에 먼저 오류를 수정해야 합니다. 토폴로지를 게시 하는 방법에 대 한 자세한 내용은 [Publish the topology in The Lync Server 2013](lync-server-2013-publish-the-topology.md)을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

