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
ms.openlocfilehash: 8a485ba2a406fd762d70ba4e8ff621d2d6af3801
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>Lync Server 2013에 대한 포리스트 준비

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

포리스트 준비는 Lync Server 2013에서 사용할 Active Directory 전역 설정 및 개체 및 Active Directory 유니버설 그룹을 만들며 Active Directory 개체에 대 한 적절 한 액세스 권한을 부여 합니다. 포리스트 준비로 만든 유니버설 그룹과 전역 설정 및 개체에 대 한 설명은 [Lync Server 2013의 포리스트 준비에서 변경한 내용을](lync-server-2013-changes-made-by-forest-preparation.md)참조 하세요.

또한 포리스트 준비는 Lync Server 2013에서 사용 되는 속성 집합 및 표시 지정자를 포함 하는 개체를 만들고 구성 컨테이너에 저장 합니다.

<div>


> [!IMPORTANT]  
> 포리스트 준비 절차를 수행 하기 전에 스키마 준비 변경 내용이 모든 도메인 컨트롤러로 복제 되었는지 확인 합니다. 복제가 완료 되지 않은 경우 오류가 발생 합니다.



</div>

새 Lync Server 배포를 수행 하는 경우 구성 컨테이너에 전역 설정을 저장 해야 합니다. 이전 버전에서 업그레이드 하는 경우 여전히 시스템 컨테이너에 전역 설정을 저장 하는 경우 시스템 컨테이너를 계속 사용할 수 있습니다.

이 절차를 수행 하려면 포리스트 루트 도메인의 엔터프라이즈 관리자 또는 Domain Admins 그룹의 구성원 이어야 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에 대한 포리스트 준비 실행](lync-server-2013-running-forest-preparation.md)

  - [Lync Server 2013에 대해 Cmdlet을 사용하여 포리스트 준비 되돌리기](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

