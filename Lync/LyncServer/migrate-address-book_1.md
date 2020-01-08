---
title: 주소록 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dff13c31ecf203d6e6e4b60c22a3792475e403f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="2ceb2-102">주소록 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2ceb2-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ceb2-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2ceb2-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2ceb2-104">**주소록을 사용자 지정 정규화 규칙으로 마이그레이션하려면 다음을 처리 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2ceb2-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="2ceb2-105">주소록 공유 폴더\_의\_루트\_에\_있는 회사 전화 번호 정규화 규칙 .txt 파일을 찾아 Lync Server 2013의 파일럿 풀에 있는 주소록 공유 폴더의 루트에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ceb2-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2ceb2-106">예제 주소록 정규화 규칙은 ABS 웹 구성 요소 파일 디렉터리에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ceb2-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="2ceb2-107">경로는 <STRONG>$installedDriveLetter: .\ Files\Microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. t a x,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2ceb2-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="2ceb2-108">이 파일 &nbsp; <STRONG></STRONG> &nbsp;을 Company_Phone_Number_Normalization_Rules으로 복사 하 여 주소록 공유 폴더의 루트 디렉터리로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ceb2-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="2ceb2-109">예를 들어 <STRONG>$serverX</STRONG>&nbsp;에서 공유 되는 주소록은 <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="2ceb2-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="2ceb2-110">메모장과 같은 텍스트 편집기를 사용 하 여\_회사 전화\_번호\_정규화\_규칙 .txt 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2ceb2-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="2ceb2-111">특정 유형의 항목이 Lync Server 2013에서 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ceb2-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="2ceb2-112">이 단계에서 설명 하는 항목 유형에 해당 하는 파일을 살펴보고 필요에 따라 편집한 다음 파일럿 풀의 주소록 공유 폴더에 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ceb2-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="2ceb2-113">필수 공백 또는 문장 부호를 포함 하는 문자열은 정규화 규칙에 입력 된 문자열에서 제거 되므로 정규화 규칙에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ceb2-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="2ceb2-114">필수 공백이 나 문장 부호를 포함 하는 문자열을 사용 하는 경우 문자열을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ceb2-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="2ceb2-115">예를 들어 다음 문자열을 선택 하면 정규화 규칙이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ceb2-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="2ceb2-116">다음 문자열은 정규화 규칙을 실패 시 키 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ceb2-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

