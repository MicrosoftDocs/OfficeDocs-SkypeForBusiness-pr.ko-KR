---
title: 'Lync Server 2013: 호출 허용 제어 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e768cdd11d92b3aab5ce849f91cc1a422f119407
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013에 대 한 통화 허용 제어 배포 검사 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

다음 검사 목록을 사용 하 여 CAC (call 허용 제어)를 배포 하는 데 필요한 모든 구성 작업을 완료 했는지 확인 합니다.

  - 하나 이상의 Edge 서버가 배포 된 경우 각 외부 인터페이스 IP 주소를 네트워크 구성 설정의 서브넷 목록에 추가 해야 하며 비트 마스크는 32입니다. 또한이 서브넷 (IP 주소)을 A/V Edge 서비스가 배포 된 지리적 위치에 대 한 네트워크 사이트 ID와 연결 해야 합니다.
    
    <div>
    

    > [!NOTE]  
    > Edge 서버는 CAC를 구현 하지 않아도 됩니다.

    
    </div>

  - Lync server 제어판을 통해 또는 [Lync server 2013에서 호출 허용 제어 사용](lync-server-2013-enable-call-admission-control.md)에 지정 된 대로 cmdlet을 실행 하 여 CAC를 사용 하도록 설정 합니다.

  - 모든 중앙 사이트에서 CAC가 사용 하도록 설정 되어 있는지 확인 합니다. 토폴로지 작성기를 통해이 작업을 수행할 수 있습니다. 게시할 때 경고가 생성 되 면이를 무시 *하지 마세요* .

  - 엔터프라이즈 네트워크에서 관리 되는 모든 서브넷이 네트워크 구성 설정에서 구성 되어 있는지 확인 합니다. 또한 [Lync Server 2013의 네트워크 사이트와 서브넷 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)에 설명 된 대로 모든 서브넷을 네트워크 사이트에 연결 하는 것이 중요 합니다.

  - 모든 프런트 엔드 서버의 서브넷 또는 IP 주소, Survivable Branch 기기 (SBAs), 오디오/비디오 회의 서버 (별도의 풀에 있는 경우) 및 중재 서버가 네트워크 구성 설정에 구성 되어 있는지 확인 합니다.

</div>

<span> </span>

</div>

</div>

</div>

