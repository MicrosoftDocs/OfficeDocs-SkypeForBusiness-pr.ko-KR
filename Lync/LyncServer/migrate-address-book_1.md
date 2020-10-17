---
title: 주소록 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f0e67dfb8e7902b2d6a0c89c327b13fb00736ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503665"
---
# <a name="migrate-address-book"></a>주소록 마이그레이션

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

**사용자 지정된 주소록 정규화 규칙을 마이그레이션하려면**

1.  \_ \_ \_ \_ 주소록 공유 폴더의 루트에서 회사 전화 번호 정규화Rules.txt 파일을 찾아 Lync Server 2013 파일럿 풀에 있는 주소록 공유 폴더의 루트에 복사 합니다.
    
    <div>
    

    > [!NOTE]  
    > ABS 웹 구성 요소 파일 디렉터리에 샘플 주소록 정규화 규칙이 설치되어 있습니다. 경로는 <STRONG>$설치 드라이브 문자:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>입니다. 이 파일 &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; 을Company_Phone_Number_Normalization_Rules.txt주소록 공유 폴더의 루트 디렉터리에 복사 하 고 이름을 바꿀 수 있습니다. 예를 들어 <STRONG>$serverX</STRONG>에서 공유 되는 주소록의 &nbsp; 경로는 <STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>와 비슷합니다.

    
    </div>

2.  메모장과 같은 텍스트 편집기를 사용 하 여 회사 \_ 전화 \_ 번호 \_ 정규화 \_Rules.txt 파일을 엽니다.

3.  특정 유형의 항목은 Lync Server 2013에서 올바르게 작동 하지 않습니다. 파일에서 이 단계에 설명한 항목 유형을 조사하고, 필요에 따라 편집한 후 변경 내용을 파일럿 풀의 주소록 공유 폴더에 저장합니다.
    
    공백 또는 문장 부호가 포함된 문자열의 경우 정규화 규칙에 입력할 때 이러한 문자가 제거되기 때문에 이러한 문자열을 사용하면 정규화 규칙이 실패할 수 있습니다. 공백 또는 문장 부호가 필요한 문자열의 경우 문자열을 수정해야 합니다. 예를 들어 다음 문자열을 사용하면 정규화 규칙이 실패합니다.
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    다음 문자열을 사용하면 정규화 규칙이 실패하지 않습니다.
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

