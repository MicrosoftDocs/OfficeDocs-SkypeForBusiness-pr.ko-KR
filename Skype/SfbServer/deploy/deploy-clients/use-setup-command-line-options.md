---
title: 비즈니스용 Skype 클라이언트에서 설치 명령줄 옵션 사용
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '요약: Office 설치 Setup.exe 명령줄 작업을 설명하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837208"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="e7579-103">비즈니스용 Skype 클라이언트에서 설치 명령줄 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="e7579-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="e7579-104">**요약:** Office 설치 Setup.exe 명령줄 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="e7579-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="e7579-105">Setup.exe 명령줄이 사용되는 Office 설치 작업은 매우 한정적입니다.</span><span class="sxs-lookup"><span data-stu-id="e7579-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="e7579-106">설치 명령줄 옵션을 사용하는 대신 일반적으로 Office 사용자 지정 도구 및 Config.xml 사용자 지정을 위해 office 사용자 지정 도구 및 Config.xml 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e7579-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="e7579-107">다음 표에는 Office Setup.exe 명령줄에서 인식하는 명령줄 옵션이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7579-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="e7579-108">**Office 설치 명령줄 옵션**</span><span class="sxs-lookup"><span data-stu-id="e7579-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="e7579-109">**설치 명령줄 옵션**</span><span class="sxs-lookup"><span data-stu-id="e7579-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="e7579-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="e7579-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e7579-111">/admin</span><span class="sxs-lookup"><span data-stu-id="e7579-111">/admin</span></span>  <br/> |<span data-ttu-id="e7579-112">Office 사용자 지정 도구를 실행하여 설치 사용자 지정 파일(.msp 파일)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e7579-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="e7579-113">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="e7579-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="e7579-p102">지정된 설치 사용자 지정 파일을 설치에 적용합니다. 특정 사용자 지정 파일(.msp 파일)의 경로 또는 사용자 지정 파일이 저장된 폴더의 경로를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7579-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="e7579-116">/config [path]</span><span class="sxs-lookup"><span data-stu-id="e7579-116">/config [path]</span></span>  <br/> |<span data-ttu-id="e7579-117">설치하는 동안 설치 프로그램에서 사용할 Config.xml 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7579-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="e7579-118">/config 옵션을 사용하여 비즈니스용 Skype Config.xml 사용자 지정한 Config.xml 지정합니다. 예를 들면 다음과 같습니다.  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="e7579-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="e7579-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="e7579-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="e7579-120">수정된 Config.xml 파일과 함께 유지 관리 모드로 설치 프로그램을 실행하고 기존 Office 설치를 변경하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7579-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="e7579-121">예를 들어 /modify 옵션을 사용하여 비즈니스용 Skype 기능을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7579-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="e7579-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="e7579-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="e7579-123">사용자의 컴퓨터에서 설치를 실행하여 비즈니스용 Skype를 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="e7579-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="e7579-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="e7579-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="e7579-125">설치를 실행하여 사용자 컴퓨터에서 비즈니스용 Skype를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e7579-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


