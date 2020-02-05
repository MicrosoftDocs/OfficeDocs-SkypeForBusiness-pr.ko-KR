---
title: 비즈니스용 Skype 클라이언트에서 설치 명령줄 옵션 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '요약: Office 설치 프로그램의 setup.exe 명령줄 작업에 대해 알아봅니다.'
ms.openlocfilehash: 68add6e2744e9648db49508519c14e64b4e6aeef
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768631"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="a0a0d-103">비즈니스용 Skype 클라이언트에서 설치 명령줄 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="a0a0d-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="a0a0d-104">**요약:** Office 설치 프로그램의 setup.exe 명령줄 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="a0a0d-105">Setup.exe 명령줄은 Office 설치 프로그램의 매우 적은 작업에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="a0a0d-106">설치 명령줄 옵션을 사용 하는 대신 일반적으로 Office 사용자 지정 도구 및 Config .xml 파일을 사용 하 여 제품 설정 및 기능을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="a0a0d-107">Office Setup.exe 명령줄은 다음 표에 설명 된 명령줄 옵션을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="a0a0d-108">**Office 설치 명령줄 옵션**</span><span class="sxs-lookup"><span data-stu-id="a0a0d-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="a0a0d-109">**설치 명령줄 옵션**</span><span class="sxs-lookup"><span data-stu-id="a0a0d-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="a0a0d-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="a0a0d-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a0a0d-111">/admin</span><span class="sxs-lookup"><span data-stu-id="a0a0d-111">/admin</span></span>  <br/> |<span data-ttu-id="a0a0d-112">Office 사용자 지정 도구를 실행 하 여 설치 사용자 지정 파일 (.msp 파일)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="a0a0d-113">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="a0a0d-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="a0a0d-114">설치에 지정 된 설치 사용자 지정 파일을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-114">Applies the specified Setup customization file to the installation.</span></span> <span data-ttu-id="a0a0d-115">특정 사용자 지정 파일 (.msp 파일) 또는 사용자 지정 파일을 저장 하는 폴더에 대 한 경로를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-115">You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="a0a0d-116">/config [path]</span><span class="sxs-lookup"><span data-stu-id="a0a0d-116">/config [path]</span></span>  <br/> |<span data-ttu-id="a0a0d-117">설치 중에 설치 하는 Config.xml 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="a0a0d-118">/Config 옵션을 사용 하 여 비즈니스용 Skype 설치를 위해 사용자 지정한 Config.xml 파일을 지정 합니다 예:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="a0a0d-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="a0a0d-119">/Skype 수정</span><span class="sxs-lookup"><span data-stu-id="a0a0d-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="a0a0d-120">수정 된 Config.xml 파일을 사용 하 여 유지 관리 모드에서 설치 프로그램을 실행 하 고 기존 Office 설치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="a0a0d-121">예를 들어/수정 옵션을 사용 하 여 비즈니스용 Skype 기능을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="a0a0d-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="a0a0d-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="a0a0d-123">사용자의 컴퓨터에서 설치 프로그램을 실행 하 여 비즈니스용 Skype를 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="a0a0d-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="a0a0d-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="a0a0d-125">설치 프로그램을 실행 하 여 사용자 컴퓨터에서 비즈니스용 Skype를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a0d-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


