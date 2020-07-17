---
title: Lync에서 사용자 사진이 표시 되는 방식
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d6f6f6f5578994831fd15329988d963a295832
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="57404-102">Lync에서 사용자 사진이 표시 되는 방식</span><span class="sxs-lookup"><span data-stu-id="57404-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57404-103">_**마지막으로 수정 된 항목:** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="57404-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="57404-104">**요약:** Lync 클라이언트에 표시 되는 사용자 사진은 사용 중인 Lync 기능 (예: 회의 또는 IM 채팅에 있는 경우)에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="57404-105">Lync 2010에는 다른 Lync 사용자에 게 표시 되는 Lync 프로필에 사진을 포함할 수 있는 기능이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="57404-106">Lync 클라이언트에서 연락처에 대 한 사진을 표시할지 여부를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="57404-107">Lync 2013에서는 사용자를 위해 고해상도 사진을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="57404-108">이 항목에서는 Lync 클라이언트가 사용자 사진, 이미지가 저장 되는 위치, 각 이미지 원본에 대 한 제한 사항, 다양 한 Lync services에서 사용자 사진을 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="57404-109">계획 고려 사항</span><span class="sxs-lookup"><span data-stu-id="57404-109">Planning considerations</span></span>

<span data-ttu-id="57404-110">사용자 사진에 대 한 지원 구현 계획을 수립할 때 다음을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="57404-111">고화질 사용자 사진을 지원 하려면 사용자의 사서함이 Exchange 2013에 있고 Lync 사용자 계정이 Lync 2013 풀에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="57404-112">고화질 사용자 사진은 Lync Server 2013 및 Exchange 2013이 모두 사용 되는 환경 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="57404-113">Exchange 2010에 사서함이 있는 사용자는 항상 AD DS의 **thumbnailPhoto** 특성을 사용자 사진의 원본으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="57404-114">AD DS의 **thumbnailPhoto** 특성으로 저장 된 사용자 사진은 외부/페더레이션 대화 상대에 게 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="57404-115">사용자 연락처에 대 한 사진이 AD DS에 저장 된 경우 사용 되는 이미지 파일은 96 × 96 픽셀로 제한 되며, 100 개 이하의 파일 크기는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="57404-116">Lync Server와 Exchange Server 간의 연결이 끊어지면 사용자의 낮은 해상도가 AD DS에서 **thumbnailPhoto** , 내부 사용자에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="57404-117">고해상도 사용자 사진은 현재 발표자가 비디오를 사용할 수 없는 경우 Lync 2013 모임에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="57404-118">또한 갤러리의 축소판 그림 위로 마우스를 이동 하면 고해상도 사진이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="57404-119">Lync 2010의 사용자 사진</span><span class="sxs-lookup"><span data-stu-id="57404-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="57404-120">Lync 2010 클라이언트에서는 사용자 프로필에 대 한 사진, **기본 회사 사진** 및 **웹 주소에서 그림**을 표시 하는 두 가지 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="57404-121">기본 회사 사진</span><span class="sxs-lookup"><span data-stu-id="57404-121">Default corporate picture</span></span>

<span data-ttu-id="57404-122">**기본 회사 그림** 옵션을 선택 하면 Lync에서 Active Directory 도메인 서비스 로부터 사용자에 게 표시 되는 사진을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="57404-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="57404-123">사용 되는 이미지는 Active Directory 도메인 서비스의 **thumbnailPhoto** 특성에 대 한 값으로 정의 된 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="57404-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="57404-124">이 파일은 Exchange에서 Outlook의 이미지를 표시 하는 데 사용 하는 것과 같은 파일로,</span><span class="sxs-lookup"><span data-stu-id="57404-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="57404-125">Active Directory 도메인 서비스에서 이미지를 사용할 때 고려해 야 할 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="57404-126">크기가 최대 96 96 픽셀인 이미지만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="57404-127">이미지의 파일 크기는 100로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="57404-128">기본적으로 사용자는 **thumbnailPhoto** 특성에 사용 되는 이미지를 직접 Lync 클라이언트를 통해 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="57404-129">Active Directory 도메인 서비스를 통해이를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="57404-130">Active Directory 도메인 서비스에 저장 된 이미지는 페더레이션 연락처 인 경우에도 조직 외부의 대화 상대에 게 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="57404-131">대규모 조직에서는 많은 사용자를 위해 이미지를 저장 및 검색 하면 Active Directory 도메인 서비스 데이터베이스 크기 및 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="57404-132">제한 된 이미지 크기와 파일 크기는 저해상도 이미지만 사용할 수 있다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="57404-133">사용자가 Active Directory 도메인 서비스에서 사용자 사진을 관리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="57404-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="57404-134">사용자는 Lync 2010 클라이언트를 통해 Active Directory 도메인 서비스 프로필에 사용 되는 이미지를 직접 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="57404-135">사용 가능한 경우 다음 옵션 중 하나를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="57404-136">**SharePoint Server**     사용자는 SharePoint Server의 ' 내 사이트 '에 사진을 업로드 한 다음 [sharepoint에서 프로필 동기화를 구성](https://go.microsoft.com/fwlink/p/?linkid=507466) 하 여 Active Directory 도메인 서비스의 **thumbnailPhoto** 특성에 사진을 동기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="57404-137">**공개적으로 액세스할 수 있는 URL**     에 저장 된 사진 사용자는 사용 하려는 이미지에 대해 공개적으로 액세스할 수 있는 URL을 지정 하는 사용자 사진을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="57404-138">이미지는 암호 없이 공개적으로 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="57404-139">지정한 웹 주소에 저장 된 이미지는 현재 상태 정보의 대화 상대 카드 범주를 통해 다른 사용자에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="57404-140">Lync 클라이언트에서 사용자 사진을 표시 해야 하는 경우에는 지정 된 웹 주소에서 이미지를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="57404-141">**Windows PowerShell**     용 Exchange 2010 cmdlet 관리자는 **thumbnailPhoto** 특성을 관리 하기 위해 Exchange 2010 관리 셸에서 [import-recipientdataproperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="57404-142">Exchange 2010 cmdlet을 사용 하 여 이미지를 가져올 때 파일 크기는 10kb로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="57404-143">타사 **도구**     사용자는 **thumbnailPhoto** 특성에 대해 자신의 사진만 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="57404-144">웹 주소의 사진 표시</span><span class="sxs-lookup"><span data-stu-id="57404-144">Show a picture from a web address</span></span>

<span data-ttu-id="57404-145">**웹 주소에서 그림 표시** 옵션을 선택 하면 lync에서 입력 한 주소에 이미지를 가져오고 사용자 사진에 대해 lync에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="57404-146">웹 주소에서 이미지를 사용할 때 고려해 야 할 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="57404-147">파일 크기 제한은 [새-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet을 사용 하 여 정의 되는 클라이언트 정책의 **maxphotosizekb** 특성에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="57404-148">기본 크기 제한은 30kb입니다.</span><span class="sxs-lookup"><span data-stu-id="57404-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="57404-149">최대값은 100입니다.</span><span class="sxs-lookup"><span data-stu-id="57404-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="57404-150">이미지 해상도에 대 한 제한은 없지만 크기 제한을 초과 하는 이미지 파일을 사용 하려고 하면 Lync 클라이언트에 다운로드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="57404-151">이 값을 0으로 설정 하 여 모든 사용자 사진이 Lync에서 사용 되지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="57404-152">웹 주소의 사용자 사진은 외부 페더레이션 대화 상대에 게 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="57404-153">클라이언트 정책 cmdlet을 사용 하 여 사용자 사진 관리</span><span class="sxs-lookup"><span data-stu-id="57404-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="57404-154">Lync Server 2010에서는 클라이언트 정책 설정이 CsClientPolicy cmdlet을 사용 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="57404-155">구성 된 정책 설정은 대역내 프로 비전을 통해 클라이언트에 게 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="57404-156">사용자 사진 환경을 결정 하는 CsClientPolicy cmdlet의 두 매개 변수는 **DisplayPhoto** 및 **Maxphoto sizekb(** 입니다.</span><span class="sxs-lookup"><span data-stu-id="57404-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="57404-157">**DisplayPhoto** 및 **Maxphotosizekb** 해당 하는 대역내 프로 비전 매개 변수는 **PhotoUsage**로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="57404-158">**PhotoUsage** 매개 변수의 값은 **endpointConfiguration** **provisionGroup**를 통해 클라이언트로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="57404-159">자세한 내용은 [클라이언트 정책 및 설정 개요](https://go.microsoft.com/fwlink/?linkid=507470) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57404-159">See [Overview of Client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="57404-160">**DisplayPhoto** 매개 변수 값은 사용자의 사진 이미지 원본을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="57404-161">다음 표에는 지원 되는 값이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57404-162">DisplayPhoto 매개 변수 값</span><span class="sxs-lookup"><span data-stu-id="57404-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="57404-163">이미지 원본</span><span class="sxs-lookup"><span data-stu-id="57404-163">Image source</span></span></th>
<th><span data-ttu-id="57404-164">Lync 2010 클라이언트 설정</span><span class="sxs-lookup"><span data-stu-id="57404-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57404-165">NoPhoto</span><span class="sxs-lookup"><span data-stu-id="57404-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="57404-166">없음</span><span class="sxs-lookup"><span data-stu-id="57404-166">none</span></span></p></td>
<td><p><span data-ttu-id="57404-167"><strong>내 사진을 표시하지 않음</strong></span><span class="sxs-lookup"><span data-stu-id="57404-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57404-168">사진 Fromadonly</span><span class="sxs-lookup"><span data-stu-id="57404-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="57404-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="57404-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="57404-170"><strong>기본 회사 사진</strong></span><span class="sxs-lookup"><span data-stu-id="57404-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57404-171">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="57404-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="57404-172">웹 주소</span><span class="sxs-lookup"><span data-stu-id="57404-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="57404-173"><strong>웹 주소의 사진 표시</strong></span><span class="sxs-lookup"><span data-stu-id="57404-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="57404-174">Lync 2010 클라이언트에서 사진을 가져오는 방법</span><span class="sxs-lookup"><span data-stu-id="57404-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="57404-175">Lync 2010에서는 사용자 사진이 주소록 서비스에 의해 서버에서 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="57404-176">Lync 클라이언트는 먼저 메일 그룹 확장 웹 서비스를 통해 노출 되는 서버에서 ABWQ (주소록 웹 쿼리) 서비스를 쿼리 하 여 사용자 사진을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="57404-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="57404-177">클라이언트는 이미지 파일을 받은 다음 사용자의 캐시에 복사 하 여 표시 해야 할 때마다 이미지를 다운로드 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="57404-178">쿼리에서 반환 된 특성 값은 사용자에 대 한 캐시 된 주소록 서비스 항목에도 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="57404-179">주소록 서비스는 캐시 된 모든 이미지를 24 시간 마다 삭제 하므로 새 사용자 이미지를 서버의 캐시에서 업데이트 하는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="57404-180">[Update-csaddressbook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet을 사용 하 여 캐시를 강제로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="57404-181">현재 상태에 포함 된 사용자 사진에는 Lync 클라이언트가 새로운 이미지를 사용할 수 있는지 여부를 확인 하기 위해 사용 하는 연결 된 해시 값도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="57404-182">현재 상태에서 사용 되는 이미지 파일에 대 한 변경 내용이 클라이언트에 자동으로 통지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="57404-183">사진이 GalContacts 데이터베이스에 저장 되지 않기 때문에 사용자 사진을 다운로드 하는 것은 클라이언트 정책 (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">설정-CsClientPolicy</A>)의 <STRONG>addressbookavailability</STRONG> 설정에 종속 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="57404-184">ABWQ 서비스에 대 한 쿼리에는 다음과 같은 특성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="57404-185">**사진 해시**     이진 사진 데이터의 해시 값으로, 현재 사진이 변경 되었는지 여부를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="57404-186">**PhotoRelPath**     서버에 저장 된 이미지 파일의 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="57404-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="57404-187">**사진 크기**     이미지 파일의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="57404-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="57404-188">**타임 스탬프**     서버에서 이미지 파일을 마지막으로 다운로드 한 날짜와 시간으로, 클라이언트 캐시에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="57404-189">그런 다음 이미지 파일을 검색 한 후 Lync 2010 클라이언트는 쿼리에서 반환 된 특성 값을 클라이언트에서 수신 되는 특성 값과 비교 하 여 해당 쿼리가 서로 다른 지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="57404-190">값이 다르면 클라이언트는 HTTP GET 요청을 사용 하 여 로그인 한 사용자의 이미지 파일을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="57404-191">또한 클라이언트는 서버의 **사진 해시** 특성 값을 클라이언트의 값과 비교 하기 위해 이미지 파일의 캐시 된 버전을 만든 시간부터 24 시간 마다 서버를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="57404-192">값이 다르면 클라이언트에서 이미지 파일이 변경 되었음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="57404-193">업데이트 된 이미지 파일을 가져오기 위해 클라이언트는 ABWQ 서비스를 다시 쿼리하여 클라이언트 캐시의 이미지 파일을 서버의 이미지 파일로 업데이트 하며,이 경우 클라이언트 캐시의 파일에 **타임 스탬프가** 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="57404-194">다음은 ABWQ 서비스에 대 한 쿼리에 대 한 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="57404-194">The following is an example response to a query to the ABWQ service:</span></span>
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="57404-195">Lync 2013의 사용자 사진</span><span class="sxs-lookup"><span data-stu-id="57404-195">User photos in Lync 2013</span></span>

<span data-ttu-id="57404-196">Lync 2013에서는 사용자 사진에 대 한 고해상도 이미지 지원이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="57404-197">Lync 2013에는 사용자의 2013 사서함에 사용자 사진을 저장 하는 기능도 포함 되어 있으며,이는 Lync 2010에 있는 이미지 해상도 및 크기 제한이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="57404-198">Lync 2013의 사용자 사진에는 최대 648 648 픽셀까지 사용할 수 있으며 파일 크기는 최대 20mb입니다.</span><span class="sxs-lookup"><span data-stu-id="57404-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="57404-199">Lync 2013의 고해상도 사진은 Exchange 2013의 사용자 사서함에 위치 해야 하며 Lync 2013 클라이언트 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="57404-200">이 Exchange와의 통합은 Lync, Exchange 및 SharePoint Oauth 라는 2013 버전에 포함 된 새 인증 프레임 워크를 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="57404-201">Exchange 2013이 배포에 사용 되지 않는 경우 사용자 사진에 대 한 지원은 Lync 2010와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="57404-202">그러나 사용할 사진을 선택할 수 있는 사용자 옵션은 Lync 2013 클라이언트에서 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="57404-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="57404-203">Lync 2013 클라이언트에서 사용자는 **내 그림 숨기기** 또는 **그림 표시**를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="57404-204">**웹 사이트의 그림 표시** 옵션은 기본적으로 사용할 수 없지만 클라이언트 정책을 할당 하 여 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="57404-205">내 사진 숨기기</span><span class="sxs-lookup"><span data-stu-id="57404-205">Hide my picture</span></span>

<span data-ttu-id="57404-206">사용자 사진에 대 한 설정은 Lync 2013의 **옵션** 대화 상자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="57404-207">**그림 숨기기**를 선택 하면 lync 클라이언트에서는 사용자 사진이 표시 되지 않지만 대화 상대 카드와 lync 외부에는 여전히 사진이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="57404-208">내 사진 표시</span><span class="sxs-lookup"><span data-stu-id="57404-208">Show my picture</span></span>

<span data-ttu-id="57404-209">**내 그림 표시** 옵션을 선택 하면 lync 클라이언트 및 lync 대화의 다른 사용자에 게 사용자 사진이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="57404-210">사용 되는 이미지는 AD DS에 저장 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="57404-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="57404-211">웹 사이트에서 그림 표시</span><span class="sxs-lookup"><span data-stu-id="57404-211">Show a picture from a website</span></span>

<span data-ttu-id="57404-212">클라이언트 정책이 사용 하도록 설정 된 후 **웹 사이트에서 그림 표시** 옵션을 Lync 2013에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="57404-213">클라이언트 버전은 [Lync 누적 업데이트: 11 월 2013](https://go.microsoft.com/fwlink/p/?linkid=509908)에 설치 된 15.0.4535.1002 보다 최신 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="57404-214">사용자가 로그 아웃 한 다음 다시 로그인 하 여 클라이언트의 변경 내용을 확인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="57404-215">Lync Server 관리 셸에서는 [CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) 정책을 실행 하 여 **웹 사이트 설정에서 그림을 표시** 하도록 클라이언트 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="57404-216">다음 예제 cmdlet은 배포의 모든 사용자에 대해 정책을 전역적으로 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="57404-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="57404-217">이미지가 사용자 사서함에 업로드 되 면 Exchange에서 클라이언트 응용 프로그램에 사용할 수 있는 더 낮은 해상도 버전의 이미지를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57404-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="57404-218">사용자 사진만 AD DS 에서도 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="57404-219">AD DS에서 이미지 파일이 업데이트 되 면 48 x 48 픽셀 이미지가 생성 되어 AD DS의 thumbnailPhoto에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="57404-220">기존 이미지는 모두 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="57404-220">Any existing image is replaced.</span></span> <span data-ttu-id="57404-221">따라서 AD DS에 96 x 96 이미지를 추가한 경우 새 48 x 48 이미지를 사용 하 여 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="57404-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="57404-222">이 기능은 클라이언트에서 Lync 2010 클라이언트를 사용 하는 사용자가 AD DS에서 사용자 사진을 가져오기 때문에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="57404-223">조직에 Lync 2010 클라이언트가 있는 경우 96 x 96 픽셀 이미지를 가져와서 AD DS에서 만든 것을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="57404-224">Lync 2013의 사용자 사진 지원</span><span class="sxs-lookup"><span data-stu-id="57404-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="57404-225">Lync 2013에서는 다음 표에 설명 된 것 처럼 사용자 사진에 대해 3 가지 이미지 해상도가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="57404-226">사용 되는 이미지는 Lync 사용자에 게 할당 된 클라이언트 정책 설정에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="57404-227">자세한 내용은이 항목의 "사용자 사진에 대 한 클라이언트 정책 cmdlet 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57404-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57404-228">이미지 해상도 (픽셀)</span><span class="sxs-lookup"><span data-stu-id="57404-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="57404-229">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="57404-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57404-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="57404-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="57404-231">더 높은 해상도 이미지를 선택 하지 않은 경우에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57404-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="57404-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="57404-233">Outlook Web App 및 Outlook 2013에서 사용 됨</span><span class="sxs-lookup"><span data-stu-id="57404-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57404-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="57404-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="57404-235">Lync 2013 데스크톱 클라이언트 및 Lync 2013 웹 응용 프로그램에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57404-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="57404-236">Exchange 2013에서 사서함이 사용 하도록 설정 된 모든 사용자는 Outlook Web Access 또는 Lync 2013 클라이언트 옵션을 통해 고해상도 사진을 비롯 한 다른 이미지를 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="57404-237">사용 되는 이미지에 권장 되는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57404-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="57404-238">**이미지 해상도**     648 x 648 픽셀</span><span class="sxs-lookup"><span data-stu-id="57404-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="57404-239">**색 농도**     24 비트</span><span class="sxs-lookup"><span data-stu-id="57404-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="57404-240">**이미지 파일 크기**     최대 20mb</span><span class="sxs-lookup"><span data-stu-id="57404-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="57404-241">**파일 형식**     JPEG</span><span class="sxs-lookup"><span data-stu-id="57404-241">**File format**   JPEG</span></span>

<span data-ttu-id="57404-242">일반적인 24 비트 JPEG 이미지에는 648 픽셀 x 648 픽셀로 표시 되는 파일 크기는 약 240 KB 이기 때문에 4 사용자 사진 마다 1MB의 저장소 공간이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="57404-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

