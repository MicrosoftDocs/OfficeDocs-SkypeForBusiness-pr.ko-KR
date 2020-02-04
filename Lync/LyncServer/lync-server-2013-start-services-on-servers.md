---
title: 'Lync Server 2013: 서버에서 서비스 시작'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e6474071e7f95228f3c04c4931b4f899df68b40
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>Lync Server 2013의 서버에서 서비스 시작

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-09-03_

이 절차를 성공적으로 완료 하려면 RTCUniversalServerAdmins 그룹의 구성원 이거나 올바른 사용 권한을 위임한 사용자로 로그인 해야 합니다. 사용 권한 위임에 대 한 자세한 내용은 [Lync Server 2013의 대리인 설정 권한](lync-server-2013-delegate-setup-permissions.md)항목을 참조 하세요.

서버에 로컬 구성 저장소를 설치 하 고 Lync Server 2013 구성 요소를 설치 하 고 프런트 엔드 서버 또는 프런트 엔드 서버에서 인증서를 구성한 후에는 서버에서 Lync Server 2013 서비스를 시작 해야 합니다. 배포의 각 프런트 엔드 서버에서 서비스를 시작 하려면 다음 절차를 사용 합니다.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>스탠더드 버전 또는 프런트 엔드 서버에서 서비스를 시작 하려면

1.  Lync Server 배포 마법사의 **Lync server 2013** 페이지에서 **4 단계: 서비스 시작**옆의 **실행** 을 클릭 합니다.

2.  **서비스 시작** 페이지에서 **다음** 을 클릭 하 여 서버에서 Lync server 서비스를 시작 합니다.

3.  **명령 실행** 페이지에서 모든 서비스가 성공적으로 시작 되 면 **마침을**클릭 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 서버에서 서비스를 시작 하는 명령은 서비스가 실제로 시작 되었음을 보고 하는 가장 좋은 방법입니다. 서비스의 실제 상태를 반영 하지 않을 수 있습니다. 서비스 <STRONG>시작</STRONG> <STRONG>상태 (선택 사항)</STRONG> 를 즉시 사용 하 여 MICROSOFT Management Console (MMC)을 열고 서비스가 성공적으로 시작 되었는지 확인 하는 것이 좋습니다. Lync Server 서비스가 시작 되지 않은 경우 MMC에서 해당 서비스를 마우스 오른쪽 단추로 클릭 한 다음 <STRONG>시작</STRONG>을 클릭할 수 있습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

