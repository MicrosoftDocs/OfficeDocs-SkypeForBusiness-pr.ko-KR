---
title: 비즈니스용 Skype 서버용 클라이언트 배포
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: '요약: 비즈니스용 Skype의 엔터프라이즈 클라이언트 설치 방법 개요.'
ms.openlocfilehash: f40a4948deb495998debd033f449d9439fd8329b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234414"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="64da5-103">비즈니스용 Skype 서버용 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="64da5-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="64da5-104">**요약:** 비즈니스용 Skype에 대 한 엔터프라이즈 클라이언트 설치 방법 개요.</span><span class="sxs-lookup"><span data-stu-id="64da5-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="64da5-105">비즈니스용 Skype를 사용자에 게 배포 하는 방법은 Office 365 계획의 일부로 비즈니스용 Skype를 구입 했는지에 따라, 볼륨 라이선스 버전의 비즈니스용 Skype를 구입 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="64da5-106">**Office 365** 비즈니스용 Skype를 포함 하는 Office 365 계획이 있는 경우 사용 되는 설치 기술을 간편 실행 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="64da5-107">Office 365를 사용 하면 Office 365 포털에서 사용자가 비즈니스용 Skype를 설치 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="64da5-108">또는 Microsoft System Center Configuration Manager와 같은 기존 소프트웨어 배포 도구를 사용 하 여 로컬 네트워크에 소프트웨어를 다운로드 한 후 사용자에 게 비즈니스용 Skype를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="64da5-109">Office 365와 함께 제공 되는 비즈니스용 Skype에 대 한 설치 정보는 [office 365의 비즈니스용 skype 클라이언트 배포](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64da5-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="64da5-110">**볼륨 라이선스** 볼륨 라이선스 버전의 비즈니스용 Skype 2015 또는 2016 클라이언트를 보유 하 고 있는 경우 사용 되는 설치 기술은 Windows Installer (MSI)입니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="64da5-111">Windows Installer 기반 설치 패키지는 여러 개의 MSI 파일로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="64da5-112">언어 중립적인 핵심 MSI 패키지는 완전 한 제품을 만들기 위해 하나 이상의 언어별 패키지와 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="64da5-113">설치 프로그램은 개별 패키지를 조립 하 고 사용자의 컴퓨터에 Office를 설치 하는 동안과 사용자 지정 및 유지 관리 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="64da5-114">비즈니스용 Skype 2019 클라이언트는 간편 실행 설치 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="64da5-115">이 섹션의 항목에서는 Windows Installer를 사용 하 고 사용자 지정 하 여 일반 절차를 통해 비즈니스용 Skype 클라이언트를 배포 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64da5-116">Outlook messaging 및 공동 작업 클라이언트 내에서 모임 관리를 지 원하는 Microsoft Office 용 Skype 모임 추가 기능이 비즈니스용 Skype 클라이언트에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="64da5-117">Office 365 설치 프로그램이 이전 버전의 Lync를 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="64da5-118">비즈니스용 Skype 클라이언트는 다른 Lync 클라이언트와 나란히 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="64da5-119">Windows 클라이언트 설치</span><span class="sxs-lookup"><span data-stu-id="64da5-119">Installing Windows clients</span></span>

- [<span data-ttu-id="64da5-120">비즈니스용 Skype 서버에서 Windows 클라이언트 설치 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="64da5-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="64da5-121">비즈니스용 Skype에서 클라이언트 환경 구성</span><span class="sxs-lookup"><span data-stu-id="64da5-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="64da5-122">비즈니스용 Skype 서버의 스마트 연락처 목록 구성</span><span class="sxs-lookup"><span data-stu-id="64da5-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="64da5-123">장치 클라이언트 설치</span><span class="sxs-lookup"><span data-stu-id="64da5-123">Installing device clients</span></span>

- [<span data-ttu-id="64da5-124">Windows Phone 용 비즈니스용 Skype 설치 및 테스트</span><span class="sxs-lookup"><span data-stu-id="64da5-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="64da5-125">IOS 용 비즈니스용 Skype 설치 및 테스트</span><span class="sxs-lookup"><span data-stu-id="64da5-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="64da5-126">비즈니스용 Skype 서버를 사용 하 여 Lync VDI 플러그 인 배포</span><span class="sxs-lookup"><span data-stu-id="64da5-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="64da5-127">비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="64da5-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="64da5-128">비즈니스용 Skype에서 Mac 클라이언트 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="64da5-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="64da5-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64da5-129">See also</span></span>

[<span data-ttu-id="64da5-130">Office 365에서 비즈니스용 Skype 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="64da5-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
