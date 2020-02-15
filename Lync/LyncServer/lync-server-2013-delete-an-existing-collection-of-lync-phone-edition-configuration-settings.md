---
title: Lync Phone Edition 구성 설정의 기존 컬렉션 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 175f7d9cd5417f350dd08873aa748c56d829d86d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="dca6a-102">Lync Server 2013에서 Lync Phone Edition 구성 설정의 기존 컬렉션 삭제</span><span class="sxs-lookup"><span data-stu-id="dca6a-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dca6a-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="dca6a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="dca6a-104">Lync Phone Edition을 실행 하는 장치에 대 한 설정 컬렉션을 더 이상 사용 하지 않으려면 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="dca6a-105">사이트의 컬렉션을 삭제하면 전역 설정이 해당 사이트의 전화에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="dca6a-106">전역 컬렉션은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="dca6a-107">컬렉션을 삭제하는 대신 일부 설정을 변경만 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="dca6a-108">이 작업을 수행 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">2013 Lync Phone Edition 구성 설정 모음을 만들거나 수정 하는</A>방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dca6a-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="dca6a-109">Lync Phone Edition 구성 설정 모음을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="dca6a-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="dca6a-110">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dca6a-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dca6a-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dca6a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dca6a-113">왼쪽 탐색 모음에서 **클라이언트**를 클릭하고 **장치 구성** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="dca6a-114">**장치 구성** 페이지에서 삭제할 컬렉션을 클릭하고 **편집** 메뉴를 클릭한 후에 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="dca6a-p104">전역 컬렉션을 삭제해도 단순히 설정이 기본 설정으로 돌아가며 컬렉션이 제거되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-p104">If you delete the global collection, the settings just revert to the default settings. The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="dca6a-117">확인 상자에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dca6a-118">Windows PowerShell Cmdlet을 사용 하 여 Lync Phone Edition 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="dca6a-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dca6a-119">Lync Phone Edition 구성 설정은 Windows PowerShell 및 **CsUCConfiguration** cmdlet을 사용 하 여 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="dca6a-120">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dca6a-121">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dca6a-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="dca6a-122">Lync Phone Edition 구성 설정의 지정 된 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="dca6a-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="dca6a-123">다음 명령은 Redmond 사이트에 적용된 UC 전화 구성 설정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="dca6a-124">사이트 범위에 적용 된 모든 Lync Phone Edition 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="dca6a-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="dca6a-125">다음 명령은 서비스 범위에 적용된 모든 UC 전화 구성 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="dca6a-126">전화 잠금이 사용 하지 않도록 설정 된 모든 Lync Phone Edition 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="dca6a-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="dca6a-127">다음 명령은 전화 잠금이 사용하지 않도록 설정된 UC 전화 구성 설정 컬렉션을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dca6a-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="dca6a-128">자세한 내용은 [Remove-set-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dca6a-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

