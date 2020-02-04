---
title: Lync Phone Edition 구성 설정의 기존 모음 삭제
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
ms.openlocfilehash: dbf7d49a14ce45550777c6c122cd799f6a511f76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="24012-102">Lync Server 2013에서 Lync Phone Edition 구성 설정의 기존 모음 삭제</span><span class="sxs-lookup"><span data-stu-id="24012-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24012-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="24012-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="24012-104">Lync Phone Edition을 실행 하는 장치에 대 한 설정 모음을 더 이상 사용 하지 않으려면 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="24012-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="24012-105">사이트에 대 한 컬렉션을 삭제 하면 해당 사이트의 휴대폰에 전역 설정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24012-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="24012-106">전역 모음은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24012-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="24012-107">컬렉션을 삭제 하는 대신 일부 설정을 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="24012-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="24012-108">이 작업을 수행 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Lync Server 2013에서 Lync Phone Edition 구성 설정 모음 만들기 또는 수정을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24012-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="24012-109">Lync Phone Edition 구성 설정 모음을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="24012-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="24012-110">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="24012-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="24012-111">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="24012-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="24012-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24012-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="24012-113">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 구성** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="24012-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="24012-114">**장치 구성** 페이지에서 삭제 하려는 모음을 클릭 하 고 **편집** 메뉴를 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="24012-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="24012-115">전역 컬렉션을 삭제 하면 설정이 기본 설정으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="24012-115">If you delete the global collection, the settings just revert to the default settings.</span></span> <span data-ttu-id="24012-116">컬렉션이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="24012-116">The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="24012-117">확인 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="24012-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="24012-118">Windows PowerShell Cmdlet을 사용 하 여 Lync Phone Edition 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="24012-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="24012-119">Windows PowerShell 및 **CsUCConfiguration** cmdlet을 사용 하 여 Lync Phone Edition 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24012-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="24012-120">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24012-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="24012-121">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24012-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="24012-122">Lync Phone Edition 구성 설정의 지정 된 모음을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="24012-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="24012-123">이 명령은 Redmond 사이트에 적용 된 UC 전화 구성 설정을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="24012-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="24012-124">사이트 범위에 적용 된 모든 Lync Phone Edition 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="24012-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="24012-125">이 명령은 서비스 범위에 적용 된 모든 UC 전화 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="24012-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="24012-126">전화 잠금이 사용 되지 않도록 설정 된 모든 Lync Phone Edition 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="24012-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="24012-127">이 명령은 전화 잠금이 사용 되지 않도록 설정 된 모든 UC 전화 구성 설정 모음을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="24012-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="24012-128">자세한 내용은 [제거-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24012-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

