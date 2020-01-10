---
title: 비즈니스용 Skype 서버에서 고해상도 사진 사용 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: '요약: Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 또는 Exchange Online 및 비즈니스용 Skype 서버에서 고해상도 사진의 사용을 구성 합니다.'
ms.openlocfilehash: 598490cfc80b8885a570317a7559bfc4cdd3caf5
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001178"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="f593b-103">비즈니스용 Skype 서버에서 고해상도 사진 사용 구성</span><span class="sxs-lookup"><span data-stu-id="f593b-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="f593b-104">**요약:** Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 또는 Exchange Online 및 비즈니스용 Skype 서버에서 고해상도 사진의 사용을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online and Skype for Business Server.</span></span>
  
<span data-ttu-id="f593b-105">비즈니스용 Skype Server에서 사진에는 사용자의 Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 또는 Exchange Online 사서함에 저장할 수 있으며,이를 통해 사진 크기를 최대 648 x 648 x e/x e e</span><span class="sxs-lookup"><span data-stu-id="f593b-105">In Skype for Business Server, photos can be stored in a user's Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="f593b-106">또한 Exchange Server는 필요에 따라 다양 한 제품에서 사용할 수 있도록 이러한 사진의 크기를 자동으로 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="f593b-107">일반적으로 다음과 같은 세 가지 사진 크기와 해상도를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="f593b-108">64 픽셀 x 64 픽셀, Active Directory thumbnailPhoto 특성에 사용 되는 크기</span><span class="sxs-lookup"><span data-stu-id="f593b-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="f593b-109">Exchange Server에 사진을 업로드 하는 경우 Exchange에서 자동으로 64 픽셀을 해당 사진의 64 픽셀 버전으로 만들고 사용자의 thumbnailPhoto 특성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="f593b-110">그러나 반대의 경우도 마찬가지입니다. Active Directory에서 thumbnailPhoto 특성을 수동으로 업데이트 하면 사용자의 Exchange 사서함에 있는 사진이 자동으로 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="f593b-111">96 픽셀 x 96 픽셀, microsoft outlook 2013 웹 앱, Microsoft Outlook 2013, 비즈니스용 Skype Web App 및 비즈니스용 Skype에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="f593b-112">Skype for Business 및 비즈니스용 skype Web app for business for 648 픽셀을 통해 648 픽셀을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="f593b-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f593b-113">리소스가 있는 경우 648 x 648 사진을 업로드 하는 것이 좋습니다. 이는 Office 2013 응용 프로그램에서 최대 해상도와 최적의 화질을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="f593b-114">크기가 648 x 648이 고 깊이가 24 비트인 각 JPEG 사진의 파일 크기는 약 240 kb입니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="f593b-115">즉, 4 개 사용자 사진 마다 약 1mb의 디스크 공간이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="f593b-116">Exchange Web Services를 사용 하 여 액세스 되는 고해상도 사진에는 Outlook 2013 웹 앱을 실행 하는 사용자가 업로드할 수 있습니다. 사용자는 자신만의 사진만 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="f593b-117">그러나 관리자는 Exchange 관리 셸 및 다음과 같은 일련의 Windows PowerShell 명령을 사용 하 여 사용자의 사진을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="f593b-118">앞의 예제에서 첫 번째 명령은 `Get-Content` cmdlet을 사용 하 여 파일 C:\Photos\Kenmyer.jpg의 내용을 읽고 해당 데이터를 $photo 이라는 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="f593b-119">두 번째 명령에서는 Exchange cmdlet `Set-UserPhoto` 을 사용 하 여 사진을 업로드 하 고 해당 사진을: 진구 Myer의 사용자 계정에 첨부 합니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f593b-120">이 예제에서는: 진구 Myer의 Active Directory 표시 이름이 사용자 계정 Id로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="f593b-121">사용자의 SMTP 주소 또는 사용자 계정 이름과 같은 다른 식별자를 사용 하 여 사용자 계정을 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="f593b-122">자세한 내용은의 Set UserPhoto cmdlet [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) 에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f593b-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="f593b-123">사진을 업로드 하는 것은: 진구 Myer의 사용자 계정에 해당 사진을 지정 하는 것과 동등 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-123">Uploading the photo does not equate to assigning that photo to Ken Myer's user account.</span></span> <span data-ttu-id="f593b-124">대신 사진을 업로드 하면 해당 사진의 미리 보기가 Outlook Web App 옵션 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-124">Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page.</span></span> <span data-ttu-id="f593b-125">실제로 해당 사진을 사용자 계정에 할당 하려면 사용자가 옵션 페이지에서 **저장** 을 클릭 해야 하거나 관리자가 예제에서 세 번째 명령을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-125">To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example.</span></span> <span data-ttu-id="f593b-126">세 번째 명령은 저장 매개 변수를 사용 하 여 사진을: 진구 Myer의 사용자 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-126">That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="f593b-127">새 사진이 사용자 계정에 할당 되었는지 확인 하려면: 진구 Myer에서 비즈니스용 Skype에 로그온 하 여 **옵션**을 선택한 다음 **내 사진을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="f593b-128">새로 업로드 된 사진은: 진구의 개인 사진으로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="f593b-129">또는 관리자가 Internet Explorer를 시작 하 고 다음과 같은 URL로 이동 하 여 사용자의 사진을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

<span data-ttu-id="f593b-130">관리자가 Internet Explorer를 사용 하 여 사진을 볼 수 있지만 사용자가 비즈니스용 Skype에서 자신의 사진을 볼 수 없는 경우 Exchange Web Services 또는 Exchange 자동 검색 서비스에 연결 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="f593b-131">또한이 사진을 비즈니스용 Skype에서 사용할 수 있도록 하기 위해 추가 구성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="f593b-132">대신 사진이 업로드 되 고 `Set-UserPhoto` cmdlet이 실행 된 후 바로 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f593b-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
