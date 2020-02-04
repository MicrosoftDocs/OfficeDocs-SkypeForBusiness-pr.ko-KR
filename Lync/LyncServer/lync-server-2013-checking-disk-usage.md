---
title: 'Lync Server 2013: 디스크 사용량 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 554b493ba7ca837a8ea5c80f6751ddb91061c374
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a>Lync Server 2013에서 디스크 사용 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-04-30_

하드 디스크 드라이브는 Lync Server 2013 배포의 중요 한 구성 요소입니다. 사용 가능한 디스크 볼륨이 충분 하지 않은 경우에도 운영 체제와 Lync Server 2013 데이터베이스가 제대로 작동 하지 않을 수 있습니다. 서버에서 디스크 공간이 부족 한지 확인 하 고 필요에 따라 저장소 리소스를 추가 하기 위해 준비 하는 데 도움이 되도록 Lync Server 2013 백 엔드 데이터베이스 통계를 매일 모니터링 해야 합니다.

운영 체제, 프로그램 파일, 데이터베이스, 트랜잭션 로그 (Lync Server 2013 백 엔드)를 호스팅하는 디스크 공간을 검사 하는 것 외에도 다음과 같은 중요 한 파일 공유에 대 한 디스크 공간을 포함 하는 파일 시스템의 사용을 모니터링 해야 합니다. 데이터

  - 모임 콘텐츠

  - 모임 콘텐츠 메타 데이터

  - 모임 준수 로그

  - 응용 프로그램 데이터 파일 (응용 프로그램 서버 구성 요소에서 내부적으로 사용 됨)

  - 그룹 채팅 서버 웹 서비스 및 준수 폴더 (그룹 채팅 웹 서비스에 업로드 한 파일을 저장 하는 경우)

  - 그룹 채팅 준수 XML 파일 (그룹 채팅 준수 레코드가 포함 되어 있는 경우)

  - 파일 업데이트 (장치 업데이트 서비스의 경우)

  - 주소록 파일

Lync Server 2013에는 이전에 나열 된 파일 공유에 있는 파일을 비롯 하 여 데이터베이스와 트랜잭션 로그를 저장 하는 데 하드 디스크 공간이 필요 합니다.

저장소 리소스가 부족 하 여 Lync Server 2013 배포가 부정적인 영향을 받지 않도록 하기 위해 정기적으로 디스크 공간을 모니터링 해야 합니다.

각 Lync Server 2013 볼륨의 사용 가능한 디스크 공간 및 데이터베이스와 트랜잭션 로그 파일의 예상 증가량에 대 한 통계 정보를 비교 하 고 유지 관리 합니다. 이는 저장소 리소스가 필요할 때 용량 계획을 수립 하 고 저장소를 추가 하는 데 도움이 됩니다.

문제 해결 및 재해 복구 상황을 수용 하기 위해 사용 가능한 빈 볼륨 공간을 데이터베이스 크기의 110% 이상으로 하는 것이 좋습니다.

다음 방법을 사용 하 여 사용 가능한 디스크 공간을 확인할 수 있습니다.

1.  **System center operations manager**   system center operations manager를 사용 하 여 볼륨 공간이 제한 된 경우 관리자에 게 경고를 표시할 수 있습니다.

2.  ****   사용 가능한 하드 디스크 공간이 20% 미만이 되 면 메시지를 보내는 스크립트를 실행 하 여 스크립트를 실행 하 여 디스크 공간을 모니터링 합니다. TechNet의 Microsoft 스크립트 센터에서 예제 스크립트를 찾으려면 다음을 확인 하세요.[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **Windows 탐색기**   는 windows 탐색기를 사용 하 여 Lync Server 2013 로그 및 데이터베이스를 저장 하는 볼륨의 디스크 공간을 확인 합니다.

</div>

<span> </span>

</div>

</div>

</div>

