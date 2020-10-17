---
title: 'Lync Server 2013: 지원 되는 클라이언트 버전 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cecc551eef4cb7574674c9f7de39f27b4efc8710
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517395"
---
# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Lync Server 2013에서 지원 되는 클라이언트 버전 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-12-14_

Lync Server 2013에서는 클라이언트 버전 정책을 설정 하 여 해당 환경에서 지원 되는 클라이언트 버전을 지정할 수 있습니다. 또한 전역 클라이언트 버전 구성을 사용 하 여 아직 버전 정책이 정의 되지 않은 클라이언트에 대 한 기본 작업을 지정할 수 있으며, 따라서 명시적으로 지원 또는 제한 되지 않습니다.

클라이언트 버전 정책을 사용 하 여 클라이언트 업데이트를 관리할 수도 있습니다. 클라이언트 버전 정책을 설정 하 고 **허용 및 업그레이드** 및 **차단 및 업그레이드**옵션을 사용 하는 경우 클라이언트는 Windows Server 업데이트 서비스 (이 서비스를 사용 하는 경우) 또는 Microsoft Update에서 업데이트 된 소프트웨어를 수신 합니다.

<div>

## <a name="client-version-policy-settings"></a>클라이언트 버전 정책 설정

기본 클라이언트 버전 정책을 사용 하려면 모든 클라이언트가 Lync를 실행 해야 합니다. 환경의 클라이언트에서 이전 버전의 Communicator를 실행 하는 경우에는 Lync Server 2013에 연결할 때 클라이언트 및 장치가 예기치 않게 차단 되거나 업데이트 되지 않도록 클라이언트 버전 규칙을 다시 구성 해야 할 수 있습니다. 기본 규칙을 수정하거나 클라이언트 버전 정책 목록에 상위 규칙을 추가하여 기본 규칙을 재정의할 수 있습니다. 또한 CU(누적 업데이트)가 출시된 경우 최신 업데이트를 요구하도록 클라이언트 버전 정책을 구성해야 합니다. 자세한 내용은 작업 설명서에서 [Lync Server 2013에 로그온 하는 데 사용할 수 있는 클라이언트 응용 프로그램 지정](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) 을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

