---
title: 'Lync Server 2013: 주소록 관리용 Windows PowerShell cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows PowerShell cmdlets for Address Book management
ms:assetid: 73bfa949-5628-4156-ad20-fe07a0dc6216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429708(v=OCS.15)
ms:contentKeyID: 48184512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 737496bbb6db1e003ec09a05980c3ef474c69924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="31db9-102">Lync Server 2013의 주소록 서비스에 대 한 Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="31db9-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31db9-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="31db9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="31db9-104">Lync Server는 주소록 서비스를 관리 하 고 구성 하는 다양 한 Windows PowerShell 명령줄 인터페이스 cmdlet을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="31db9-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="31db9-105">이러한 cmdlet 중 일부는 이전 버전의 Office Communications Server에 사용 되는 ABServer .exe 명령에 대 한 대체입니다.</span><span class="sxs-lookup"><span data-stu-id="31db9-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="31db9-106">다음 항목에서는 주소록 서비스에 대 한 정보를 설정, 생성 및 검색 하는 데 사용 되는 cmdlet에 대해 주소록 서비스에서 주소록 서비스를 검색할 때 사용 하는 웹 서비스에 대 한 구성 및 정보를 설명 합니다. 파일 및 설정</span><span class="sxs-lookup"><span data-stu-id="31db9-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="31db9-107">이러한 모든 cmdlet은 관리 도구가 설치 된 서버 또는 워크스테이션의 Lync Server 도구에 있는 Lync Server 관리 셸을 통해 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31db9-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="31db9-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="31db9-108">In This Section</span></span>

  - [<span data-ttu-id="31db9-109">Lync Server 2013의 주소록 관리를 위한 새 CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="31db9-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="31db9-110">Lync Server 2013의 주소록 관리에 대 한 집합-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="31db9-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="31db9-111">Lync Server 2013의 주소록 관리를 위한 가져오기-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="31db9-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="31db9-112">Lync Server 2013의 주소록 관리를 위한 CsAddressBookConfiguration 제거</span><span class="sxs-lookup"><span data-stu-id="31db9-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="31db9-113">Lync Server 2013의 주소록 관리를 위한 테스트-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="31db9-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="31db9-114">Lync Server 2013의 주소록 관리를 위한 테스트-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="31db9-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="31db9-115">업데이트-Lync Server 2013의 주소록 관리에 대 한 CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="31db9-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="31db9-116">Lync Server 2013의 주소록 관리에 대 한 새 CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="31db9-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="31db9-117">Lync Server 2013의 주소록 관리에 대 한 Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="31db9-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="31db9-118">Lync Server 2013의 주소록 관리를 위한 Get CsService</span><span class="sxs-lookup"><span data-stu-id="31db9-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="31db9-119">CsWebServiceConfiguration-Lync Server 2013의 주소록 관리를 위한 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="31db9-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="31db9-120">Lync Server 2013의 주소록 관리를 위한 get-help CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="31db9-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="31db9-121">Set-Lync Server 2013의 주소록 관리에 대 한 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="31db9-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="31db9-122">Lync Server 2013의 주소록 관리에 대 한 CsWebServiceConfiguration 제거</span><span class="sxs-lookup"><span data-stu-id="31db9-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="31db9-123">관련 단원</span><span class="sxs-lookup"><span data-stu-id="31db9-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="31db9-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31db9-124">See Also</span></span>


[http://go.microsoft.com/fwlink/p/?linkId=205826](http://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

