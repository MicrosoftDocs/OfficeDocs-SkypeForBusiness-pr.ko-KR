---
title: 'Lync Server 2013: 원격 통화 제어 및 전화 번호 정규화'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76d7ffb386f6b565fc00b866072bfab6390bc8d9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Lync Server 2013의 원격 통화 제어 및 전화 번호 정규화

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-22_

Lync 클라이언트는 ABS (주소록 서비스) 파일 다운로드의 일부로 전화 번호 정규화 규칙을 다운로드 합니다. 원격 통화 제어 시나리오에서 주소록 서비스 전화 번호 정규화 규칙은 수신 및 발신 원격 통화 제어 통화에 모두 적용됩니다. 원격 통화 제어를 사용하도록 설정한 사용자에 대한 수신 전화의 경우에는 먼저 발신자의 전화 번호가 SIP/CSTA 게이트웨이 또는 PBX(Private Branch Exchange)를 통해 E.164 형식으로 정규화됩니다. Lync Server 2013이 게이트웨이에서 전화를 받으면 발신자의 전화 번호에 대해 수신자의 Microsoft Office Outlook 대화 상대 목록 또는 GAL (전체 주소 목록)에 저장 된 정규화 된 번호에 대해 RNL (역방향 번호 조회)를 수행 합니다. 주소록 서비스 역방향 번호 조회에서 일치하는 항목이 검색되면 발신자가 수신 전화 알림에 이름으로 표시됩니다.

나가는 원격 통화 제어 통화의 경우 Lync는 통화를 SIP/CSTA 게이트웨이로 라우팅하기 전에 전화 건 번호에 주소록 서비스 전화 번호 정규화 규칙을 적용 합니다.

원격 통화 제어에 대 한 전화 번호 정규화 규칙을 만드는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 다이얼 플랜 및 정규화 규칙](lync-server-2013-dial-plans-and-normalization-rules.md) 을 참조 하십시오.

<div>

## <a name="migrating-phone-number-normalization-rules"></a>전화 번호 정규화 규칙 마이그레이션

이전에 원격 통화 제어를 사용하도록 설정한 사용자를 마이그레이션하는 경우 마이그레이션 설명서에서 다음 항목을 참조하십시오.

  - Lync Server 2010에 대 한 자세한 내용은 마이그레이션 설명서에서 주소록 [주소록](migrate-address-book.md) 마이그레이션을 참조 하십시오.

  - Communications Server 2007 r 2에 대 한 내용은 마이그레이션 설명서에서 주소록 [주소록](migrate-address-book_1.md) 마이그레이션을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

