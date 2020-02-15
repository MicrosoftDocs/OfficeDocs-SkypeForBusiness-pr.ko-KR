---
title: 'Lync Server 2013: 주소록 서버 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1782dbc22b94ed492878c545df70fa1bdaaeeeb3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="540ef-102">Lync Server 2013의 주소록 서버 cmdlet</span><span class="sxs-lookup"><span data-stu-id="540ef-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="540ef-103">_**마지막으로 수정 된 항목:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="540ef-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="540ef-104">Active Directory 도메인 서비스와 Microsoft Lync Server 2013 사이에 주소록 서버가 중개 됩니다.</span><span class="sxs-lookup"><span data-stu-id="540ef-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="540ef-105">주소록 서버는 Lync Server 2013에 저장 되어 있는 사용자 정보가 Active Directory에 저장 된 사용자 정보와 동기화 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="540ef-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="540ef-106">이 작업은 주소록 파일을 사용자 데이터베이스에 저장된 정보와 주기적으로 동기화하는 방식으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="540ef-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="540ef-107">Lync Server에는 주소록 서버를 관리 하기 위한 여러 개의 cmdlet이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="540ef-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="540ef-108">주소록 서버 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="540ef-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="540ef-109">Lync Server 제어판에서는 주소록 서버 설정을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="540ef-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="540ef-110">Windows PowerShell은 이러한 설정을 관리 하기 위한 기본 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="540ef-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="540ef-111">다음은 주소록 서버 관리에 직접적으로 관련된 cmdlet 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="540ef-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="540ef-112">**주소록 서버**</span><span class="sxs-lookup"><span data-stu-id="540ef-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="540ef-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="540ef-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="540ef-114">[새-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="540ef-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="540ef-115">[CsAddressBookConfiguration 제거](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="540ef-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="540ef-116">[설정-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="540ef-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="540ef-117">[업데이트-Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="540ef-117">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="540ef-118">[디버그-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="540ef-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="540ef-119">[테스트-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="540ef-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="540ef-120">[테스트-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="540ef-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="540ef-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="540ef-121">See Also</span></span>


[<span data-ttu-id="540ef-122">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="540ef-122">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

