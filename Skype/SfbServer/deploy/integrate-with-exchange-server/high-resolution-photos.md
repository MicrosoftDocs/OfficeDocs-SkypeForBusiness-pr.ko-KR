---
title: 비즈니스용 Skype 서버에서 고해상도 사진 사용 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: '요약: Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 또는 Exchange Online 및 비즈니스용 Skype 서버에서 고해상도 사진 사용을 구성합니다.'
ms.openlocfilehash: c55e5a90e222ea024dd63f72b26627141b2f113e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834008"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="edb27-103">비즈니스용 Skype 서버에서 고해상도 사진 사용 구성</span><span class="sxs-lookup"><span data-stu-id="edb27-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="edb27-104">**요약:** Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 또는 Exchange Online 및 비즈니스용 Skype 서버에서 고해상도 사진 사용을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online and Skype for Business Server.</span></span>
  
<span data-ttu-id="edb27-105">비즈니스용 Skype 서버에서 사진은 사용자의 Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 또는 Exchange Online 사서함에 저장하여 최대 648 x 648픽셀의 사진 크기를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-105">In Skype for Business Server, photos can be stored in a user's Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="edb27-106">또한 Exchange Server 다른 제품에서 사용할 수 있는 이러한 사진의 조정을 자동으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="edb27-107">일반적으로 이 자동 조정 기능을 통해 세 가지 사진 크기 및 해상도를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="edb27-108">64 x 64픽셀( Active Directory thumbnailPhoto 특성에 사용되는 크기)</span><span class="sxs-lookup"><span data-stu-id="edb27-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="edb27-109">사진을 업로드하여 Exchange Server 경우 Exchange는 해당 사진의 64 x 64픽셀 버전을 자동으로 만들고 사용자의 thumbnailPhoto 특성을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="edb27-110">그러나 반대의 경우도 마찬가지입니다. Active Directory에서 thumbnailPhoto 특성을 수동으로 업데이트하면 사용자의 Exchange 사서함에 있는 사진이 자동으로 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="edb27-111">Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, 비즈니스용 Skype Web App 및 비즈니스용 Skype에서 사용할 수 있는 96 x 96픽셀</span><span class="sxs-lookup"><span data-stu-id="edb27-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="edb27-112">비즈니스용 Skype 및 비즈니스용 Skype Web App Web App에서 사용할 수 있는 648 x 648픽셀</span><span class="sxs-lookup"><span data-stu-id="edb27-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="edb27-113">리소스가 있는 경우 648 x 648 사진을 업로드하는 것이 좋습니다. 는 모든 Office 2013 응용 프로그램에서 최대 해상도와 최적의 그림 품질을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="edb27-114">크기가 648 x 648이고 깊이가 24비트인 각 JPEG 사진의 파일 크기는 약 240킬로바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="edb27-115">즉, 4명의 사용자 사진마다 약 1MB가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="edb27-116">Exchange 웹 서비스를 사용하여 액세스하는 고해상도 사진은 Outlook 2013 Web App을 실행하는 사용자가 업로드할 수 있습니다. 사용자는 자신의 사진만 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="edb27-117">그러나 관리자는 Exchange 관리 셸 및 다음과 같은 일련의 Windows PowerShell 사용하여 모든 사용자의 사진을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="edb27-118">위의 예제의 첫 번째 명령은 이 cmdlet을 사용하여 C:\Photos\Kenmyer.jpg 파일의 내용을 읽고 해당 데이터를 `Get-Content` $photo.</span><span class="sxs-lookup"><span data-stu-id="edb27-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="edb27-119">두 번째 명령에서는 Exchange cmdlet을 사용하여 사진을 업로드하고 사진을 Ken Myer의 사용자 계정에 `Set-UserPhoto` 첨부합니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="edb27-120">이 예에서는 사용자 계정 ID로 Ken Myer의 Active Directory 표시 이름이 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="edb27-121">또한 사용자의 SMTP 주소 또는 사용자 계정 이름 등의 다른 식별자를 사용하여 사용자 계정을 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="edb27-122">자세한 내용은 Set-UserPhoto cmdlet에 대한 [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="edb27-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="edb27-p107">사진을 업로드한다고 해서 해당 사진이 Ken Myer의 사용자 계정에 할당되는 것은 아닙니다. 사진을 업로드하면 단지 Outlook Web App 옵션 페이지에 해당 사진의 미리 보기가 표시됩니다. 실제로 사진을 사용자 계정에 할당하려면 사용자가 옵션 페이지에서 **저장** 을 클릭하거나 관리자가 위 예에 있는 세 번째 명령을 실행해야 합니다. 세 번째 명령은 다음과 같이 Save 매개 변수를 사용하여 사진을 Ken Myer의 사용자 계정에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="edb27-127">새 사진이 사용자 계정에 할당되어 있는지 확인하려면 Ken Myer가 비즈니스용 Skype에 로그온하고 옵션을 선택한 다음 내 사진을 선택할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="edb27-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="edb27-128">그러면 새로 업로드된 사진이 Ken의 개인 사진으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="edb27-129">또한 관리자의 경우 Internet Explorer를 시작하고 다음과 유사한 URL로 이동하여 모든 사용자의 사진을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

<span data-ttu-id="edb27-130">관리자가 계정을 사용하여 사진을 볼 Internet Explorer 사용자가 비즈니스용 Skype에서 자신의 사진을 볼 수 없는 경우 Exchange 웹 서비스 또는 Exchange 자동 검색 서비스에 연결 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="edb27-131">또한 비즈니스용 Skype에서 이 사진을 사용할 수 있도록 설정하기 위해 추가 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="edb27-132">대신 사진이 업로드되고 cmdlet이 실행된 후 즉시 사용할 `Set-UserPhoto` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb27-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
