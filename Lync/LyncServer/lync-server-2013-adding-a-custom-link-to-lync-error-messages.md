---
title: 'Lync Server 2013: Lync 오류 메시지에 사용자 지정 링크 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c02534c76a26313818e9ed4af8c51c31621bbd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="b2f1a-102">Lync Server 2013의 Lync 오류 메시지에 사용자 지정 링크 추가</span><span class="sxs-lookup"><span data-stu-id="b2f1a-102">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2f1a-103">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="b2f1a-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="b2f1a-104">자체 문제 해결 또는 지원 센터 정보에 대 한 링크를 추가 하 여 Lync 2013 오류 메시지를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-104">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="b2f1a-105">이 작업을 수행 하려면 CustomLinkInErrorMessages 매개 변수를 사용 하 여 **신규 csclientpolicy** 또는 **Set-csclientpolicy** Lync Server Management Shell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-105">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="b2f1a-106">사용자 지정 링크의 텍스트는 "관리자의 지원 항목은 여기를 클릭 하세요." 이며 사용자 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-106">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="b2f1a-107">예를 들어 다음 명령은 모든 Lync 2013 오류 메시지의 각주 영역에 사용자 지정 링크가 표시 되도록 하 고 링크 대상을 다음으로 설정 합니다.http://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="b2f1a-107">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="b2f1a-108">**Grant-CSClientPolicy**를 사용하여 새로운 이 정책을 사용자에게 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-108">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="b2f1a-109">자세한 내용은 Lync Server 관리 셸 설명서에서 **New-csclientpolicy** 및 **Grant-csclientpolicy** 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-109">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

