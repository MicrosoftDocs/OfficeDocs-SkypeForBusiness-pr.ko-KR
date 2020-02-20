---
title: 'Lync Server 2013: A/V (오디오/비디오)에 지 서버'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62f31721b21e8738dcd57dfb203d7fd306c38c94
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Lync Server 2013의 A/V (오디오/비디오)에 지 서버

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

A/V 에지 서비스는 내부 사용자(조직 단위 네트워크에 로그온된 사용자)가 외부 사용자(조직 단위 네트워크에 로그온되지 않은 사용자)와 오디오 및 비디오를 공유할 수 있는 방법을 제공합니다. A/V에 지 서비스는 오디오 및 비디오 외에도 데스크톱 공유 및 파일 전송에 대 한 지원도 제공 합니다.

A/V에 지 서비스는 기본적으로 A/V에 지 구성을 사용 하 여 관리 됩니다. 이러한 설정을 사용 하 여 포트 당 할당할 최대 대역폭 크기와 사용자 단위를 관리할 수 있으며, 해당 토큰이 갱신 되기 전에 인증 토큰을 사용할 수 있는 기간을 지정할 수 있습니다. A/V에 지 구성 설정을 사이트 또는 개별 A/V에 지 서버에 적용할 수 있습니다. 우선 순위를 지정할 설정 컬렉션을 결정할 때는 다음 가이드를 사용 합니다.

  - 서비스 범위로(즉, 개별 서버에서) 구성된 설정은 다른 모든 것들보다 우선 적용됩니다.

  - 사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 합니다. 그러나 서비스 범위 설정도 사이트 범위 설정으로 대체 됩니다.

  - 전역 범위의 설정은 개별 서버에 구성된 서비스 설정이 없는 경우 그리고 서버가 배치된 위치에 사이트 설정이 없는 경우에만 사용됩니다.

A/V에 지 서비스는 Lync Server PowerShell 및 Get-csavedgeconfiguration cmdlet을 사용 해야만 관리할 수 있습니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 A/V에 지 서버 구성 정보 반환](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Lync Server 2013에서 A/V에 지 서버 구성 설정 모음 만들기 또는 수정](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Lync Server 2013에서 A/V에 지 서버 구성 설정의 기존 컬렉션 삭제](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

