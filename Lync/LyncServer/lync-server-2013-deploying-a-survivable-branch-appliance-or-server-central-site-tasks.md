---
title: SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 배포 - 중앙 사이트 작업
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9aa6d38ec873652feae6ef6a374ee5b771520b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Lync Server 2013을 통해 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 배포 - 중앙 사이트 작업

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

중앙 사이트에서이 섹션의 작업을 완료 합니다. Survivable Branch 서버를 배포 하는 경우 첫 번째 작업을 건너뜁니다.

<div>


> [!IMPORTANT]
> 이 섹션의 작업을 수행 하기 전에 다음 조건이 충족 되어야 합니다. 
> <UL>
> <LI>
> <P>중앙 사이트에서 Lync Server를 설정 해야 합니다.</P>
> <LI>
> <P>지점 사이트의 설치 기술자를 RTCUniversalSBATechnicians 그룹에 추가 해야 합니다.</P></LI></UL>또한 다음을 수행 하는 것이 좋습니다.
> <UL>
> <LI>
> <P>각 지점 사이트에 DHCP 서버를 배포 하 여 클라이언트가 IP 주소를 얻을 수 있도록 합니다.</P>
> <LI>
> <P>각 지점 사이트에서 DHCP 서버를 배포 하는 대신 Survivable Branch 기기 또는 Survivable Branch 서버에서 lync server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration – EnableDHCPServer $true</STRONG>를 사용 하 여이 서버를 사용할 수 있도록 설정 합니다. 자세한 내용은 계획 설명서의 <A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013의 지점 사이트 복원 요구 사항에 대 한</A> "하드웨어 및 소프트웨어 요구 사항" 섹션을 참조 하세요.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 Active Directory에 SBA(Survivable Branch Appliance) 추가](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Lync Server 2013에서 토폴로지에 분기 사이트 추가](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Lync Server 2013에서 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 정의](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

