---
title: 비즈니스용 Skype 서버에서 Windows 클라이언트 설치 사용자 지정
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
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: '요약: 비즈니스용 Skype의 설치 방법 및 도구에 대한 개요입니다.'
ms.openlocfilehash: 001224369e46978e96ee063b31fcb546ef213a05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805718"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="37ce8-103">비즈니스용 Skype 서버에서 Windows 클라이언트 설치 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="37ce8-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="37ce8-104">**요약:** 비즈니스용 Skype의 설치 방법 및 도구 개요.</span><span class="sxs-lookup"><span data-stu-id="37ce8-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="37ce8-105">Microsoft 365 및 Office 365와 함께 제공된 비즈니스용 Skype에 대한 설치 정보는 [Microsoft 365 또는 Office 365에서](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)비즈니스용 Skype 클라이언트 배포를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37ce8-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="37ce8-106">엔터프라이즈 관리자는 이 섹션에서 설명하는 방법을 사용하여 볼륨 라이선스 버전의 비즈니스용 Skype에 대한 Windows Installer 기반(.msi) 설치를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ce8-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="37ce8-107">모든 사용자 지정 옵션을 제공하는 단일 도구가 아니기 때문에 비즈니스용 Skype 배포에서 이러한 방법의 조합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ce8-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="37ce8-108">다음 섹션에 설명된 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ce8-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="37ce8-109">비즈니스용 Skype 서버의 [OCT(Office](use-the-office-customization-tool-oct.md) 사용자 지정 도구)를 사용하여 비즈니스용 Skype 및 기타 Office 프로그램의 설정 옵션과 기능을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="37ce8-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="37ce8-110">[이 Config.xml](use-config-xml-to-perform-installation-tasks.md) 사용하여 비즈니스용 Skype 서버에서 설치 작업을 수행하여 네트워크 설치 지점의 경로를 지정하고 자동 설치를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="37ce8-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="37ce8-111">[비즈니스용 Skype 서버의](use-setup-command-line-options.md) 설치 명령줄 옵션을 사용하여 설치 중에 사용할 Config.xml 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="37ce8-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="37ce8-112">[그룹 정책 개체](configure-client-bootstrapping-policies.md) 편집기 MMC 스냅인을 사용하여 비즈니스용 Skype 서버에서 클라이언트 부트스트래프 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="37ce8-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="37ce8-113">Office 제품군을 배포할 때 구성할 다른 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ce8-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="37ce8-114">이 섹션의 항목에서는 이러한 사용자 지정 도구에 대해 간략하게 설명하고 비즈니스용 Skype와 관련한 고려 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="37ce8-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="37ce8-115">각 도구에 대한 자세한 Office 도움말 링크도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="37ce8-115">Included are links to detailed Office help for each tool.</span></span> 
  

