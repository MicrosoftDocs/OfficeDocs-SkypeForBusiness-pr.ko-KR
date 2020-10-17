---
title: BackCompatSite 제거
description: BackCompatSite을 제거 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809324320ec1869ac0c9d324b8fc270a3cf8f174
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570274"
---
# <a name="remove-backcompatsite"></a>BackCompatSite 제거

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

모든 풀이 비활성화되고 모든 에지 서버가 제거된 후 토폴로지 작성기 병합 마법사를 실행하여 **BackCompatSite**를 제거합니다.

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>토폴로지 작성기에서 BackCompat 사이트를 제거하려면

1.  토폴로지 작성기에서 기존 배포를 엽니다.

2.  **동작** 메뉴에서 **2007 R2 토폴로지 병합**을 클릭합니다.

3.  계속하려면 **다음**을 클릭합니다.

4.  **레거시 에지 지정** 페이지에서 에지 서버의 목록이 비어 있는지 확인합니다. 목록이 비어 있지 않으면 **제거** 단추를 사용하여 모든 레거시 에지 서버를 제거한 후 **다음**을 클릭합니다.
    
    ![토폴로지 병합 마법사,에 지 설정 지정 페이지](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "토폴로지 병합 마법사,에 지 설정 지정 페이지")  

5.  **내부 SIP 포트 설정 지정** 페이지에서 **다음**을 클릭합니다.

6.  **요약** 페이지에서 **다음** 을 클릭 하 여 토폴로지 병합을 시작 하 고 레거시 사이트를 제거 합니다.

7.  **상태** 열에서 값이 **성공**인지 확인한 다음 **마침**을 클릭하여 마법사를 닫습니다.

8.  토폴로지 작성기의 왼쪽 창에서 BackCompatSite를 확장하고 나열된 서버가 없는지 확인합니다.

9.  **BackCompatSite**를 마우스 오른쪽 단추로 클릭한 다음 **삭제**를 클릭합니다.

10. **토폴로지 작성기**에서 맨 위에 있는 **Lync Server** 노드를 선택합니다.

11. **동작** 메뉴에서 **토폴로지 게시**를 선택한 후 **다음**을 클릭합니다.

12. **게시 마법사**가 완료되면 **마침**을 클릭하여 마법사를 닫습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

