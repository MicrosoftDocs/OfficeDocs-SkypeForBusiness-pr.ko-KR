---
title: 'Lync Server 2013: 위치 얻기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e54c7032973f75922f6c6893a0c758409ec945be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>Lync Server 2013에서 위치 얻기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-06_

Lync Server 2013 E9-1-1 배포에서 내부적으로 연결 된 각 Lync 또는 Lync Phone Edition 클라이언트는 자신의 위치를 적극적으로 가져옵니다. SIP 등록 후 클라이언트는 복제 된 SQL Server 데이터베이스에 의해 지원 되는 웹 서비스인 위치 정보 서비스에 대 한 위치 요청에 대해 자신에 대해 알고 있는 모든 네트워크 연결 정보를 furnishes 합니다. 각 중앙 사이트 풀에는 네트워크 정보를 사용 하 여 해당 위치에 대 한 레코드를 쿼리 하는 위치 정보 서비스가 있습니다. 일치 하는 항목이 있는 경우 위치 정보 서비스에서 클라이언트에 대 한 위치를 반환 합니다. 일치 하는 항목이 없을 경우 위치 정책 설정에 따라 위치를 수동으로 입력 하 라는 메시지가 표시 될 수 있습니다. 위치 데이터는 현재 상태 정보 데이터 서식 위치 개체 (PIDF-낮음) 라는 표준화 된 XML 형식으로 클라이언트에 다시 전송 됩니다.

Lync Server 클라이언트는 비상 전화의 일부로 PIDF-낮음 데이터를 포함 하며,이 데이터는 E9 서비스 공급자가 해당 PSAP를 확인 하 고 해당 PSAP에 대 한 통화를 올바른 ESQK로 라우팅합니다 .이는 PSAP 디스패처가 다음을 얻을 수 있도록 합니다. 발신자의 위치.

다음 다이어그램에서는 타사 클라이언트 MAC 주소 기반 위치 메서드를 제외 하 고 Lync Server 클라이언트가 위치를 가져오는 방법을 보여 줍니다.

![클라이언트가 위치를 가져오는 방법 다이어그램](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "클라이언트가 위치를 가져오는 방법 다이어그램")

클라이언트가 위치를 가져오려면 다음 단계를 수행 해야 합니다.

1.  관리자가 네트워크 wiremap 매핑 (다양 한 유형의 네트워크 주소를 해당 비상 응답 위치 (ERLs)에 매핑하는 테이블)로 위치 정보 서비스 데이터베이스를 채웁니다.

2.  SIP 트렁크 E9-1-1 서비스 공급자를 사용 하는 경우 관리자는 E9-1-1 서비스 공급자가 유지 관리 하는 MSAG (마스터 주소 가이드) 데이터베이스에 대해 ERLs의 도심 주소 부분에 대해 유효성을 검사 합니다. 게이트웨이에서 ELIN 사용 하는 경우 관리자는 PSTN 캐리어가 자동 위치 확인 (ALI) 데이터베이스에 ELIN을 업로드 하는지 확인 합니다.

3.  등록 하는 동안 또는 네트워크 변경이 발생할 때마다 내부적으로 연결 된 클라이언트가 위치 정보 서비스에 대 한 클라이언트의 검색 된 네트워크 주소를 포함 하는 위치 요청을 보냅니다.

4.  위치 정보 서비스는 위치에 대 한 게시 된 레코드를 쿼리하고, 일치 하는 항목이 있는 경우 ERL를 PIDF-낮음 형식으로 클라이언트에 반환 합니다.

</div>

<span> </span>

</div>

</div>

</div>

