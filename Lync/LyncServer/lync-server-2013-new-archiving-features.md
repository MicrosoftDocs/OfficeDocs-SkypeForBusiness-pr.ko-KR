---
title: 'Lync Server 2013: 새로운 보관 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d736e823892aa6d6edcc5ab90df900a5c6b7ac79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Lync Server 2013의 새로운 보관 기능

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-09_

Lync Server 2013 보관에는 다음 유형의 콘텐츠를 보관할 수 있습니다.

  - 피어 투 피어 인스턴트 메시지

  - 여러 사람이 있는 인스턴트 메시지 회의 (모임)

  - 업로드 된 콘텐츠 (예: 유인물) 및 이벤트 관련 콘텐츠 (예: 참가, 종료, 공유 업로드, 표시 유형 변경)를 포함 한 컨퍼런스 콘텐츠

또한 Lync Server 2013에서 보관 하면 배포 및 작업 효율성을 향상 시키는 새로운 기능을 제공 합니다. 이러한 새 기능은 다음과 같이 구성 됩니다.

  - **프런트 엔드 서버에서 보관 하는 위치입니다.**    Lync server 2013에 별도의 보관 서버 역할이 없습니다. 보관은 Enterprise Edition 배포의 모든 프런트 엔드 서버와 풀 또는 사이트에 대해 구성할 수 있는 표준 버전 서버에서 사용할 수 있는 선택적 기능입니다.

  - **Microsoft Exchange 통합.**    보관을 배포 하는 경우 exchange 2013에 속한 모든 사용자의 기존 exchange 2013 저장소에 데이터 저장소를 통합 하 고 해당 사서함이 원본 위치 유지에 배치 되도록 하면 별도의 SQL Server 데이터베이스를 배포 하 여 Lync 데이터를 보관할 필요가 없습니다. Exchange 2013 배포를 사용 하지 않거나 해당 사서함과 통합 하지 않으려는 경우 또는 Exchange 2013에 포함 되지 않은 Lync 2013 사용자가 현재 위치 유지를 사용 하 고 있는 경우에는 SQL Server에 stor를 사용 하 여 별도의 보관 데이터베이스를 배포할 수 있습니다. 전자 Lync 통신에서 데이터를 보관 합니다. 배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하려는 경우 Microsoft exchange 통합 및 Lync Server 2013 보관 데이터베이스를 모두 사용할 수 있습니다. 원본 위치 유지에 대 한 자세한 내용은에서 "원본 위치 유지"를 참조 [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)하세요.

  - **SQL Store 미러링.**    보관을 배포할 때 보관 데이터베이스에 대해 SQL Server 데이터베이스 미러링을 사용 하도록 설정할 수 있습니다.

  - **화이트 보드 및 설문을 보관 합니다.**    이제 보관 된 회의 콘텐츠에는 모임 중에 공유 되는 화이트 보드 및 설문에 대 한 정보가 포함 됩니다.

다음과 같은 유형의 콘텐츠는 보관 되지 않습니다.

  - 피어 투 피어 파일 전송

  - 피어 투 피어 인스턴트 메시지 및 회의를 위한 오디오/비디오

  - 피어 투 피어 인스턴트 메시지 및 회의를 위한 응용 프로그램 공유

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 보관 계획](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

