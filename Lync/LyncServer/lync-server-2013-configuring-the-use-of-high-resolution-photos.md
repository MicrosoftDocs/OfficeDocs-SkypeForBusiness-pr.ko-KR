---
title: 'Lync Server 2013: 고해상도 사진 사용 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e817e86d6f05291192593e2345b9e4bc1c0b6db3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517361"
---
# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="74348-102">Microsoft Lync Server 2013에서 고해상도 사진 사용 구성</span><span class="sxs-lookup"><span data-stu-id="74348-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74348-103">_**마지막으로 수정 된 항목:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="74348-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="74348-104">Microsoft Lync Server 2010에서는 사용자가 연락처의 사진을 볼 수 있도록 하 고 다른 사용자가 자신의 사진을 사용 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="74348-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="74348-105">일반적으로 이러한 사진은 Active Directory에서 사용자의 thumbnailPhoto 특성의 일부로 저장되었으며, 이로 인해 사진의 크기와 해상도에 상당한 제한이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="74348-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="74348-106">thumbnailPhoto 특성은 최대 48 x 48픽셀 크기의 사진을 포함할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="74348-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="74348-107">그러나 Microsoft Lync Server 2013에서는 사진을 사용자의 Microsoft Exchange Server 2013 사서함에 저장할 수 있습니다. 이에 따라 사진 크기를 최대 648 픽셀, 648 픽셀까지 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="74348-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="74348-108">이 외에도 Exchange 2013에서는 필요에 따라 다양 한 제품에서 사용할 수 있도록 이러한 사진의 크기를 자동으로 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74348-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="74348-109">일반적으로 이 자동 조정 기능을 통해 세 가지 사진 크기 및 해상도를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74348-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="74348-110">48 x 48 픽셀, Active Directory thumbnailPhoto 특성에 사용 되는 크기</span><span class="sxs-lookup"><span data-stu-id="74348-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="74348-111">2013 Exchange에 사진을 업로드 하는 경우 Exchange에서 해당 사진의 48 픽셀 버전으로 48 픽셀을 자동으로 만들고 사용자의 thumbnailPhoto 특성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="74348-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="74348-112">그러나 reverse는 그렇지 않으며 Active Directory에서 thumbnailPhoto 특성을 수동으로 업데이트 하는 경우 사용자의 Exchange 2013 사서함에 있는 사진이 자동으로 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74348-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="74348-113">96 픽셀 x 96 픽셀 (Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App 및 Lync 2013)에서 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="74348-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="74348-114">648 Lync 2013 및 Microsoft Lync Web App에서 사용할 때 648 픽셀 단위</span><span class="sxs-lookup"><span data-stu-id="74348-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74348-p104">리소스가 충분한 경우 모든 Office 2013 응용 프로그램에서 최대의 해상도와 최적의 화질을 제공하는 648x648 사진을 업로드하는 것이 좋습니다. 크기가 648 x 648이고 비트 수준이 24인 각 JPEG 사진의 파일 크기는 약 240KB입니다. 즉, 4명의 사용자 사진마다 약 1MB가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="74348-p104">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications. Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes. That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="74348-118">Exchange 웹 서비스를 사용 하 여 액세스 하는 고해상도 사진에는 Outlook 2013 Web App을 실행 하는 사용자가 업로드할 수 있습니다. 사용자는 자신의 사진만 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74348-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="74348-119">그러나 관리자는 Exchange 관리 셸 및 다음과 같은 일련의 Windows PowerShell 명령을 사용 하 여 모든 사용자에 대 한 사진을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74348-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="74348-120">위 예제의 첫 번째 명령은 Get-Content cmdlet을 사용 하 여 파일 C: \\ 사진Kenmyer.jpg 내용을 읽고 \\ 해당 데이터를 $photo 이라는 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="74348-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="74348-121">두 번째 명령은 Set-UserPhoto Exchange cmdlet을 사용 하 여 사진을 업로드 하 고 해당 사진을 Ken Myer의 사용자 계정에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="74348-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74348-122">이 예에서는 사용자 계정 ID로 Ken Myer의 Active Directory 표시 이름이 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74348-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="74348-123">또한 사용자의 SMTP 주소 또는 사용자 계정 이름 등의 다른 식별자를 사용하여 사용자 계정을 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74348-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="74348-124">자세한 내용은의 Set-UserPhoto cmdlet에 대 한 설명서를 참조 하세요. <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A></span><span class="sxs-lookup"><span data-stu-id="74348-124">See the documentation for the Set-UserPhoto cmdlet at <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="74348-p108">사진을 업로드한다고 해서 해당 사진이 Ken Myer의 사용자 계정에 할당되는 것은 아닙니다. 사진을 업로드하면 단지 Outlook Web App 옵션 페이지에 해당 사진의 미리 보기가 표시됩니다. 실제로 사진을 사용자 계정에 할당하려면 사용자가 옵션 페이지에서 **저장**을 클릭하거나 관리자가 위 예에 있는 세 번째 명령을 실행해야 합니다. 세 번째 명령은 다음과 같이 Save 매개 변수를 사용하여 사진을 Ken Myer의 사용자 계정에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="74348-p108">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="74348-129">새 사진이 사용자 계정에 할당 되었는지 확인 하기 위해 Ken Myer에서 Lync 2013에 로그온 하 고 **옵션**을 선택한 다음 **내 그림**을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74348-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="74348-130">그러면 새로 업로드된 사진이 Ken의 개인 사진으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74348-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="74348-131">또한 관리자의 경우 Internet Explorer를 시작하고 다음과 유사한 URL로 이동하여 모든 사용자의 사진을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74348-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="74348-132">관리자가 Internet Explorer를 사용 하 여 사진을 볼 수 있으 나 사용자가 Lync 2013에서 해당 사진을 볼 수도 없으며,이는 일반적으로 Exchange 웹 서비스와의 연결 문제 또는 Exchange 자동 검색 서비스를 사용 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74348-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="74348-133">Lync 2013에서이 사진을 사용할 수 있도록 하기 위해 추가 구성이 필요 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74348-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="74348-134">대신, 사진이 업로드 되 고 Set-UserPhoto cmdlet이 실행 된 후에 즉시 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74348-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

