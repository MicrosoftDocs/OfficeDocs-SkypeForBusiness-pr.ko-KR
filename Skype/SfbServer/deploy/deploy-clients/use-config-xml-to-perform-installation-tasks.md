---
title: 비즈니스용 Skype Config.xml 설치 작업을 수행하기 위해 다음을 수행합니다.
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: '요약: Config.xml 파일을 사용하여 추가 설치 지침을 지정하는 방법'
ms.openlocfilehash: 1b8aeeb16e061e7816e475f01c9cd9a9146306ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825188"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="8eafb-103">비즈니스용 Skype Config.xml 설치 작업을 수행하기 위해 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="8eafb-104">**요약:** 추가 설치 Config.xml 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="8eafb-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="8eafb-p101">사용자 지정 설치에는 기본적으로 OCT(Office 사용자 지정 도구)가 사용되기는 하지만, 관리자는 Config.xml 파일을 사용하여 OCT에서 사용할 수 없는 추가 설치 지침을 지정할 수 있습니다. Config.xml 파일을 통해서만 수행할 수 있는 사용자 지정 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="8eafb-107">네트워크 설치 지점 경로 지정</span><span class="sxs-lookup"><span data-stu-id="8eafb-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="8eafb-108">설치할 제품 선택</span><span class="sxs-lookup"><span data-stu-id="8eafb-108">Select the products to install.</span></span>

- <span data-ttu-id="8eafb-109">설치 사용자 지정 파일 및 소프트웨어 업데이트의 위치와 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="8eafb-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="8eafb-110">사용자 이름 등의 설치 옵션 지정</span><span class="sxs-lookup"><span data-stu-id="8eafb-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="8eafb-111">Office를 설치하지 않고 사용자 컴퓨터에 LIS(로컬 설치 원본) 복사</span><span class="sxs-lookup"><span data-stu-id="8eafb-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="8eafb-112">설치에서 언어 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="8eafb-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="8eafb-113">비즈니스용 Skype 자동 설치를 Config.xml 파일을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="8eafb-114">기본적으로 핵심 Config.xml 폴더(예: \ 제품)에 저장된 _파일입니다._ WW)는 설치 시 제품을 설치하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="8eafb-115">예를 들어 다음 Config.xml 파일에서 비즈니스용 Skype를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="8eafb-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="8eafb-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="8eafb-117">다음 Config.xml 비즈니스용 Skype 설치에 가장 일반적으로 사용되는 구성 요소에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="8eafb-118">**Config.xml 요소**</span><span class="sxs-lookup"><span data-stu-id="8eafb-118">**Config.xml elements**</span></span>


| <span data-ttu-id="8eafb-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="8eafb-119">**Element**</span></span>              | <span data-ttu-id="8eafb-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="8eafb-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8eafb-121">구성</span><span class="sxs-lookup"><span data-stu-id="8eafb-121">Configuration</span></span>  <br/>     | <span data-ttu-id="8eafb-122">최상위 요소(필수)입니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-122">Top-level element (required).</span></span> <span data-ttu-id="8eafb-123">Product 특성(예: Product=Lync)을 포함(비즈니스용 Skype 클라이언트에 대해 작동)</span><span class="sxs-lookup"><span data-stu-id="8eafb-123">Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="8eafb-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="8eafb-124">OptionState</span></span>  <br/>       | <span data-ttu-id="8eafb-125">특정 제품 기능이 설치 중에 처리되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="8eafb-126">다음 특성을 사용하여 Outlook을 방해하는 공유 구성 Business Connectivity Services 포함된 응용 프로그램은 설치되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="8eafb-127">Id="LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="8eafb-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="8eafb-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="8eafb-128">State="Absent"</span></span> <br/>  <span data-ttu-id="8eafb-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="8eafb-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="8eafb-130">표시</span><span class="sxs-lookup"><span data-stu-id="8eafb-130">Display</span></span>  <br/>           | <span data-ttu-id="8eafb-p105">설치 프로그램에서 사용자에게 표시하는 UI의 수준입니다. 일반적인 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="8eafb-133">CompletionNotice="Yes"</span><span class="sxs-lookup"><span data-stu-id="8eafb-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="8eafb-134">로깅</span><span class="sxs-lookup"><span data-stu-id="8eafb-134">Logging</span></span>  <br/>           | <span data-ttu-id="8eafb-p106">설치 프로그램이 수행하는 로깅 종류에 대한 옵션입니다. 일반적인 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="8eafb-137">Type ="Off"</span><span class="sxs-lookup"><span data-stu-id="8eafb-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="8eafb-138">설정</span><span class="sxs-lookup"><span data-stu-id="8eafb-138">Setting</span></span>  <br/>           | <span data-ttu-id="8eafb-p107">Windows Installer 속성의 값을 지정합니다. 일반적인 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="8eafb-141">Setting Id=" *이름*" (Windows Installer 속성의 이름)</span><span class="sxs-lookup"><span data-stu-id="8eafb-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="8eafb-142">Value=" *값*" (속성에 할당할 값)</span><span class="sxs-lookup"><span data-stu-id="8eafb-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="8eafb-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="8eafb-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="8eafb-p108">설치를 실행할 네트워크 설치 지점의 정규화된 경로입니다. Location 특성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="8eafb-146">Location=" *path*"</span><span class="sxs-lookup"><span data-stu-id="8eafb-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="8eafb-147">다음 예에서는 비즈니스용 Skype Config.xml 자동 설치에 대한 파일 형식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="8eafb-148">office 설치 및 유지 관리 작업을 수행하기 위해 Config.xml 파일에 대한 자세한 정보를 사용할 수 [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="8eafb-149">Config.xml 파일을 사용자 지정하려면</span><span class="sxs-lookup"><span data-stu-id="8eafb-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="8eafb-150">메모장과 같은 텍스트 편집기 도구를 사용하여 Config.xml 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="8eafb-151">변경할 요소가 포함된 줄을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="8eafb-152">요소 항목을 사용하려는 자동 옵션으로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="8eafb-153">주석 분리기 " "를 제거해야 \<!--" and "--\> 합니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="8eafb-154">예를 들어 다음과 같은 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="8eafb-155">Config.xml 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8eafb-155">Save the Config.xml file.</span></span>


