---
title: 'Lync Server 2013: 지정 하지 않은 전화 번호 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02dd4f71b3bc9d53fcbd65f4e143fec550c6a528
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a>Lync Server 2013에서 할당 되지 않은 전화 번호 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

Lync Server를 사용 하 여 조직에 유효 하지만 사용자 또는 휴대폰에 할당 되지 않은 전화 번호로 들어오는 호출에 대 한 발생을 구성할 수 있습니다. 이러한 호출 처리를 구성 하려면 지정 하지 않은 번호 표를 설정 합니다. 표를 사용 하 여 알림 응용 프로그램이 나 Exchange UM 서버로 전화를 라우팅할 수 있습니다.

할당되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다. 조직에 대해 유효한 모든 내선 번호로 또는 할당되지 않은 내선 번호만으로 또는 두 번호 유형의 결합으로 테이블을 구성할 수 있습니다. 할당되지 않은 번호 테이블은 할당된 번호와 할당되지 않은 번호를 모두 포함할 수 있지만 발신자가 현재 할당되지 않은 번호로 전화를 걸 때만 호출됩니다. 할당되지 않은 번호 테이블에 유효한 내선 번호를 모두 포함하면 테이블을 재구성하지 않고도 다른 사용자가 조직을 떠날 때마다 발생하는 동작을 지정할 수 있습니다. 테이블에 할당되지 않은 내선 번호를 포함하면 특정 번호에 대해 발생하는 동작을 조정할 수 있습니다. 예를 들어 고객 서비스 센터의 내선 번호를 변경하려면 테이블에 기존의 고객 서비스 센터 번호를 포함하고 새 번호를 제공하는 알림에 이 번호를 할당하면 됩니다.

<div>


> [!IMPORTANT]  
> 지정 하지 않은 번호 테이블을 구성 하기 전에 이미 하나 이상의 공지 사항이 정의 되어 있거나 Exchange UM 자동 전화 교환이 설정 되어 있어야 합니다. 공지 사항 만들기에 대 한 자세한 내용은 <A href="lync-server-2013-create-an-announcement.md">Lync Server 2013에서 공지 만들기</A>를 참조 하세요. Exchange UM 설정을 구성 했는지 확인 하려면 <STRONG>Get-C고 Umcontact</STRONG> cmdlet을 실행 합니다. 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">get-help (Get-c)</A>을 참조 하세요.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 할당 되지 않은 숫자 범위 만들기 또는 수정](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Lync Server 2013에서 할당 되지 않은 번호 범위 삭제](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

