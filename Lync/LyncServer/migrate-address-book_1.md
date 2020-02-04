---
title: 주소록 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2c904a122f781da08c92c6b1123cfeb1944dd2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>주소록 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

**주소록을 사용자 지정 정규화 규칙으로 마이그레이션하려면 다음을 처리 합니다.**

1.  주소록 공유 폴더\_의\_루트\_에\_있는 회사 전화 번호 정규화 규칙 .txt 파일을 찾아 Lync Server 2013의 파일럿 풀에 있는 주소록 공유 폴더의 루트에 복사 합니다.
    
    <div>
    

    > [!NOTE]  
    > 예제 주소록 정규화 규칙은 ABS 웹 구성 요소 파일 디렉터리에 설치 되어 있습니다. 경로는 <STRONG>$installedDriveLetter: .\ Files\Microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. t a x,</STRONG>. 이 파일 &nbsp; <STRONG></STRONG> &nbsp;을 Company_Phone_Number_Normalization_Rules으로 복사 하 여 주소록 공유 폴더의 루트 디렉터리로 바꿀 수 있습니다. 예를 들어 <STRONG>$serverX</STRONG>&nbsp;에서 공유 되는 주소록은 <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>와 비슷합니다.

    
    </div>

2.  메모장과 같은 텍스트 편집기를 사용 하 여\_회사 전화\_번호\_정규화\_규칙 .txt 파일을 엽니다.

3.  특정 유형의 항목이 Lync Server 2013에서 제대로 작동 하지 않습니다. 이 단계에서 설명 하는 항목 유형에 해당 하는 파일을 살펴보고 필요에 따라 편집한 다음 파일럿 풀의 주소록 공유 폴더에 변경 내용을 저장 합니다.
    
    필수 공백 또는 문장 부호를 포함 하는 문자열은 정규화 규칙에 입력 된 문자열에서 제거 되므로 정규화 규칙에 실패 합니다. 필수 공백이 나 문장 부호를 포함 하는 문자열을 사용 하는 경우 문자열을 수정 해야 합니다. 예를 들어 다음 문자열을 선택 하면 정규화 규칙이 실패 합니다.
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    다음 문자열은 정규화 규칙을 실패 시 키 지 않습니다.
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

