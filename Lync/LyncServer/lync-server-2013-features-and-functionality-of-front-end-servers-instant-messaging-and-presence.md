---
title: 'Lync Server 2013: 프런트 엔드 서버, 메신저, 현재 상태의 기능'
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
ms.openlocfilehash: 4a76dfed553e85838739c7c348e5bc53fc9943a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 서버, 메신저, 현재 상태의 기능

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-17_

프런트 엔드 서버는 대부분의 Lync Server 기능을 제공 합니다. 두 가지 버전의 Lync Server Enterprise Edition (대규모 조직에 대해 기본적으로 디자인 되어 있음)과 Lync Server Standard Edition (기본적으로 소규모 조직에서 하드웨어 investement 하 고 사용 하지 않음)이 필요 합니다. 고가용성이 필요 합니다. 두 에디션 모두 메신저, 현재 상태, 회의, 엔터프라이즈 보이스 등의 모든 Lync Server 작업을 지원 합니다.

인스턴트 메시지 (IM)를 사용 하면 사용자가 텍스트 기반 메시지를 사용 하 여 컴퓨터에서 실시간으로 서로 통신할 수 있습니다. 2-파티 및 단체 IM 세션이 모두 지원 됩니다. 타사 메신저 대화의 참가자는 언제 든 지 대화에 세 번째 참가자를 추가할 수 있습니다. 이런 경우 대화 창이 회의 기능을 지원 하도록 변경 됩니다.

<div>


> [!IMPORTANT]
> 1 ~ 1 통신에 참가 하는 Lync 및 Communicator 클라이언트는 종종 피어 투 피어 라고 합니다. 기술적으로 두 클라이언트는 중앙의 IMMCU (지점 제어 단위)를 사용 하 여 일대일 대화로 통신 합니다. IMMCU는 프런트 엔드 서버의 구성 요소입니다. 필요한 통신 워크플로에 IMMCU를 배치 하면 프런트 엔드 서버에서 사용할 수 있는 통화 정보 기록 및 기타 기능을 사용할 수 있습니다. 클라이언트의 동적 원본 포트에서 프런트 엔드 서버 포트 TLS/TCP/5061으로 통신 하는 것으로 간주 됩니다 (권장 전송 계층 보안을 사용 하는 경우). Lync Server와 IMMCU가 활성 상태이 고 사용할 수 있는 경우에만 피어 투 피어 통신 및 여러 파티 IM을 디자인할 수 있습니다.



</div>

*현재* 상태는 네트워크의 다른 사용자에 대 한 정보를 제공 합니다. 사용자의 현재 상태는 다른 사람이 사용자에 게 연락 여부, 인스턴트 메시지, 전화 또는 전자 메일을 사용할지 여부를 결정 하는 데 도움이 되는 정보를 제공 합니다. 현재 상태는 즉각적인 의사 소통을 가능 하 게 하는 반면, 사용자가 인스턴트 통신을 할 수 없음을 나타내는 office 모임 인지 또는 부재 중인지에 대 한 정보를 제공 합니다. 이 현재 상태는 Microsoft Outlook 메시지 및 공동 작업 클라이언트, Microsoft SharePoint 기술, Microsoft Word, Microsoft Excel 스프레드시트를 포함 하 여 Lync 및 기타 현재 상태 인식 응용 프로그램에 현재 상태 아이콘으로 표시 됩니다. 소프트웨어. 현재 상태 아이콘은 사용자의 현재 상태 및 통신 하는 willingness를 나타냅니다.

</div>

<span> </span>

</div>

</div>

</div>

