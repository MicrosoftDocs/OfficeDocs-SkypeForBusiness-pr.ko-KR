---
title: 'Lync Server 2013: 업데이트-주소록 관리에 대 한 CsAddressBook'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7e10f9d52d9e4090601330cad44d5da03e69540
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="3471f-102">업데이트-Lync Server 2013의 주소록 관리에 대 한 CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="3471f-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3471f-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3471f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3471f-104">이 cmdlet을 실행할 수 있는 사람: 기본적으로 다음 그룹의 구성원은 업데이트 CsAddressBook cmdlet을 로컬로 실행할 권한이 있습니다. RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3471f-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="3471f-105">이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3471f-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="3471f-106">CsAddressBook cmdlet은 Office Communications Server에서 **abserver .exe – syncNow** 명령을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="3471f-106">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server.</span></span> <span data-ttu-id="3471f-107">Cmdlet의 용도는 예약 된 시간을 기다리지 않고 즉시 동기화를 시작 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3471f-107">The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time.</span></span> <span data-ttu-id="3471f-108">첫 번째 예제 명령은 조직의 모든 주소록을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3471f-108">The first example command updates all Address Books in the organization.</span></span> <span data-ttu-id="3471f-109">두 번째는 정의 된 서버와 연결 된 주소록만 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3471f-109">The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3471f-110">Lync Server 2013에서 Lync Server 사용자 복제기는 Active Directory에서 변경 된 내용을 선택 하 고 구성 된 간격을 기준으로 Lync Server 사용자 데이터베이스를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3471f-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="3471f-111">또한 Lync Server 사용자 복제기는 관리자가 CSAddressBook를 실행 하지 않아도 RTCab 데이터베이스에 대 한 변경 내용을 빠르게 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="3471f-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="3471f-112">주소록 파일 다운로드를 사용 하는 경우 관리자는 업데이트 CSAddressBook 실행 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3471f-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="3471f-113">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3471f-113">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="3471f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3471f-114">See Also</span></span>


[<span data-ttu-id="3471f-115">업데이트-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="3471f-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

