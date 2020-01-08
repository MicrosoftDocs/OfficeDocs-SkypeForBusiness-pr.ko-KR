---
title: 'Lync Server 2013: 오디오/비디오 (A/V) Edge 서버'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9738dbb11ce731ac832a5529d2013f3f9b2907
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Lync Server 2013의 오디오/비디오 (A/V) Edge 서버

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

A/V Edge 서비스는 내부 사용자 (조직의 네트워크에 로그온 한 사용자)가 외부 사용자 (조직의 네트워크에 로그인 하지 않은 사용자)와 오디오 및 비디오를 공유 하는 방법을 제공 합니다. A/V Edge 서비스는 오디오 및 비디오 외에도 데스크톱 공유 및 파일 전송에 대 한 지원도 제공 합니다.

A/V Edge 서비스는 주로 A/V Edge 구성을 사용 하 여 관리 됩니다. 이러한 설정을 사용 하 여 포트당 사용자 당 할당할 최대 대역폭을 관리 하 고 해당 토큰을 갱신 하기 전에 인증 토큰을 사용할 수 있는 시간을 지정 합니다. A/V Edge 구성 설정을 사이트 또는 개별 A/V Edge 서버에 적용할 수 있습니다. 어떤 설정 모음에 우선 순위를 둘지를 결정 하는 경우 다음 가이드를 사용 합니다.

  - 서비스 범위 (즉, 개별 서버)에 구성 된 설정은 모두에 게 우선 합니다.

  - 사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 합니다. 그러나 서비스 범위 설정 에서도 사이트 범위 설정이 대체 됩니다.

  - 전역 범위의 설정은 개별 서버에 구성 된 서비스 설정이 없고 해당 서버가 있는 사이트에 대 한 사이트 설정이 없는 경우에만 사용 됩니다.

A/V Edge 서비스는 Lync Server PowerShell 및 CsAVEdgeConfiguration cmdlet을 사용 하는 경우에만 관리할 수 있습니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 A/V Edge 서버 구성 정보 반환](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Lync Server 2013에서 A/V Edge 서버 구성 설정 모음 만들기 또는 수정](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Lync Server 2013에서 A/V Edge 서버 구성 설정의 기존 컬렉션 삭제](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

