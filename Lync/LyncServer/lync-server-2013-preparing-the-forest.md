---
title: 'Lync Server 2013: 포리스트 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9ab1ea2180c8fa4ba4f40cbf621816fe41ea7f9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>Lync Server 2013에 대 한 포리스트 준비

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

포리스트 준비에서는 Lync Server 2013에서 사용 하기 위한 Active Directory 전역 설정 및 개체 및 Active Directory 유니버설 그룹을 만들고 Active directory 개체에 대 한 적절 한 액세스 권한을 부여 합니다. 포리스트 준비에서 만드는 유니버설 그룹 및 전역 설정 및 개체에 대 한 설명은 [Lync Server 2013에서 포리스트 준비로 인 한 변경 사항](lync-server-2013-changes-made-by-forest-preparation.md)을 참조 하십시오.

또한 포리스트 준비에서는 Lync Server 2013에서 사용 되는 속성 집합 및 표시 지정자를 포함 하는 개체를 만들고 구성 컨테이너에 저장 합니다.

<div>


> [!IMPORTANT]  
> 포리스트 준비 절차를 수행 하기 전에 스키마 준비 변경 내용이 모든 도메인 컨트롤러에 복제 되었는지 확인 합니다. 복제가 완료되지 않은 경우 오류가 발생합니다.



</div>

새 Lync Server 배포를 수행 하는 경우에는 구성 컨테이너에 전역 설정을 저장 해야 합니다. 이전 버전에서 업그레이드 하는 동안 여전히 System 컨테이너에 전역 설정을 저장 하는 경우에는 System 컨테이너를 계속 사용할 수 있습니다.

이 절차를 수행하려면 포리스트 루트 도메인의 Enterprise Admins 또는 Domain Admins 그룹 구성원이어야 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에 대 한 포리스트 준비 실행](lync-server-2013-running-forest-preparation.md)

  - [Cmdlet을 사용 하 여 Lync Server 2013에 대 한 포리스트 준비 되돌리기](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

