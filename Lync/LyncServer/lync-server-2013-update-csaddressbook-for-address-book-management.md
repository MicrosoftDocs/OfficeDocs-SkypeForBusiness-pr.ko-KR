---
title: 'Lync Server 2013: Update-csaddressbook for 주소록 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dc4452eadb1584f9e99e9b1b3508e507c2e8fff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="8e558-102">Update-csaddressbook Lync Server 2013의 주소록 관리에 대 한 업데이트</span><span class="sxs-lookup"><span data-stu-id="8e558-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e558-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8e558-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8e558-p101">이 cmdlet을 실행할 수 있는 사용자: 기본적으로 RTCUniversalUserAdmins 및 RTCUniversalServerAdmins 그룹의 구성원은 Update-CsAddressBook cmdlet을 로컬로 실행할 수 있습니다. 사용자가 직접 만든 사용자 지정 RBAC(역할 기반 액세스 제어) 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 가져오려면 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8e558-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="8e558-p102">Update-CsAddressBook cmdlet은 Office Communications Server의 **abserver.exe –syncNow** 명령을 대체합니다. 이 cmdlet은 예약된 시간을 기다리지 않고 동기화를 즉시 시작하는 데 사용됩니다. 첫 번째 예제 명령에서는 조직의 모든 주소록을 업데이트합니다. 두 번째 예제 명령에서는 정의된 서버에 연결된 주소록만 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="8e558-p102">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server. The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time. The first example command updates all Address Books in the organization. The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e558-110">Lync Server 2013에서는 Lync Server 사용자 복제기가 Active Directory에서 변경 된 내용을 선택 하 고 구성 된 간격에 따라 Lync Server 사용자 데이터베이스를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e558-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="8e558-111">또한 Lync Server 사용자 복제기는 관리자가 Update-csaddressbook를 실행 하지 않고 RTCab 데이터베이스에 대 한 변경 내용을 빠르게 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e558-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="8e558-112">주소록 파일 다운로드가 설정된 경우 관리자는 Update -CSAddressBook만 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e558-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="8e558-113">예:</span><span class="sxs-lookup"><span data-stu-id="8e558-113">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="8e558-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e558-114">See Also</span></span>


[<span data-ttu-id="8e558-115">업데이트-Update-csaddressbook</span><span class="sxs-lookup"><span data-stu-id="8e558-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

