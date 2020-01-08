---
title: BackCompatSite 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6a3d1dc92e45bc99892e7827394376b6f28b12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>BackCompatSite 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

모든 풀을 비활성화 하 고 모든 Edge 서버를 제거한 후에는 토폴로지 작성기 병합 마법사를 실행 하 여 **BackCompatSite**를 제거 합니다.

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>토폴로지 작성기에서 백 호환성 사이트를 제거 하려면

1.  토폴로지 작성기에서 기존 배포를 엽니다.

2.  **작업** 메뉴에서 **2007 R2 토폴로지 병합**을 클릭 합니다.

3.  계속하려면 **다음**을 클릭합니다.

4.  **레거시 Edge 지정** 페이지에서 Edge 서버 목록이 비어 있는지 확인 합니다. 목록이 비어 있지 않으면 **제거** 단추를 사용 하 여 모든 레거시 Edge 서버를 제거 하 고 **다음**을 클릭 합니다.
    
    ![토폴로지 병합 마법사, Edge 설정 페이지](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "병합 마법사 지정, Edge 설정 페이지로 지정")  

5.  **내부 SIP 포트 설정 지정** 페이지에서 **다음**을 클릭 합니다.

6.  **요약** 페이지에서 **다음** 을 클릭 하 여 기존 사이트 제거를 위해 토폴로지 병합을 시작 합니다.

7.  **상태** 열에서 값이 **성공적** 인지 확인 한 다음 **마침을** 클릭 하 여 마법사를 닫습니다.

8.  토폴로지 작성기의 왼쪽 창에서 BackCompatSite를 확장 하 고 서버가 나열 되지 않도록 합니다.

9.  **BackCompatSite**를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.

10. **토폴로지 작성기**에서 최상위 노드 **Lync 서버**를 선택 합니다.

11. **작업** 메뉴에서 **토폴로지 게시** 를 선택 하 고 **다음**을 클릭 합니다.

12. **게시 마법사** 가 완료 되 면 **마침을** 클릭 하 여 마법사를 닫습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

