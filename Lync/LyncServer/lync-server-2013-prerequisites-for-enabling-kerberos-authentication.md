---
title: 'Lync Server 2013: Kerberos 인증을 사용 하기 위한 필수 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0be98112431b9e57486bb33e0eab84eada94e50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506785"
---
# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Lync Server 2013에서 Kerberos 인증을 사용 하기 위한 필수 구성 요소

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

Kerberos 인증을 사용 하도록 설정 하기 전에 모든 필수 구성 및 인프라 준비 작업을 완료 해야 합니다.

  - Lync Server 2013에 대 한 Active Directory 스키마가 확장 되었습니다.

  - Lync Server 2013에 대 한 Active Directory 포리스트 준비가 완료 되었습니다.

  - Lync Server 2013에 대 한 Active Directory 도메인 준비가 완료 되었습니다.

  - 중앙 관리 저장소를 성공적으로 설치 하 고 사용할 수 있습니다.

  - 토폴로지 작성기를 사용 하 여 토폴로지를 만들고 게시 했습니다.

  - 프런트 엔드 서버, Standard Edition 서버 및 디렉터를 비롯 하 여 웹 서비스를 필요로 하는 서버와 역할이 정의 되 고 배포 되었습니다.

  - Lync Server 2013에서 웹 서비스를 지원 하기 위한 권장 역할 서비스를 사용 하 여 IIS (인터넷 정보 서비스)를 구성 하 고 배포 합니다.

필수 구성 요소를 충족 한 후에는 웹 서비스에 대해 하나 이상의 계정을 만들어 배포에 대 한 Kerberos 인증에 사용할 수 있습니다. 최소한 각 배포에 대해 Kerberos 인증 계정 하나를 만들어야 합니다. 그러나 각 사이트에 대해 계정을 만들어 사이트에서 로컬 Kerberos 인증을 제공할 수 있습니다. Kerberos 인증 계정은 사이트당 하나만 지정할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

