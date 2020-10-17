---
title: 'Lync Server 2013: 주소록 관리용 Windows PowerShell cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets for Address Book management
ms:assetid: 73bfa949-5628-4156-ad20-fe07a0dc6216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429708(v=OCS.15)
ms:contentKeyID: 48184512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170936c8ca4445a7dc4e816c2300176d9b730f80
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535325"
---
# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="e76f1-102">Lync Server 2013의 주소록 서비스용 Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="e76f1-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e76f1-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e76f1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e76f1-104">Lync Server에서는 주소록 서비스를 관리 하 고 구성 하기 위한 다양 한 Windows PowerShell 명령줄 인터페이스 cmdlet을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e76f1-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="e76f1-105">이러한 cmdlet 중 일부는 이전 버전의 Office Communications Server에서 사용 되는 ABServer.exe 명령 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76f1-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="e76f1-106">다음 항목은 주소록 서비스에 대한 정보를 설정하고 만들고 검색하는 데 사용되는 cmdlet와 클라이언트가 주소록 서비스 파일 및 설정을 검색할 때 주소록 서비스에서 사용하는 웹 서비스에 대한 해당 구성 및 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="e76f1-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="e76f1-107">이러한 모든 cmdlet은 관리 도구가 설치 된 서버 또는 워크스테이션의 Lync Server 도구에 있는 Lync Server 관리 셸을 통해 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e76f1-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e76f1-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e76f1-108">In This Section</span></span>

  - [<span data-ttu-id="e76f1-109">Lync Server 2013의 주소록 관리를 위한 신규-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="e76f1-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-110">Lync Server 2013의 주소록 관리에 대해 CsAddressBookConfiguration 설정</span><span class="sxs-lookup"><span data-stu-id="e76f1-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-111">Lync Server 2013의 주소록 관리를 위한 Get-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="e76f1-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-112">Lync Server 2013의 주소록 관리를 위한 CsAddressBookConfiguration 제거</span><span class="sxs-lookup"><span data-stu-id="e76f1-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-113">Lync Server 2013의 주소록 관리를 위한 테스트-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="e76f1-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-114">Lync Server 2013의 주소록 관리를 위한 테스트-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="e76f1-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-115">Update-csaddressbook Lync Server 2013의 주소록 관리에 대 한 업데이트</span><span class="sxs-lookup"><span data-stu-id="e76f1-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-116">Lync Server 2013의 주소록 관리를 위한 신규 및 CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="e76f1-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-117">Lync Server 2013의 주소록 관리에 대 한 CsClientPolicy 설정</span><span class="sxs-lookup"><span data-stu-id="e76f1-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-118">Lync Server 2013의 주소록 관리를 위한 get-help 서비스</span><span class="sxs-lookup"><span data-stu-id="e76f1-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-119">Lync Server 2013의 Set-cswebserviceconfiguration for 주소록 관리를 위한 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="e76f1-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-120">Lync Server 2013의 Set-cswebserviceconfiguration for 주소록 관리</span><span class="sxs-lookup"><span data-stu-id="e76f1-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-121">Set-cswebserviceconfiguration Lync Server 2013의 주소록 관리에 대 한 설정</span><span class="sxs-lookup"><span data-stu-id="e76f1-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="e76f1-122">Lync Server 2013의 Set-cswebserviceconfiguration for 주소록 관리를 위한 제거</span><span class="sxs-lookup"><span data-stu-id="e76f1-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="e76f1-123">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="e76f1-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e76f1-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e76f1-124">See Also</span></span>


[https://go.microsoft.com/fwlink/p/?linkId=205826](https://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

