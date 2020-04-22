---
title: 비즈니스용 Skype 서버에 대 한 클라이언트 배포
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
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: '요약: 비즈니스용 Skype에 대 한 엔터프라이즈 클라이언트 설치 방법에 대해 간략하게 설명 합니다.'
ms.openlocfilehash: cdee3db6dc6fcec646ee2e15b6aeebc298d75b67
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778284"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="1af15-103">비즈니스용 Skype 서버에 대 한 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="1af15-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="1af15-104">**요약:** 비즈니스용 Skype에 대 한 엔터프라이즈 클라이언트 설치 방법 개요</span><span class="sxs-lookup"><span data-stu-id="1af15-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="1af15-105">비즈니스용 Skype를 사용자에 게 배포 하는 방법은 Office 365 계획의 일부로 비즈니스용 Skype를 구매한 경우 또는 볼륨 라이선스 버전의 비즈니스용 Skype를 구매한 경우에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="1af15-106">**Office 365** 비즈니스용 Skype를 포함 하는 Office 365 요금제가 있는 경우 사용 되는 설치 기술을 간편 실행 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="1af15-107">Office 365를 사용 하 여 Microsoft 365 관리 센터에서 사용자를 위해 비즈니스용 Skype를 설치 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-107">With Office 365, you can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="1af15-108">또는 소프트웨어를 로컬 네트워크에 다운로드 한 다음 Microsoft 끝점 구성 관리자와 같은 기존 소프트웨어 배포 도구를 사용 하 여 비즈니스용 Skype를 사용자에 게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="1af15-109">Office 365와 함께 제공 되는 비즈니스용 Skype에 대 한 설치 정보를 보려면 [office 365에서 비즈니스용 skype 클라이언트 배포](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1af15-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="1af15-110">**볼륨 라이선스** 볼륨 라이선스 버전의 비즈니스용 Skype 2015 또는 2016 클라이언트를 보유 하는 경우 사용 되는 설치 기술은 Windows Installer (MSI)입니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="1af15-111">Windows Installer 기반 설치 패키지는 여러 개의 MSI 파일로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="1af15-112">언어 중립적인 핵심 MSI 패키지는 완벽한 제품 구성을 위해 하나 이상의 언어별 패키지로 조합됩니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="1af15-113">설치 프로그램은 개별 패키지를 조합하고 사용자 컴퓨터에 Office를 설치하는 동안 그리고 설치 후에 사용자 지정 및 유지 관리 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="1af15-114">비즈니스용 Skype 2019 클라이언트는 간편 실행 설치 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="1af15-115">이 섹션의 항목에서는 Windows Installer를 사용 하 고 사용자 지정 하 여 일반 절차를 통해 비즈니스용 Skype 클라이언트를 사용자에 게 배포 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1af15-116">Outlook 메시징 및 공동 작업 클라이언트에서 모임 관리를 지 원하는 Microsoft Office 용 Skype 모임 추가 기능이 비즈니스용 Skype 클라이언트에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1af15-117">Office 365 설치 프로그램은 이전 버전의 Lync를 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="1af15-118">비즈니스용 Skype 클라이언트는 다른 Lync 클라이언트와 나란히 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1af15-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="1af15-119">Windows 클라이언트 설치</span><span class="sxs-lookup"><span data-stu-id="1af15-119">Installing Windows clients</span></span>

- [<span data-ttu-id="1af15-120">비즈니스용 Skype 서버에서 Windows 클라이언트 설치 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1af15-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="1af15-121">비즈니스용 Skype를 사용 하 여 클라이언트 환경 구성</span><span class="sxs-lookup"><span data-stu-id="1af15-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="1af15-122">비즈니스용 Skype 서버에서 스마트 연락처 목록 구성</span><span class="sxs-lookup"><span data-stu-id="1af15-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="1af15-123">장치 클라이언트 설치</span><span class="sxs-lookup"><span data-stu-id="1af15-123">Installing device clients</span></span>

- [<span data-ttu-id="1af15-124">Windows Phone 용 비즈니스용 Skype 설치 및 테스트</span><span class="sxs-lookup"><span data-stu-id="1af15-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="1af15-125">IOS 용 비즈니스용 Skype 설치 및 테스트</span><span class="sxs-lookup"><span data-stu-id="1af15-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="1af15-126">비즈니스용 Skype 서버를 사용 하 여 Lync VDI 플러그 인 배포</span><span class="sxs-lookup"><span data-stu-id="1af15-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="1af15-127">비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="1af15-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="1af15-128">비즈니스용 Skype에서 Mac 클라이언트 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1af15-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="1af15-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1af15-129">See also</span></span>

[<span data-ttu-id="1af15-130">Office 365에서 비즈니스용 Skype 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="1af15-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
