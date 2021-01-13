---
title: 비즈니스용 Skype 서버에서 OCT(Office 사용자 지정 도구) 사용
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
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: '요약: 비즈니스용 Skype 클라이언트에서 Office 사용자 지정 도구를 사용하는 방법'
ms.openlocfilehash: ba99f0556f3fb1d0e0f6870d1eaa7a3d2108b4d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812568"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="7c66e-103">비즈니스용 Skype 서버에서 OCT(Office 사용자 지정 도구) 사용</span><span class="sxs-lookup"><span data-stu-id="7c66e-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="7c66e-104">**요약:** 비즈니스용 Skype 클라이언트에서 Office 사용자 지정 도구를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="7c66e-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="7c66e-105">OCT(Office 사용자 지정 도구)는 설치 프로그램의 일부로, 많은 사용자 지정에 권장되는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="7c66e-106">OCT를 사용하면 Office를 사용자 지정하고 설치 사용자 지정 .msp 파일에 사용자 지정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="7c66e-107">이 파일은 네트워크 설치 지점의 Updates 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="7c66e-108">Office를 설치하면 설치 프로그램이 Updates 폴더에서 설치 사용자 지정 파일을 검색하고 사용자 지정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="7c66e-109">Updates 폴더는 Office 초기 설치 중에 소프트웨어 업데이트를 배포하는 데만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="7c66e-110">OCT는 설치의 일부분으로, 제품의 볼륨 라이선스 버전에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="7c66e-111">Office 원본 파일이 포함된 네트워크 설치 지점의 루트에서 명령줄에 입력하여 OCT를  `setup.exe /admin` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="7c66e-112">예를 들어 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="7c66e-113">관리자는 OCT를 사용하여 설치 사용자 지정 .msp 파일을 만들고 다음 영역을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="7c66e-114">**설치** 클라이언트 및 기본 조직 이름의 기본 설치 위치, 추가 네트워크 설치 원본, 제품 키, 최종 사용자 사용권 계약, 표시 수준, 제거할 이전 버전의 Office, 설치 중에 실행할 사용자 지정 프로그램, 보안 설정 및 설치 속성을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="7c66e-115">**기능** 사용자 설정을 구성하고 Office 기능 설치 방법을 사용자 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="7c66e-116">관리자는 OCT를 사용하여 사용자에 대한 Office 응용 프로그램 설정의 초기 기본값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="7c66e-117">사용자는 설치 후 대부분의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="7c66e-118">**추가 콘텐츠** 파일을 추가 또는 제거하고, 레지스트리 항목을 추가 또는 제거하고, 바로 가기를 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="7c66e-119">**Outlook** 사용자의 기본 Outlook 프로필을 사용자 지정하고, Exchange 설정을 지정하고, 계정을 추가하고, 계정을 제거하고, 설정을 내보내고, 보내기/받기 그룹을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="7c66e-120">OCT에 대한 자세한 내용은 [OCT를 사용하여 Office 2013을 사용자 지정합니다.](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="7c66e-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="7c66e-121">이 정보는 이후 버전의 Office에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c66e-121">Note that this information also applies to later versions of Office.</span></span>
  

