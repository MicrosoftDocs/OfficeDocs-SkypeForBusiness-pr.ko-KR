---
title: 'Lync Server 2013: 지정되지 않은 번호 테이블 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b99679d439257b54b6bb40d8e724bb63da4a1ea5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>Lync Server 2013에서 지정되지 않은 번호 테이블 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-30_

Lync Server 2013에서 조직에 대해 유효 하지만 사용자 또는 휴대폰에 할당 되지 않은 전화 번호로 들어오는 호출에 대해 수행할 작업을 지정할 수 있습니다. 발신자는 메시지를 듣거나 다른 대상 또는 둘 다에 게 라우팅될 수 있습니다.

할당되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다. 조직에 대해 유효한 모든 내선 번호로 또는 할당되지 않은 내선 번호만으로 또는 두 번호 유형의 결합으로 테이블을 구성할 수 있습니다. 할당되지 않은 번호 테이블은 할당된 번호와 할당되지 않은 번호를 모두 포함할 수 있지만 발신자가 현재 할당되지 않은 번호로 전화를 걸 때만 호출됩니다. 할당되지 않은 번호 테이블에 유효한 내선 번호를 모두 포함하면 테이블을 재구성하지 않고도 다른 사용자가 조직을 떠날 때마다 발생하는 동작을 지정할 수 있습니다. 표에 할당 되지 않은 확장명을 포함 하는 경우 특정 숫자에 대해 발생 하는 동작을 수정할 수 있습니다. 예를 들어 고객 서비스 데스크에 대 한 내선 번호를 변경 하는 경우에는 테이블에 이전의 고객 서비스 번호가 포함 된 다음 새 번호를 제공 하는 공지 사항에 할당할 수 있습니다.

<div>


> [!IMPORTANT]  
> 할당 되지 않은 번호 테이블을 구성 하기 전에 시스템에 이미 공지가 정의 되어 있거나 UM (Exchange 통합 메시징) 자동 전화 교환이 설정 되어 있어야 합니다.



</div>

<div>


> [!TIP]  
> 다른 사용자가 지정 되지 않은 번호를 호출 하는 경우, Lync Server는 지정 되지 않은 번호 표를 위에서 아래로 검색 하 고 첫 번째 일치 범위를 사용 합니다. 따라서 표의 마지막 범위에 대해 마지막 수단으로 수행 하려는 작업을 지정 해야 합니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

Lync [server 2013에서 할당 되지 않은 번호 범위 만들기 또는 수정](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [lync server 2013에서 알림 만들기](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

