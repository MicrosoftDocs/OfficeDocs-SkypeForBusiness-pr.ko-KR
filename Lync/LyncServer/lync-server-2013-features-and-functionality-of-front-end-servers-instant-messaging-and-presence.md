---
title: 'Lync Server 2013: 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 기능 및 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8e25a74dcffe76f16b12a8c80f8ad8f980370dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 기능 및 기능

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-17_

프런트 엔드 서버는 대부분의 Lync Server 기능을 제공 합니다. 두 가지 버전, 즉 대규모 조직에 주로 디자인 되는 Lync Server Enterprise Edition과, 가장 작은 규모의 하드웨어를 investement 하는 소규모 조직에 주로 디자인 된 Lync server Standard Edition을 사용할 수 있습니다. 고가용성을 사용 해야 합니다. 두 버전 모두 IM, 현재 상태, 회의 및 Enterprise Voice를 비롯 한 모든 Lync Server 작업을 지원 합니다.

IM(인스턴트 메시징)은 사용자가 텍스트 기반 메시지를 사용하여 컴퓨터에서 실시간으로 다른 사용자와 통신할 수 있도록 합니다. 양방향 및 단체 IM 세션이 모두 지원됩니다. 양방향 IM 대화의 참가자는 언제든지 대화에 세 번째 참가자를 추가할 수 있습니다. 이 경우 대화 창이 회의 기능을 지원하도록 변경됩니다.

<div>


> [!IMPORTANT]
> Lync 및 Communicator 클라이언트는 일대일 통신에 관여 하는 경우 피어-투-피어 라고 합니다. 기술적으로 두 클라이언트는 중앙에 있는 IMMCU (인스턴트 메시징 multipoint control unit)를 사용 하 여 일대일 대화로 통신 합니다. IMMCU는 프런트 엔드 서버의 구성 요소입니다. 필요한 통신 워크플로에 IMMCU를 배치 하면 프런트 엔드 서버에서 사용 하는 통화 정보 기록 및 기타 기능을 사용할 수 있습니다. 클라이언트의 동적 원본 포트에서 프런트 엔드 서버 포트 TLS/TCP/5061 (권장 전송 계층 보안을 사용 하는 경우)으로 통신 합니다. Lync Server 및 IMMCU가 활성 상태이 고 사용 가능한 경우에만 피어-투-피어 통신 및 여러 당사자 IM을 기본적으로 사용할 수 있습니다.



</div>

*현재 상태*는 네트워크에 있는 다른 사용자의 상태에 대한 정보를 제공합니다. 사용자의 현재 상태는 다른 사용자가 사용자와 대화를 시도해야 하는지 여부와 인스턴트 메시징, 전화 또는 전자 메일 중 어떤 것을 사용할지 결정하는 데 유용한 정보를 제공합니다. 현재 상태는 가능한 경우 인스턴트 통신을 촉진하는 동시에, 사용자가 회의 중인지 또는 부재 중인지에 대한 정보를 제공하여 인스턴트 통신을 사용할 수 없다는 것도 표시합니다. 이 현재 상태는 Lync 및 기타 현재 상태를 감지 하는 응용 프로그램 (Microsoft Outlook 메시징 및 공동 작업 클라이언트, microsoft SharePoint 기술, Microsoft Word 및 Microsoft Excel 스프레드시트 포함)에 현재 상태가 아이콘으로 표시 됩니다. 소프트웨어로. 현재 상태 아이콘은 사용자의 현재 상태와 통신 가능 여부를 나타냅니다.

</div>

<span> </span>

</div>

</div>

</div>

