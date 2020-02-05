---
title: 비즈니스용 Skype 서버에서 Windows 클라이언트 설치 사용자 지정
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
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: '요약: 비즈니스용 Skype의 설치 방법 및 도구에 대 한 개요입니다.'
ms.openlocfilehash: 4661a440cfcb85a097f7760e2dd8992faf9adb70
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768801"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="da74b-103">비즈니스용 Skype 서버에서 Windows 클라이언트 설치 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="da74b-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="da74b-104">**요약:** 비즈니스용 Skype의 설치 방법 및 도구에 대 한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="da74b-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da74b-105">Office 365와 함께 제공 되는 비즈니스용 Skype에 대 한 설치 정보는 [office 365의 비즈니스용 skype 클라이언트 배포](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da74b-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="da74b-106">엔터프라이즈 관리자는이 섹션에서 설명 하는 방법을 사용 하 여 비즈니스용 Skype 라이선스 버전에 대 한 Windows Installer 기반 (.msi) 설치를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da74b-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="da74b-107">모든 사용자 지정 옵션을 제공 하는 도구는 없기 때문에 비즈니스용 Skype 배포에서 이러한 방법을 함께 사용 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="da74b-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="da74b-108">다음 섹션에서 설명 하는 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da74b-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="da74b-109">비즈니스용 skype [서버에서 OCT (Office 사용자 지정 도구)를 사용](use-the-office-customization-tool-oct.md) 하 여 비즈니스용 skype 및 다른 Office 프로그램에 대 한 설정 옵션 및 기능을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da74b-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="da74b-110">[Config.xml을 사용 하 여 비즈니스용 Skype 서버에서 설치 작업을 수행](use-config-xml-to-perform-installation-tasks.md) 하 여 네트워크 설치 지점의 경로를 지정 하 고 자동 설치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="da74b-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="da74b-111">[비즈니스용 Skype Server의 설치 명령줄 옵션을 사용](use-setup-command-line-options.md) 하 여 설치 중에 사용할 config.xml 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da74b-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="da74b-112">그룹 정책 개체 편집기 MMC 스냅인을 사용 하 여 [비즈니스용 Skype 서버에서 클라이언트 부트스트랩 정책을 구성](configure-client-bootstrapping-policies.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="da74b-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="da74b-113">Office 제품군을 배포 하는 동안 다른 옵션을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="da74b-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="da74b-114">이 섹션의 항목에서는 이러한 사용자 지정 도구에 대해 개괄적으로 살펴보고 비즈니스용 Skype에 대 한 고려 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="da74b-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="da74b-115">각 도구에 대 한 자세한 Office 도움말에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="da74b-115">Included are links to detailed Office help for each tool.</span></span> 
  

