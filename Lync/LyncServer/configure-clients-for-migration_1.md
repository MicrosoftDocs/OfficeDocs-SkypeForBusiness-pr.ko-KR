---
title: 마이그레이션을 위한 클라이언트 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710a5cf6cb23b91431b340c44ebe6ff2738b0822
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40979211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>마이그레이션을 위한 클라이언트 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-21_

이 항목에는 Lync Server 2013로 마이그레이션하기 전에 수행 해야 하는 권장 클라이언트 배포 단계가 포함 되어 있습니다. 이러한 구성 변경은 Office Communications Server 2007 R2에서 수행 해야 합니다. 마이그레이션하기 전에 이러한 단계를 수행 하는 것이 매우 중요 합니다. 자세한 내용은 [Lync Server 2013의 클라이언트 및 장치 계획](lync-server-2013-planning-for-clients-and-devices.md)을 참조 하세요.

<div>

## <a name="to-configure-clients-prior-to-migration"></a>마이그레이션하기 전에 클라이언트를 구성 하려면

1.  가장 최근의 Office Communications Server 2007 R2 서버, 클라이언트 및 장치 업데이트 (핫픽스)를 배포 합니다.
    
      - [Office Communications Server 2007 R2 업데이트 적용](apply-office-communications-server-2007-r2-updates.md)
    
      - [Communicator 2007 R2의 누적 업데이트 패키지에 대 한 설명](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [장치 소프트웨어 업데이트 구하기](http://go.microsoft.com/fwlink/?linkid=335809)

2.  Office Communications Server 2007 R2에서 클라이언트 버전 필터링을 사용 하 여 로그인 하는 데 설치 된 최신 업데이트를 사용 하는 Office Communications Server 2007 R2 클라이언트만 허용 합니다.

3.  Office Communications Server 2007 R2에서 클라이언트 버전 필터링을 사용 하 여 Lync Server 2013 클라이언트가 로그인 하지 못하도록 차단 합니다. 다음 표에 나열 된 버전 필터 [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) 를 추가 하기 위해 **클라이언트 버전 필터링 구성** 에 설명 된 단계를 따릅니다. 각 버전 필터에 대해 작업 **블록**을 할당 합니다.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>클라이언트</th>
    <th>사용자 에이전트 헤더</th>
    <th>버전</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15 ...** *</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5 ...** *</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4 ...** *</p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

