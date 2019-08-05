---
title: 비즈니스용 Skype 서버에서 OCT (Office 사용자 지정 도구) 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: '요약: 비즈니스용 Skype 클라이언트에서 Office 사용자 지정 도구를 사용 하는 방법을 설명 합니다.'
ms.openlocfilehash: a71ab8947d964dff90510257c4a8b2cbffb3be96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197713"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="07fb6-103">비즈니스용 Skype 서버에서 OCT (Office 사용자 지정 도구) 사용</span><span class="sxs-lookup"><span data-stu-id="07fb6-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="07fb6-104">**요약:** 비즈니스용 Skype 클라이언트에서 Office 사용자 지정 도구를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="07fb6-105">OCT (Office 사용자 지정 도구)는 설치 프로그램의 일부 이며 많은 사용자 지정에 권장 되는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="07fb6-106">OCT를 사용 하 여 Office를 사용자 지정 하 고 설치 사용자 지정 .msp 파일에 사용자 지정을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="07fb6-107">네트워크 설치 지점의 Updates 폴더에 파일을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="07fb6-108">Office를 설치 하면 설치 프로그램이 Updates 폴더에서 설치 사용자 지정 파일을 찾고 사용자 지정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="07fb6-109">업데이트 폴더는 Office 최초 설치 중에 소프트웨어 업데이트를 배포 하는 데에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="07fb6-110">OCT는 설치 프로그램의 일부 이며 볼륨 라이선스 버전의 제품에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="07fb6-111">Office 원본 파일을 포함 하 `setup.exe /admin` 는 네트워크 설치 지점의 루트에 있는 명령줄을 입력 하 여 OCT를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="07fb6-112">예를 들어 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-112">For example, use the following:</span></span>
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="07fb6-113">관리자는 OCT를 사용 하 여 설치 사용자 지정 .msp 파일을 만들고 다음 영역을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="07fb6-114">**설정** 클라이언트 및 기본 조직 이름, 추가 네트워크 설치 원본, 제품 키, 최종 사용자 사용권 계약, 표시 수준, 이전 버전의 Office에서 실행할 수 있는 사용자 지정 프로그램 등의 기본 설치 위치를 지정 하는 데 사용 됩니다. 설치, 보안 설정 및 설정 속성</span><span class="sxs-lookup"><span data-stu-id="07fb6-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="07fb6-115">**기능** 사용자 설정을 구성 하 고 Office 기능을 설치 하는 방법을 사용자 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="07fb6-116">관리자는 OCT를 사용 하 여 사용자에 대 한 Office 응용 프로그램 설정의 초기 기본 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="07fb6-117">설치 후 사용자가 대부분의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="07fb6-118">**추가 콘텐츠** 파일을 추가 또는 제거 하 고, 레지스트리 항목을 추가 또는 제거 하 고, 바로 가기를 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="07fb6-119">**Outlook** 사용자의 기본 Outlook 프로필을 사용자 지정 하 고, Exchange 설정을 지정 하 고, 계정 추가, 계정 제거 및 설정 내보내기를 하 고, Send\Receive 그룹을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="07fb6-120">OCT에 대 한 자세한 내용은 [oct를 사용 하 여 Office 2013 사용자 지정](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07fb6-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="07fb6-121">이 정보는 최신 버전의 Office에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07fb6-121">Note that this information also applies to later versions of Office.</span></span>
  

