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
ms.openlocfilehash: 7d276dfdedacdcb00b4cc19a486fea1103c0bc8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532965"
---
# <a name="start-services-on-servers-for-lync-server-2013"></a>Lync Server 2013의 서버에서 서비스 시작

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-09-03_

이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그인하거나 올바른 권한을 위임받아야 합니다. 사용 권한 위임에 대 한 자세한 내용은 [Lync Server 2013의 대리인 설정 권한](lync-server-2013-delegate-setup-permissions.md)항목을 참조 하십시오.

서버에 로컬 구성 저장소를 설치한 후에는 Lync Server 2013 구성 요소를 설치 하 고 프런트 엔드 서버 또는 프런트 엔드 서버에서 인증서를 구성한 후에는 서버에서 Lync Server 2013 서비스를 시작 해야 합니다. 다음 절차에 따라 배포의 각 프런트 엔드 서버에서 서비스를 시작 합니다.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>Standard Edition Server 또는 프런트 엔드 서버에서 서비스를 시작하려면

1.  Lync Server 배포 마법사의 **Lync server 2013** 페이지에서 **4 단계: 서비스 시작**옆에 있는 **실행** 을 클릭 합니다.

2.  **서비스 시작** 페이지에서 **다음** 을 클릭 하 여 서버에서 Lync Server 서비스를 시작 합니다.

3.  **명령 실행** 페이지에서 모든 서비스가 정상적으로 시작되었으면 **마침**을 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 서버에서 서비스를 시작 하는 명령은 서비스가 실제로 시작 된 것을 보고 하는 최상의 방법입니다. 서비스의 실제 상태를 반영 하지 않을 수 있습니다. 서비스 <STRONG>시작</STRONG> <STRONG>(선택 사항)</STRONG> 을 사용 하 여 MMC (Microsoft Management Console)를 열고 서비스가 정상적으로 시작 되었는지 확인 하는 것이 좋습니다. Lync Server 서비스가 시작 되지 않은 경우 MMC에서 해당 서비스를 마우스 오른쪽 단추로 클릭 한 다음 <STRONG>시작</STRONG>을 클릭할 수 있습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

