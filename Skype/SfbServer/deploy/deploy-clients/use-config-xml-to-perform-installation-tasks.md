---
title: Config.xml을 사용 하 여 비즈니스용 Skype 클라이언트에서 설치 작업 수행
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: '요약: Config.xml 파일을 사용 하 여 추가 설치 지침을 지정 하는 방법입니다.'
ms.openlocfilehash: a935e3623e99324eb24caef4e7e232d2311c5cfb
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768651"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="d774f-103">Config.xml을 사용 하 여 비즈니스용 Skype 클라이언트에서 설치 작업 수행</span><span class="sxs-lookup"><span data-stu-id="d774f-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="d774f-104">**요약:** Config.xml 파일을 사용 하 여 추가 설치 지침을 지정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="d774f-105">OCT (Office 사용자 지정 도구)는 사용자 지정 설치에 대 한 기본 도구 이지만 관리자는 Config.xml 파일을 사용 하 여 OCT에서 사용할 수 없는 추가 설치 지침을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-105">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT.</span></span> <span data-ttu-id="d774f-106">다음 사용자 지정은 Config.xml 파일만을 사용 하 여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-106">The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="d774f-107">네트워크 설치 지점의 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="d774f-108">설치할 제품을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-108">Select the products to install.</span></span>

- <span data-ttu-id="d774f-109">로깅 및 설치 사용자 지정 파일 및 소프트웨어 업데이트의 위치를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="d774f-110">사용자 이름 등의 설치 옵션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="d774f-111">Office를 설치 하지 않고 사용자의 컴퓨터에 LIS (로컬 설치 원본)를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="d774f-112">설치에서 언어를 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="d774f-113">Config.xml 파일을 사용 하 여 비즈니스용 Skype 자동 설치를 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="d774f-114">기본적으로 core product 폴더에 저장 된 Config.xml 파일입니다 (예: \ _product_. WW) 설치 프로그램이 해당 제품을 설치 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="d774f-115">예를 들어 다음 폴더의 Config.xml 파일은 비즈니스용 Skype를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="d774f-116">\\server\share\Skype15\Skype.WW \Configxml</span><span class="sxs-lookup"><span data-stu-id="d774f-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="d774f-117">비즈니스용 Skype 설치에 가장 일반적으로 사용 되는 Config.xml 요소는 다음 표에 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="d774f-118">**Config.xml 요소**</span><span class="sxs-lookup"><span data-stu-id="d774f-118">**Config.xml elements**</span></span>


| <span data-ttu-id="d774f-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="d774f-119">**Element**</span></span>              | <span data-ttu-id="d774f-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="d774f-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d774f-121">구성</span><span class="sxs-lookup"><span data-stu-id="d774f-121">Configuration</span></span>  <br/>     | <span data-ttu-id="d774f-122">최상위 수준 요소 (필수).</span><span class="sxs-lookup"><span data-stu-id="d774f-122">Top-level element (required).</span></span> <span data-ttu-id="d774f-123">Product = Lync (비즈니스용 Skype 클라이언트용으로 작동 하는 제품) 특성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-123">Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="d774f-124">없음 상태</span><span class="sxs-lookup"><span data-stu-id="d774f-124">OptionState</span></span>  <br/>       | <span data-ttu-id="d774f-125">설치 중에 특정 제품 기능을 처리 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="d774f-126">다음 특성을 사용 하 여 Outlook에 방해가 되는 공유 구성 요소를 포함 하는 Business Connectivity Services의 설치를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="d774f-127">Id = "주 Imain"</span><span class="sxs-lookup"><span data-stu-id="d774f-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="d774f-128">State = "없음"</span><span class="sxs-lookup"><span data-stu-id="d774f-128">State="Absent"</span></span> <br/>  <span data-ttu-id="d774f-129">Children = "Force"</span><span class="sxs-lookup"><span data-stu-id="d774f-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="d774f-130">표시</span><span class="sxs-lookup"><span data-stu-id="d774f-130">Display</span></span>  <br/>           | <span data-ttu-id="d774f-131">설치 프로그램이 사용자에 게 표시 하는 UI 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-131">The level of UI that Setup displays to the user.</span></span> <span data-ttu-id="d774f-132">일반적인 특성에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-132">Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="d774f-133">고 지 사항 = "예"</span><span class="sxs-lookup"><span data-stu-id="d774f-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="d774f-134">로깅하</span><span class="sxs-lookup"><span data-stu-id="d774f-134">Logging</span></span>  <br/>           | <span data-ttu-id="d774f-135">설정이 수행 하는 로깅 종류에 대 한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-135">Options for the kind of logging that Setup performs.</span></span> <span data-ttu-id="d774f-136">일반적인 특성에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-136">Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="d774f-137">Type = "Off"</span><span class="sxs-lookup"><span data-stu-id="d774f-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="d774f-138">설정</span><span class="sxs-lookup"><span data-stu-id="d774f-138">Setting</span></span>  <br/>           | <span data-ttu-id="d774f-139">Windows Installer 속성에 대 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-139">Specifies values for Windows Installer properties.</span></span> <span data-ttu-id="d774f-140">일반적인 특성에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-140">Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="d774f-141">설정 Id = " *name*" (Windows Installer 속성의 이름)</span><span class="sxs-lookup"><span data-stu-id="d774f-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="d774f-142">값 = " *값*" (속성에 할당할 값)</span><span class="sxs-lookup"><span data-stu-id="d774f-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="d774f-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="d774f-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="d774f-144">설치를 실행할 네트워크 설치 지점의 정규화 된 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-144">The fully qualified path of the network installation point from which the installation is to run.</span></span> <span data-ttu-id="d774f-145">Location 특성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-145">Includes the Location attribute:</span></span> <br/>  <span data-ttu-id="d774f-146">위치 = " *path*"</span><span class="sxs-lookup"><span data-stu-id="d774f-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="d774f-147">다음 예제에서는 비즈니스용 Skype 클라이언트의 일반적인 자동 설치에 대 한 Config.xml 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="d774f-148">Config.xml 파일을 사용 하 여 Office 설치 및 유지 관리 작업을 수행 하는 방법에 대 [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)한 자세한 내용은에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="d774f-149">Config.xml 파일을 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="d774f-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="d774f-150">메모장과 같은 텍스트 편집기 도구를 사용 하 여 Config.xml 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="d774f-151">변경 하려는 요소가 포함 된 선을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="d774f-152">사용할 자동 옵션으로 요소 항목을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="d774f-153">주석 구분 기호 "\<!--" 및 "--\>"을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="d774f-154">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="d774f-155">Config.xml 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d774f-155">Save the Config.xml file.</span></span>


